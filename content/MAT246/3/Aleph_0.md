---
title: "3.4. Aleph naught"
draft: true
---
## Countability

Let me relax the definition of equinumerous a bit. Often I want to compare the sizes of sets without declaring exactly what that size is. I merely want to point out that one set has _at least as many elements_ as another set.

>[!warning] Note:
>
>I give precise intuition for this in the lectures. This requires pointing and sketching so I will not include that here.

>[!def] Definition.
>
>For two sets $A$ and $B$, I use the symbol $|A|\leq|B|$ to indicate that there is an injective function from $A$ to $B$.

Here are some basic properties that describe $\leq$ as an _order_ among sets. The same metamathematical warning as above applies here, however.

>[!thm] Proposition.
>
>Let $A$, $B$ and $C$ be sets.
>
>1. If $|A|\leq|B|$ and $|B|\leq|C|$, then $|A|\leq|C|$ (_Transitivity_)
>2. $|A|\leq|B|$ and $|B|\leq|A|$ if and only if $|A|=|B|$ (_Antisymmetry_)
>3. If $A\subseteq B$, then $|A|\leq|B|$ (_Monotonicity_)
>4. $|A|\leq|A|$ (_Reflexivity_)
>5. Either $|A|\leq|B|$ or $|B|\leq|A|$ (_Linearity_)
>6. $|A|\leq|B|$ if and only if there exists a surjection $B\to A$.

If $|A|\leq|B|$ and $|A|\neq|B|$, I write $|A|<|B|$.

>[!warning] Stop! Try proving these yourself before continuing or you'll miss out.

It is surprisingly deceptive knowing which proofs are easy and which ones are hard.

>[!proof]- Proof:
>
>1. Composition of injective functions is injective.
>2. The $\boxed\Longrightarrow$ implication is known as the [Cantor-Schröder-Bernstein theorem](https://en.wikipedia.org/wiki/Schr%C3%B6der%E2%80%93Bernstein_theorem), and its proof is beyond the scope of this course. The other implication is immediate.
>3. The inclusion map is injective.
>4. The $\boxed\Longleftarrow$ implication of 2 implies this result.
>5. This is equivalent to the axiom of choice. You will only see this in a set theory course. (But unknowingly use it all the time. E.g. linear algebra, analysis, etc.) [Here is a relevant discussion](https://math.stackexchange.com/questions/268942/for-any-two-sets-a-b-a-leqb-or-b-leqa).
>6. See Problem Set 1.

>[!def] Definition (Countable).
>
>A set $X$ is _countable_ if $|X|\leq|\mathbb N|$.

>[!abstract] Examples.
>
>The following sets are all countable.
>
>1. $\mathbb N$.
>2. Any finite set.
>3. The set of even naturals.
>4. (Galileo) The set of squares, i.e. $\{n^2:n\in\mathbb N\}$
>5. (Hilbert) $\mathbb Z$.
>6. $\mathbb N\times\mathbb N$.
>7. The set of positive rationals.

>[!warning] Note:
>
>These proofs are best understood by interactively sketching and drawing, in the lectures.

>[!proof]- Proof:
>
>I only do the ones that require work.
>
>8. Consider mapping $n\mapsto n^2$.
>9. Define $f(n)$ as $2n$ for non-negative $n$ and $2(-n)+1$ otherwise. Show it is injective.
>10. Map $(n,m)$ to $2^n3^m$. Injectivity follows from FTA. Is this mapping a bijection?
>11. The same idea as (6) works here too.

## $\aleph_0$

In the lecture's informal discussion, I talked about the concept of _cardinal_ and _ordinal_ numbers. The former are often denoted by the first letter of the Hebrew alphabet, $\aleph_0$. The smallest transfinite ordinal number is $\omega$, and the corresponding cardinal is the first infinite cardinal number: $\aleph_0$. I declare

$$
|\mathbb N|=\aleph_0.
$$

This section is devoted to convincing you that $\aleph_0$ is the "smallest" infinity.

>[!thm] Theorem.
>
>The set $X$ is infinite if and only if $|\mathbb N|\leq|X|$. 

>[!proof]+ Proof:
>First, suppose that $X$ is infinite. I define $f:\mathbb N\to X$ _recursively_. Since clearly $X\neq\emptyset$, pick any element $f(0)\in X$. Suppose that $f$ is defined on $k$ for all $k<n$. Since $X$ is infinite, $X\not\subseteq\{f(k):k<n\}$. Thus, there exists $x\in X$ that is not of the form $f(k)$ for any $k<n$. Let $f(n):=x$. By induction, $f$ is a function $\mathbb N\to X$. The injectivity of $f$ also follows from induction.
>
>Now assume that $|\mathbb N|\leq|X|$. Thus there is an injection $\mathbb N\to X$. This mapping is bijective onto its image, and thus equinumerous with a subset of $X$. If $X$ were finite, so would this subset be. But this contradicts that $\mathbb N$ is infinite. Therefore, $X$ must be infinite.

>[!thm] Theorem.
>
>A set is countable if and only if it is finite or equinumerous with $\mathbb N$. In the latter case I say it is _countably infinite_.

>[!proof]+ Proof:
>
>This follows from Cantor-Bernstein or "antisymmetry."

>[!question] Reflect.
>
>Can you find a set whose powerset is countably infinite?

>[!thm] Theorem ("The cardinal $\aleph_1$ is _regular_").
>
>The countable union of countable sets is countable.

>[!proof]+ Proof (Hilbert):
>
>Let $\mathcal F$ be a countable collection of countable sets.
>
>>[!hint] Hint.
>>
>>If it makes the notation easier for you, assume that $\mathcal F=\{A_n:n\in\mathbb N\}$ and that $A_n=\{a^{(n)}_0,a^{(n)}_1,\dots\}$ and rewrite the proof using this notation instead.
>
>By definition, there is an injective mapping $F:\mathcal F\to\mathbb N$, and for every $A\in\mathcal F$, there is an injective function $f_A:A\to\mathbb N$.
>
>I now define an injective mapping $\Psi:\bigcup\mathcal F\to\mathbb N\times\mathbb N$. Recall that $\bigcup\mathcal F$ is simply the union over all sets in the family, that is
>
>$$
>\bigcup\mathcal F=\bigcup_{A\in\mathcal F}A=\{x:\exists A\in\mathcal F,\ x\in A\}.
>$$ 
>
>More details on indexed families can be found [[Indexed families|here]]. Given $x\in\bigcup\mathcal F$, use the well-ordering principle to select the set $A_x\in\mathcal F$ for which $F(x)$ is the smallest natural such that $x\in A_x$. Then define $\Psi(x):=(F(x),f_{A_x}(x))$. Since both $F$ and $f_{A_x}$ are injective, $\Psi$ is injective. Therefore, by the example (6) from the Countability section,
>
>$$
>\left|\bigcup\mathcal F\right|\leq|\mathbb N\times\mathbb N|\leq|\mathbb N|.
>$$
>
>By transitivity, I am done.

## Cantor's theorems

>[!thm] Cantor's diagonal argument.
>
>The set of real numbers is **not** countable.

>[!proof] Informal proof seen in lectures.

>[!question] Question (Continuum hypothesis).
>
>Can you find a set $X$ such that $|\mathbb N|<|X|<|\mathbb R|$?

**Answer:** In the standard axioms of set theory I follow (Zermelo-Fraenkel or ZFC), this problem is _undecidable_, meaning both the statement and its negation are proven to be un-provable.

I finally arrive at the first theorem of set theory:

>There are infinities of different sizes.

>[!thm] Theorem (Cantor).
>
>For any set $X$, $|X|<|\mathcal P(X)|$.

An exercise worth writing down before continuing is below.

>[!note] Exercise.
>
>Formalize and write down an argument that $|\{0,1\}^X|=2^{|X|}=|\mathcal P(X)|$. You may **not** use this for PS3, as it is the same idea as below, just for functions instead of subsets.

>[!warning] Note:
>
>The diagram seen in lectures should clarify the following argument.

>[!proof]+ Proof of Cantor's theorem.
>
>First, the mapping $x\mapsto\{x\}$ is easily seen to be an injection. Thus $|X|\leq|\mathcal P(X)|$.
>
>Let $f:X\to\mathcal P(X)$ be any function. I prove that $f$ **cannot** be surjective and the conclusion follows. The set
>
>$$
>\{x\in X:x\notin f(x)\}
>$$
>
>is a subset of $X$ and hence an element of $\mathcal P(X)$. Now use the idea behind [[Introduction#Russel's paradox|Russel's paradox]] to prove that this set cannot be in the image of $f$.

