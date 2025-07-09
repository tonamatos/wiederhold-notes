---
title: "Midterm solutions"
draft: false
---
1. Use the extended Euclidean algorithm to find integers $s$ and $t$ such that $\gcd(18,40)=18s+40t$. Show every step of the algorithm. What is the value of $\gcd(18,40)$?

**Solution:**

$$
\boxed{\gcd(18,40)=2=9\cdot18+(-4)40}
$$

---

2. Assume that $p$ is a prime number. Prove that $x\cdot x\equiv1\pmod p$ if and only if either $x\equiv1\pmod p$ or $x\equiv-1\pmod p$. Justify every step of the argument.

**Solution:**
$\boxed{\Longrightarrow}$ By definition, $p\mid x^2-1=(x+1)(x-1)$. Since $p$ is prime, by Euclid's lemma, $p\mid x+1$ or $p\mid x-1$. Therefore, $x\equiv_p\pm1$.

$\boxed{\Longleftarrow}$ If $x\equiv_p\pm1$, then $x^2\equiv_p(-1)^2=1$.

---
3. Prove that, for every natural $n$, $2^n+3^n+3$ is divisible by $5$ if and only if $n$ is divisible by $4$.

**Solution 1:**
Let $f(n):=2^n+3^n+3$ and start computing a few examples:

| $n$ | $2^n\pmod 5$ | $3^n\pmod 5$ | $f(n)=2^n+3^n+3\pmod 5$ |
| --- | ------------ | ------------ | ----------------------- |
| 0   | 1            | 1            | 0                       |
| 1   | 2            | 3            | 3                       |
| 2   | -1           | -1           | 1                       |
| 3   | 3            | 2            | 3                       |
| 4   | 1            | 1            | 0                       |

Thus, $2^{k+4}=2^k2^4\equiv_52^k$ and similarly, $3^{k+4}\equiv_53^k$, thus $f(k+4)\equiv_5f(k)$ for all $k$.

Now I prove the statement by strong induction on $n$. The base cases $n=0,1,2,3$ follow from the table above. Suppose that $n\geq4$. Then $f(n)\equiv_5f(n-4)$ is, by inductive hypothesis, congruent to zero if and only if $n$ is divisible by 4.

**Solution 2:**
Let $r$ be the remainder of $n$ divided by $4$. By a corollary of Fermat's little theorem, $k^n\equiv_5k^r$ for $k=2,3$. Therefore, using the same table as above, $f(n)\equiv_50$ if and only if $r=0$ or, in other words, $4\mid n$.

---

4. Argue, without reference to the fundamental theorem of arithmetic, that every integer $n>1$ has a prime divisor.

**Solution 1:**
Let $A:=\{k\in\mathbb N:k\mid n\land k>1\}$. Since $\mid$ is reflexive, $n\in A$. Then by the well-ordering principle, $A$ has a least element $p$. If $p$ were composite, there would be an integer $k$ such that $k\mid p$ and $1<k<p$. Then by minimality, $k\notin A$, so $k$ does not divide $n$. But this contradicts the transitivity of $\mid$.

**Solution 2:**
By strong induction on $n$. Suppose the statement holds for all $k<n$. If $n$ is prime, I am done. Otherwise, there exists an integer $k$ with $1<k<n$. But if $k$ has a prime divisor, so does $n$ by the transitivity of $\mid$.

**Solution 3:**
By weak induction on $d(n)$, the number of positive divisors of $n$. if $d(n)=2$, then $n$ is prime and I am done. Suppose the statements holds for all $n$ with $d(n)=k$ and let $n$ have $k+1$ divisors; let $m>1$ be the least of them. Then $d(n/m)=k$, so $n/m$ has a prime divisor. But then so does $n$ by transitivity.

---
5. Suppose that $g:B\to A$ is a surjective function between two sets $B$ and $A\neq\emptyset$. Give a direct proof that $|A|\leq|B|$.

**Solution with hint:**
By PS1, the relation $\sim:=\{(b,b'):g(b)=g(b')\}$ is an equivalence relation on $B$. Define $f:A\to B/\sim$ given by $f(a):=[g(a)]_\sim=g^{-1}\{a\}$. I claim $f$ is injective. Indeed, if $f(a)=f(a')$, then $g^{-1}\{a\}=g^{-1}\{a'\}$. By surjectivity, this set cannot be empty, so say $b$ belongs to it. Then $a=g(b)=a'$.

Therefore, $|A|\leq|B/\sim|\leq|B|$.

**Solution without hint:**
For every $a\in A$ choose, by surjectivity, $b_a\in g^{-1}\{a\}$. Define $f:A\to B$ by $f(a):=b_a$. I now argue $f$ is injective. Suppose that $f(a)=f(a')$. Then, $b_a=b_{a'}\in g^{-1}\{a\}\cap g^{-1}\{a'\}$, from where $a=g(b_a)=g(b_{a'})=a'$.

Therefore, $|A|\leq|B|$ by definition.

---

6. Write down an explicit injective function from $\mathbb Z\times\mathbb Z\times\mathbb Z$ into $\mathbb N$. Prove the injectivity.

**Solution:**
Let

$$
s(n):=\begin{cases}0&n\geq0\\1&n<0\end{cases}.
$$

Define $f:\mathbb Z\times\mathbb Z\times\mathbb Z\to\mathbb N$ by

$$
f(n,m,\ell):=2^{|n|}\cdot3^{|m|}\cdot5^{|\ell|}\cdot7^{s(n)}\cdot11^{s(m)}\cdot13^{s(\ell)}.$$

Injectivity follows form the fundamental theorem of arithmetic.

---

7. Show that, if $|A|=|B|$ and $X$ is any set, then $|X^A|=|X^B|$.

**Solution:**
Let $\varphi:B\to A$ be a bijection. Define $\Phi:X^A\to X^B$ by $\Phi(f):=f\circ\varphi$. I now argue $\Phi$ is injective. Indeed suppose that $f,g:A\to X$ are such that $\Phi(f)=\Phi(g)$. Let $a\in A$. Then, for $\varphi^{-1}(a)\in B$,

$$
f(a)=f\circ\varphi\circ\varphi^{-1}(a)=\Phi(f)(\varphi^{-1}(a))=\Phi(g)(\varphi^{-1}(a))=g\circ\varphi\circ\varphi^{-1}(a)=g(a).
$$

Hence, $f=g$.

This proves that $|X^A|\leq|X^B|$, but by the symmetry of equinumerosity and the Cantor-Bernstein theorem, this is clearly enough.

---