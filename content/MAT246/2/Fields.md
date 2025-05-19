---
title: "2.6. Fields"
draft: false
---
Informally, a _field_ is an algebraic structure in which all non-zero elements are _invertible_. That is, a structure where multiplication has division. Examples of fields include the rationals, the reals and the complex numbers. Interestingly, it also includes $\mathbb Z_p$ precisely when $p$ is a prime number.

>[!question] Reflect.
>
>Look back at your notes. You should be able to prove that any non-zero element of $\mathbb Z_p$ is invertible just by citing the right things.

>[!warning] Note:
>
>Most of this section is discussed informally and actively (i.e. with a lot of me pointing at things) during the lecture. As such, these notes do not cover said discussion.
## Fermat's little theorem

Let $p$ be a prime number.

>[!thm] Fermat's little theorem.
>
>If $p\not\mid a$, then $a^{p-1}\equiv_p1$.

I prove this by first considering a lemma.

>[!thm] Lemma.
>
>Let $0<a<p$ and $0<i\leq j<p$. If $ia\equiv_pja$, then $i=j$.

>[!proof] Proofs are informally seen in lectures.

>[!abstract] Example.
>
>Say you want to figure out what the number $50^{247}$ is mod $83$. First, divide $247=82\cdot3+1$ and substitute. Then, Fermat's little theorem solves the problem.
>
>$$
>50^{247}=50^{82\cdot3+1}=\left(50^{82}\right)^3\cdot50\equiv1^3\cdot50=50\pmod{83}.
>$$
## A tiny glimpse into more advanced number theory

Prove these as exercises. You need nothing more than what I covered so far.

>[!thm] Modular logarithms.
>
>If $k\equiv\ell\pmod{p-1}$, then $a^k\equiv_pa^\ell$. That is, you can reduce the exponent mod $p-1$ to simplify computations.

>[!thm] Modular inverses.
>
>If $p$ is not $2$, then the inverse of $a\not\equiv_p0$ is $a^{p-2}$.

>[!thm] Modular unit square roots.
>
>If $p$ is not $2$, then $\left(a^{\frac{p-1}2}\right)^2=a^{p-1}\equiv_p1$. That is, $a^{\frac{p-1}2}$ is like the "square root" of $1$ mod $p$.