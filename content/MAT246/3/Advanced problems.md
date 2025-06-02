---
title: "3.6. Advanced set theory problems"
draft: false
---
### Functions

Let $A,B$ and $C$ be sets.

>[!thm] Exponent rules for cardinal numbers.
>
>1. Suppose that $B\cap C=\emptyset$. Then, $\left|A^{B\cup C}\right|=\left|A^B\times A^C\right|$.
>2. $\left|\left(A^B\right)^C\right|=\left|A^{B\times C}\right|$.

>[!note] Exercise.
>
>Prove that $\left|A^A\right|\leq\left|\{0,1\}^{A\times A}\right|$.

>[!note] Exercise.
>
>Show that $F^X$ and $\{0,1\}^X$ have the same size whenever $F$ is finite and has at least two elements, and $X$ is an infinite set.

### Countability

>[!note] Exercise.
>
>Suppose that $X$ is countably infinite and that $A$ is finite. Show that $X\setminus A$ is countably infinite.

>[!note] Exercise.
>
>A real number $r$ is _algebraic_ if there is a polynomial $p(x)$ with rational coefficients such that $p(r)=0$. Prove that there are countably many algebraic numbers.

>[!thm] Theorem.
>
>The image, under any function, of a countable set is countable.

>[!note] Exercise.
>
>The collection of all subsets...
>
>1. of a countable set of a fixed finite size, is countable.
>2. of a countable set of any finite size, is countable.
>3. of an infinite set is always uncountable.

### Almost disjointness

>[!def] Definition (Almost disjoint family).
>
>A family of sets $\mathcal F$ is called _pairwise disjoint_ if for all $A,B\in\mathcal F$, $A\neq B$ implies $A\cap B$ is empty.
>
>A family $\mathcal F$ consisting of infinite sets is called _almost disjoint_ if in the above definition you change **empty** to **finite**.

>[!note] Exercise (Any family can be made disjoint).
>
>For any family $\mathcal F$, there is a pairwise disjoint family with the same union as $\mathcal F$.

>[!note] Exercise.
>
>In this exercise we only consider families of subsets of $\mathbb N$.
>
>1. Show that all pairwise disjoint families are countable.
>2. Show that there is an uncountable almost disjoint family.
>3. Any countable almost disjoint family can be extended by adding more subsets.
>
>>[!hint]- Hint.
>>
>>2. For every real number $x$, fix a sequence of rationals $a_k^{(x)}$ that converges to $x$. Enumerate the rationals $q_0,q_1,\dots$ and show that the collection of all sets of the form $A_x:=\{k\in\mathbb N:\exists n\in\mathbb N,\ q_k=a_n^{(x)}\}$ is almost disjoint and has size $|\mathbb R|$.
