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

You will need this technical lemma to complete the proof:

>[!thm] Lemma.
>
>For $0<s\leq n$,
>
>$$
>\sum_{\tau\in[n+1]^s}\left|\bigcap_{i\in\tau}A_i\right|=\sum_{\tau\in[n]^s}\left|\bigcap_{i\in\tau}A_i\right|+\sum_{\tau\in[n]^{s-1}}\left|\bigcap_{i\in\tau}A_i\cap A_n\right|.
>$$

>[!proof]+ Proof of lemma:
>
>By associativity and commutativity of the intersection,
>
>$$
>\sum_{\tau\in[n+1]^s}\left|\bigcap_{i\in\tau}A_i\right|=\sum_{\substack{\tau\in[n+1]^s\\n\notin\tau}}\left|\bigcap_{i\in\tau}A_i\right|+\sum_{\substack{\tau\in[n+1]^s\\n\in\tau}}\left|\bigcap_{i\in\tau}A_i\right|
>$$
>
>$$
>=\sum_{\tau\in[n]^s}\left|\bigcap_{i\in\tau}A_i\right|+\sum_{\tau\in[n]^{s-1}}\left|\bigcap_{i\in\tau\cup\{n\}}A_i\right|=\sum_{\tau\in[n]^s}\left|\bigcap_{i\in\tau}A_i\right|+\sum_{\tau\in[n]^{s-1}}\left|\bigcap_{i\in\tau}A_i\cap A_n\right|.
>$$

>[!proof]+ Proof of the inclusion-exclusion principle:
>
>By induction on $n$. The case when $n=1$ is trivial. The case when $n=2$ is the corollary at the beginning of this section.
>
>I will assume the inclusion-exclusion principle holds for any family of finite sets of size $n$. Now let $A_0,\dots,A_n$ be an arbitrary family of $n+1$ finite sets.
>
>On the one hand, expanding the left-hand side and using the inductive hypothesis twice:
>
>$$
>\left|\bigcup_{i\leq n}A_i\right|=\left|\bigcup_{i<n}A_i\right|+|A_n|-\left|\bigcup_{i<n}A_i\cap A_n\right|
>$$
>
>$$
>=\sum_{\emptyset\subsetneq\tau\subseteq n}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\right|+|A_n|-\sum_{\emptyset\subsetneq\tau\subseteq n}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\cap A_n\right|
>$$
>
>On the other hand, expanding the right-hand side by ordering the sum by the size of $\tau$, I apply the lemma above and simplify:
>
>$$
>\sum_{\emptyset\subsetneq\tau\subseteq n+1}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\right|=\sum_{0<s\leq n+1}\sum_{\tau\in[n+1]^s}(-1)^{s+1}\left|\bigcap_{i\in\tau}A_i\right|=\sum_{0<s\leq n+1}\left((-1)^{s+1}\sum_{\tau\in[n+1]^s}\left|\bigcap_{i\in\tau}A_i\right|\right)
>$$
>
>$$
>=\sum_{0<s\leq n+1}\left((-1)^{s+1}\sum_{\tau\in[n]^s}\left|\bigcap_{i\in\tau}A_i\right|-(-1)^s\sum_{\tau\in[n]^{s-1}}\left|\bigcap_{i\in\tau}A_i\cap A_n\right|\right)
>$$
>
>$$
>=\sum_{0<s\leq n+1}\left(\sum_{\tau\in[n]^s}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\right|-\sum_{\tau\in[n]^{s-1}}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\cap A_n\right|\right)
>$$
>
>$$
>=\sum_{0<s\leq n+1}\sum_{\tau\in[n]^s}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\right|-\sum_{0<s\leq n+1}\sum_{\tau\in[n]^{s-1}}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\cap A_n\right|
>$$
>
>The first double sum is just
>
>$$
>\sum_{\emptyset\subsetneq\tau\subseteq n}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\right|;
>$$
>
>and the latter double sum, the indexing goes from $\tau\in[n]^0=\{\emptyset\}$ to $\tau\in[n]^n=\{n\}$. When $\tau=\emptyset$, the intersection is just $A_n$; therefore the second double sum may be rewritten as
>
>$$
>\sum_{\emptyset\subsetneq\tau\subseteq n}(-1)^{|\tau|+1}\left|\bigcap_{i\in\tau}A_i\cap A_n\right|-|A_n|.
>$$
>
>Combining both, I see that they are equal, hence the theorem is proved.

>[!hint]- Alternative proof.
>
>Let $B_i:=A_i\setminus A_n$ for $i<n$ and notice that $\bigcup_{i\leq n}A_i=\bigcup_{i<n}B_i\cup A_n$ which is a disjoint union and thus $\left|\bigcup_{i\leq n}A_i\right|=\left|\bigcup_{i<n}B_i\right|+|A_n|$. Moreover,
>
>$$
>\bigcap_{i\in\tau}B_i=\bigcap_{i\in\tau}A_i\setminus\bigcap_{i\in\tau}(A_i\cap A_n).
>$$
>
>>[!note] Exercise.
>>
>>Complete the proof.


For example, for three sets, we have $n=\{0,1,2\}$, so the right-hand sum iterates over three singletons, three complements of singletons and $n$ (there are seven nonempty subsets of $n$ in this case). Therefore,

$$
|A_0\cup A_1\cup A_2|=|A_0|+|A_1|+|A_2|-|A_0\cap A_1|-|A_0\cap A_2|-|A_1\cap A_2|+|A_0\cap A_1\cap A_2|.
$$

Just as a sanity check, I write the following "obvious" fact, which can be of course proved using much simpler methods.

>[!thm] Corollary.
>
>Assume, in addition to the hypotheses of the inclusion-exclusion principle, that the sets are pairwise disjoint. Then,
>
>$$
>\left|\bigcup_{i<n}A_i\right|=\sum_{k<n}|A_i|.
>$$

>[!proof]+ Proof:
>
>If the sets are pairwise disjoint, all intersections of two or more are empty. Therefore, only the cases when $\tau$ are singleton sets contribute to the sum, which simplifies to the above.
### Application: Euler's totient function

Let $\varphi(n)$ denote the number of invertible elements of $\mathbb Z_n$. In Chapter 2, I proved that an integer $k$ is invertible mod $n$ if and only if $k\perp n$. I will show you a formula for computing $\varphi(n)$ when the prime factorization of $n$ is known.

Suppose that $n=\prod_{i=1}^rp_i^{\alpha_i}$ where the $p_i$ are distinct primes and $\alpha\geq1$. Therefore, $k\perp n$ if and only if no $p_i$ divides $k$. Let $A_i$ be the set of integers $\leq n$ that are divisible by $p_i$. The union of all the $A_i$ is thus precisely the set of elements of $\mathbb Z_n$ that are **not** invertible.

For each $i$, $A_i$ consists of the multiple of $p_i$, of which there are $n/p_i$. Similarly, for any prime factors of $n$, $p_{i_1},\dots,p_{i_q}$, there are $n/p_{i_1}\cdots p_{i_q}$ many integers that share that prime factor. By the inclusion-exclusion principle, the number of integers $\leq n$ that share no prime factors with $n$ is

$$
\varphi(n)=n-\sum_{p\mid n}\frac np+\sum_{p<q}\frac n{pq}\pm\cdots=n\prod_{p\mid n}\left(1-\frac 1p\right).
$$

### Application: derangements

In many situations, the above formula may be simplified. One such example is when the summand $\left|\bigcap_{i\in\tau}A_i\right|$ depends only on the size of $\tau$ (and not the particular elements of $\tau$).

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

A _derangement_ is a permutation with no fixed points. That is, let $\varphi\in\Phi_X$ be a bijection $X\to X$. Then $\varphi$ is called a _derangement_ if for all $x\in X$, $\varphi(x)\neq x$. How many of the $|X|!$ permutations are derangements? I will denote the number of derangements of a set of size $n$ by $!n$. Thus obviously $!n\leq n!$.

>[!note] Exercise.
>
>Show that $!n=(n-1)(!(n-1)+!(n-2))$ by using a combinatorial argument, that is, without using the formula below.

>[!thm] Derangement formula.
>
>$$
>!n=\sum_{k=0}^n\frac{(-1)^k\ n!}{k!}.
>$$

From Calculus, I know that the McLaurin series of the exponential function gives me

$$
e^x=\sum_{k=0}^\infty\frac{x^k}{k!},
$$

and thus $1/e\approx0.37$ is a good approximation of the probability that a random permutation of $n$ objects, for large $n$, is a derangement. This limit converges rather quickly, and so with high probability, a random shuffle of cards will leave at least one card in the same place, for instance.

>[!note] Exercise.
>
>Show that $n!=\sum_{k=0}^n{n\choose k}!k$ and give a combinatorial interpretation of it.

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