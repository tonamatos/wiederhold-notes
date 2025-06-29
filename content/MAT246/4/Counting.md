---
title: "4.3. Counting principles"
draft: false
---
In the tutorials, it was argued that for any two finite sets $A$ and $B$, $|A\cup B|\leq|A|+|B|$ and equality holds if the sets are disjoint. Can I say something stronger in the general case?

All sets are assumed to be finite in the section.

>[!thm] Proposition.
>
>If $A\subseteq B$, then $|B\setminus A|=|B|-|A|$.

>[!proof]+ Proof:
>
>Obviously $A$ and $B\setminus A$ are disjoint sets, so by the result from the tutorials, $|B|=|B\setminus A|+|A|$. Using that $A\subseteq B$, I get $|A|\leq|B|$ and so the result follows.

## The inclusion-exclusion principle

>[!thm] Corollary.
>
>For any sets $A$ and $B$,
>
>$$
>|A\cup B|=|A|+|B|-|A\cap B|.
>$$

>[!proof]+ Proof:
>
>By the proposition,
>
>$$
>|A\cup B|=|A\setminus(A\cap B)\quad\cup\quad B\setminus(A\cap B)\quad\cup\quad A\cap B|
>$$
>
>$$
>=|A|-|A\cap B|+|B|-|A\cap B|+|A\cap B|=|A|+|B|-|A\cap B|
>$$

>[!thm] Inclusion-exclusion principle.
>
>For any finite family of finite sets $A_0,A_1,\dots,A_{n-1}$,
>
>$$
>\left|\bigcup_{i<n}A_i\right|=\sum_{\emptyset\subsetneq\tau\subseteq n}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\right|.
>$$

>[!proof]- Proof:
>
>>[!fail] Removed during quiz.

For example, for three sets, we have $n=\{0,1,2\}$, so the right-hand sum iterates over three singletons, three complements of singletons and $n$ (there are seven nonempty subsets of $n$ in this case). Therefore,

$$
|A_0\cup A_1\cup A_2|=|A_0|+|A_1|+|A_2|-|A_0\cap A_1|-|A_0\cap A_2|-|A_1\cap A_2|+|A_0\cap A_1\cap A_2|.
$$

### Application: Euler's totient function

Let $\varphi(n)$ denote the number of invertible elements of $\mathbb Z_n$. In Chapter 2, I proved that an integer $k$ is invertible mod $n$ if and only if $k\perp n$. I will show you a formula for computing $\varphi(n)$ when the prime factorization of $n$ is known.

Suppose that $n=\prod_{i=1}^rp_i^{\alpha_i}$ where the $p_i$ are distinct primes and $\alpha\geq1$. Therefore, $k\perp n$ if and only if no $p_i$ divides $k$. Let $A_i$ be the set of integers $\leq n$ that are divisible by $p_i$. The union of all the $A_i$ is thus precisely the set of elements of $\mathbb Z_n$ that are **not** invertible.

For each $i$, $A_i$ consists of the multiple of $p_i$, of which there are $n/p_i$. Similarly, for any prime factors of $n$, $p_{i_1},\dots,p_{i_q}$, there are $n/p_{i_1}\cdots p_{i_q}$ many integers that share that prime factor. By the inclusion-exclusion principle, the number of integers $\leq n$ that share no prime factors with $n$ is

$$
\varphi(n)=n-\sum_{p\mid n}\frac np+\sum_{p<q}\frac n{pq}\pm\cdots=n\prod_{p\mid n}\left(1-\frac 1p\right).
$$

### Application: derangements

In many situation, the above formula may be simplified. One such example is when the summand $\left|\bigcap_{i\in\tau}A_i\right|$ depends only on the size of $\tau$ (and not the particular elements of $\tau$).

>[!thm] Corollary.
>
>Add to the hypotheses of the inclusion-exclusion principle the condition that there is a function $\omega$ such that $\left|\bigcap_{i\in\tau}A_i\right|=\omega(|\tau|)$ for all $\tau$. Then,
>
>$$
>\left|\bigcup_{i<n}A_i\right|=\sum_{k=1}^n(-1)^{k+1}{n\choose k}\omega(k).
>$$

>[!proof]+ Proof:
>
>By the inclusion-exclusion principle, it is sufficient to notice that
>
>$$
>\sum_{\emptyset\subsetneq\tau\subseteq n}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\right|=\sum_{\emptyset\subsetneq\tau\subseteq n}(-1)^{|\tau|+1}\omega(|\tau|)=\sum_{k=1}^n\sum_{\tau\in[n]^k}(-1)^{|\tau|+1}\omega(|\tau|)
>$$
>
>$$
>=\sum_{k=1}^n\sum_{\tau\in[n]^k}(-1)^{k+1}\omega(k)=\sum_{k=1}^n(-1)^{k+1}{n\choose k}\omega(k).
>$$

A _derangement_ is a permutation where no fixed points. That is, let $\varphi\in\Phi_X$ be a bijection $X\to X$. Then $\varphi$ is called a _derangement_ if for all $x\in X$, $\varphi(x)\neq x$. How many of the $|X|!$ permutations are derangements?

>[!info] To be added depending on progress.

## The stars and bars theorem

Suppose I have $k$ bins and $n$ indistinguishable objects to put in them. If bins can be left empty, in how many ways can I place the objects in the bins?

The correct way to think about this problem is to ignore the bins and instead picture the bars $k-1$ **separating** the bins. As an example, here I placed an object in the first bin, left the second bin empty, three objects in the third bin, and so on.

$$
\star\ |\ |\ \star\star\star\ |\ \star\ |\ \star\ |
$$
Interchanging two stars makes no difference and I consider the arrangement the same (that's what the object being _indistinguishable_ means). There are two ways of counting the number of such arrangements. First, notice I have $n$ stars and $k-1$ bars for a total of $n+k-1$ symbols being permuted. The stars and bars are indistinguishable among themselves, so I must divide by each permutation of the two groups. In total, there are

$$
\frac{(n+k-1)!}{n!(k-1)!}
$$

star and bars arrangements. Alternatively, I can think of this as selecting, from a set of $n+k-1$ symbols, those that will be drawn as bars, or those that will be drawn as stars. In other words, respectively,

$$
{n+k-1\choose k-1}\qquad{n+k-1\choose n}
$$

Of course, all of these numbers are equal.

### Application: Number of Diophantine solutions

How many positive integers solve the equation

$$
x_1+x_2+\dots+x_{246}=2025?
$$

What about non-negative solutions?