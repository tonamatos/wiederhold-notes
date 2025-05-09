---
title: "1.5. Induction"
draft: false
---
## Informal construction of the naturals

>[!warning] Note:
>
>Informal discussions are inadequate for these notes and are thus mostly omitted.

## Why induction works

Induction is a **proving technique**. The most elementary version of induction is used to prove statements of the form

$$
\text{for all }n\in\mathbb N,\quad P(n),
$$

where $\mathbb N$ is the set of natural numbers, that is $\mathbb N=\{0,1,2,\dots\}$ and $P(n)$ is a statement about $n$. For example, $P(n)$ could be

$$
\text{if }n>2, \text{ then }n\text{ is the sum of two prime numbers}.
$$

That this particular statement is true for all $n$ is known as the _Goldbach Conjecture_ and it remains a famous open problem.

The property that makes induction possible is the _well-ordering principle_:

>[!def] Axiom (well-ordering principle).
>
>Every non-empty subset of the naturals has a least element.

Proving this is beyond the scope of the course, but the curious reader will verify that the next two corollaries of the theorem are indeed logically equivalent to it. What this means meta-mathematically is that any statement provable by one technique is provable by all. Knowing which one to pick is a skill acquired by practice.

Some questions to deepen your understanding of the well-ordering principle follow.

>[!note] Exercises.
>1. Is it true that every non-empty subset of the naturals has a _maximal_ element?
>2. Is the well-ordering principle true if you replace the naturals with the integers?

The way this principle is applied is that, whenever some natural number has a property, there must always be a **first** natural number with that property. Let us start with a simple example often attributed to Gauss.

>[!thm] Theorem (Gauss summation formula).
>
>For any natural number $n$,
>
>$$
>\sum_{k=0}^nk=\frac{n(n+1)}2.
>$$

>[!proof]+ Proof:
>
>Let $A$ be the set of natural numbers for which the statements does **not** hold. That is, $A$ is the set of all counterexamples, which I now show must be empty.
>
>By contradiction, suppose that $A\neq\emptyset$. Then the well-ordering principle dictates that there must be a smallest natural $n$ inside of $A$. First, notice that $n$ cannot be zero, because zero **does** satisfy the proposition: $\sum_{k=0}^0k=0=\frac{0(0+1)}2.$
>
>Then it makes sense to consider the natural number $n-1$, which by _minimality_ (meaning, by the fact that $n$ is the smallest element of $A$) cannot be in $A$, and thus must satisfy the proposition. That is,
>
>$$
>\sum_{k=0}^{n-1}k=\frac{(n-1)n}2.
>$$
>
>But then, if I add $n$ on both sides of that equality,
>
>$$
>\sum_{k=0}^nk=\sum_{k=0}^{n-1}k+n=\frac{(n-1)n}2+n=\frac{(n-1)n+2n}2=\frac{n(n+1)}2,
>$$
>
>which is the conclusion of the proposition but for $n$. This is a contradiction. Hence, such an $n$ cannot exist and thus $A=\emptyset$ or, in words, **all naturals satisfy the proposition**.

There is an easier way of writing the previous proof, namely using the following principle instead.

>[!thm] Corollary (Principle of mathematical induction).
>
>Suppose that $A\subseteq\mathbb N$ satisfies that
>
>1. $0\in A$; and that
>2. for all $n$, $n\in A$ implies $n+1\in A$.
>
>Then, $A$ must contain every natural number. That is, $A=\mathbb N$.

>[!proof]+ Proof:
>
>By contradiction, suppose that $A\subseteq\mathbb N$ satisfies (1.) and (2.) but that the conclusion is wrong, that is, that $A\subsetneq\mathbb N$. Then, there exists some natural number not in $A$. By the well-ordering principle, there is a smallest natural $m$ not in $A$.
>
>By the assumption (1.), $m>0$. Then, by the choice of $m$, $m-1\in A$. But then, applying the assumption (2.), $m\in A$, which is a contradiction.
>
>Therefore, such an $m$ cannot exist and hence $A=\mathbb N$.

>[!hint] Think.
>
>How would the conclusion change if (1.) is changed to $3\in A$ instead? What about $m\in A$?

## How to write proofs by induction

This principle offers a sort of "cooking recipe" for writing proofs: First, verify that $0$ (or whatever natural the induction starts at) has the property you want to prove for all $n$. This is called the _Base case_. Then, assume the _Inductive hypothesis_, or the fact that $n\in A$. Finally, perform the _Inductive step_, where you use the fact that $n$ has the sought property to show that $n+1\in A$ and thus you are done.

>[!note] Exercise.
>
>Rewrite the proof of the Gauss summation formula using this form.

>[!warning] Warning:
>
>A common mistake is having an inductive hypothesis that assumes what you want to prove in the first place. For example, assuming that for all $n$, $\sum_{k=0}^nk=n(n+1)/2$ as part of the inductive hypothesis.

While this structure is useful for standardizing solutions and learning how to write proofs, **I discourage rote memorization**, as it hinders understanding more complicated proofs that might not be easily written in this format.

>[!warning] Warning:
>
>Careful when applying the inductive hypothesis to the inductive step. The following example illustrates one possible complication.

>[!error] Fallacious claim:
>
>All trains have just one type of car.

>[!proof]+ Fallacious proof:
>
>By induction on $n$, the length of the train.
>
>**Base case:** When $n=1$, the train has just one car, and thus all cars are the same type.
>
>**Inductive hypothesis:** Suppose that for $n$, all trains of length $n$ just have one type of car.
>
>**Inductive step:** Let $C_1,C_2,\dots,C_{n+1}$ be the cars of an arbitrary train of length $n+1$. By the inductive hypothesis, $C_1,C_2,\dots C_n$ are the same type and $C_2,C_3,\dots,C_{n+1}$ are the same type (given that they both are trains of length $n$). Since $C_1$ and $C_2$ are the same type and $C_2$ and $C_3$ are the same type, then all cars must be the same type. Thus, the train has just one type of car.

>[!note] Exercise.
>
>Find the first mistake in the previous fallacious proof.

## Strong induction

As I move to more complicated proofs by induction, one might run into the following situation where reducing the statement from $n+1$ to $n$ is unhelpful or tricky. In this case, it would be much better to reduce it to say $n-2$ or some other (or even multiple!) natural $k\leq n$. Here is an example of this scenario.

>[!thm] Claim.
>
>Alice has an infinite amount of \$6 coins and \$10 and \$15 bills. Use induction to prove that Alice can form any amount of at least \$30 using these. For example, Alice can form \$31 by taking one of each, or she can form \$32 by taking two \$10 bills and two coins.
>
>>[!hint]- Hint.
>>
>>The formal statement is: for every natural $n$, if $n\geq30$, then there exist naturals $s,t,u$ such that $n=15s+10t+6u$.

>[!proof]+ Proof:
>
>>[!fail] Removed for being in the problem set.


You can **strengthen**} the hypothesis by not just assuming that the property you want to prove holds for the previous natural but indeed **all** smaller naturals:

>[!thm] Corollary (Principle of strong mathematical induction).
>
>Suppose that $A\subseteq\mathbb N$ satisfies that
>
>1. for every $n$, if for all $k<n$, $k\in A$, then $n\in A$.
>
>Then, $A=\mathbb N$.

There is no need to add the assumption that $0\in A$ in this case, since this is a consequence of property (1.). Indeed, by vacuous truth, any natural $k<0$ (of which there are none) satisfies that $k\in A$.

>[!warning] Warning:
>
>This does not mean that, in general, proofs by strong induction do not need a base case.

>[!proof]+ Proof:
>
>Suppose that $A\neq\mathbb N$. Then, by the well-ordering principle, there must be a least natural $n\notin A$. By minimality, any natural $k<n$ must be in $A$. But by property (1.), this would imply that $n\in A$, a contradiction.

I illustrate the fact that, in many cases, you still need to provide the base case to complete the proof by rewriting the proof of the Claim from above.

```python
# Can you write a computer program that explicitly finds these paremeters?
# Something like this:

def money(n: int):
	# {YOUR CODE HERE}
	return s, t, u
```

>[!proof]+ Proof of Claim by strong induction:
>
>>[!fail] Removed for being in the problem set.


Implementing this particular idea in code produces a _greedy algorithm_ that attempts to maximize the number of coins. Find similar proofs/algorithms that maximize the bills instead. This makes the proof longer to write. Why?

Moreover, the attentive reader will verify that the base cases were tacitly used in the original proof, hinting the fact that both induction types are really just **different ways of writing the same proof**.