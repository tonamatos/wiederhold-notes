---
title: "2.4. Fundamental theorem"
draft: false
---
I will present to you a more modern treatment of this very old theorem than what you are likely to find in textbooks. I need some basic notation for this.

>[!def] Notation.
>
>1. $\sum_{i=1}^n\alpha_i:=\alpha_1+\cdots+\alpha_n$. (_Summation_)
>2. $\prod_{i=1}^n\alpha_i:=\alpha_1\cdots\alpha_n$ (_Product_)
>
>If $S$ is a **finite** set of integers, $\sum_{x\in S}x$ is the sum over all elements of $S$. The product is defined the same way. In the case when $S=\emptyset$, I define $\sum_{x\in\emptyset}=0$ (the additive identity) and $\prod_{x\in\emptyset}=1$ (the multiplicative identity).

## Multiplicity

>[!def] Definition.
>
>Given a positive integer $a$ and a prime $p$, the _multiplicity of $a$ with respect to $p$_, in symbols, $\operatorname{mult}_p(a)$, is the largest integer $k$ such that $p^k\mid a$.

>[!question] Reflect.
>
>Why does the multiplicity exist? In other words, is it clear to you that the aforementioned set always has a largest element?

>[!abstract] Examples.
>
>|$p$|$a$|$\operatorname{mult}_p(a)$|
>| --- | --- | --- |
>|$2$|$4$|$2$|
>|$2$|$6$|$1$|
>|$3$|$6$|$1$|
>|$5$|$7$|$0$|

## The fundamental theorems

>[!thm] Old fundamental theorem of arithmetic.
>
>Every positive integer is the product of primes. This product is unique up to permutations.

I will give a precise definition of the word _permutation_ in a later chapter. For now, it just means that the order of the primes with positive multiplicity might change and yet I do not consider them different products. The examples below illustrate this idea.

>[!question] Reflect.
>
>Most textbooks state the theorem by adding "every integer **bigger than 1**." Did I make a typo above?

Here is my preferred way of stating the main result of this section.

>[!thm] Fundamental theorem of arithmetic (FTA).
>
>For any $n>0$,
>
>$$
>n=\prod_{p\text{ prime}}p^{\operatorname{mult}_p(n)}.
>$$

>[!question] Reflect.
>
>I have not (and will not, in this course) defined the concept of an _infinite_ product. There are infinitely many primes, so how is the above well-defined?

A crucial observation is that in the above product, primes with zero multiplicity do not contribute to the product (since they add a factor of $1$), so I only ever need to consider the primes with positive multiplicity, of which there could be none as in the first example below.

>[!abstract] Examples.
>
>1. $1=\prod_{p\in\emptyset}$ (empty product)
>2. $7=7$ (product with a single factor, a prime)
>3. $14=2\cdot7$ (product with two different primes)
>4. $9=3^2$ (product with one prime but of higher multiplicity)

### Proof of the fundamental theorems

I divide the proof of the fundamental theorem into its two basic components.

>[!thm] Lemma (**Existence** part of FTA).
>
>Every integer bigger than 1 is the product of primes.

>[!thm] Lemma (**Uniqueness** part of FTA).
>
>Two products of primes are equal only if the factors are permutations of each other. (In other words, the set of primes are the same.)

>[!question] Reflect.
>
>How do the two lemmas actually prove FTA?

>[!proof] Proof of **Existence**:
>
>Suppose that the lemma fails. Then, by the [[Induction#The well-ordering principle|well-ordering principle]], there must exist a least counterexample $n>1$. That is, $n$ is **not** the product of primes. Obviously, $n$ itself cannot be prime, so there exist two integers $a$ and $b$ such that $1<a,b<n$ and $ab=n$. By minimality (this word is defined in [[Induction]]), both $a$ and $b$ are products of primes. But then, $n=ab$ must also be a product of primes. This contradiction proves the lemma.

>[!proof] Sketch of proof of **Uniqueness**:
>
>>[!warning] Note:
>>
>>This proof follows an informal discussion given in class. It is inadequate for these notes.

---

The GCD and LCM can be computed in terms of the multiplicities.

>[!note] **Hard** exercise.
>
>Let $\{a_1,\dots,a_n\}\neq\{0\}$. Then,
>
>$$
>\gcd(a_1,\dots,a_n)=\prod_{p\text{ prime}}p^{\min\{\operatorname{mult}_p(a_i)\ :\ 0<i\leq n\}};
>$$
>
>and
>
>$$
>\operatorname{lcm}(a_1,\dots,a_n)=\prod_{p\text{ prime}}p^{\max\{\operatorname{mult}_p(a_i)\ :\ 0<i\leq n\}}.
>$$

>[!note] Exercise.
>
>Use the above to show that for any integers not both zero $a$ and $b$,
>
>$$
>\gcd(a,b)\operatorname{lcm}(a,b)=ab.
>$$
>
>**Hard:** give a proof directly from the definition, that is, without using the above formulas.
