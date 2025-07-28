---
title: "3.5. The continuum"
draft: false
---
The size of the set of real numbers, $\mathbb R$ is denoted by $\mathfrak c:=|\mathbb R|$. Cantor's diagonal argument implies that $\aleph_0<\mathfrak c$. In this section I prove the stronger result that $2^{\aleph_0}=\mathfrak c$.

Here is a list of lemmas students proved in class that culminate in the main result of the section. Recall that the _closed interval_ is $[a,b]:=\{x\in\mathbb R:a\leq x\leq b\}$, and the _half-open interval_ $[a,b):=\{x\in\mathbb R:a\leq x<b\}$, and similarly for other types of intervals.

>[!thm] Lemma.
>
>For all reals $a<b$, $|[0,1]|=|[a,b]|$.

>[!thm] Lemma.
>
>$|[0,1]|=|[0,1)|$.

>[!thm] Theorem.
>
>$$
>|\mathbb R|=|\mathcal P(\mathbb N)|
>$$

>[!proof]+ Proof:
>
>Consider $f:[0,1)\to\mathcal P(\mathbb N)$ given by $f(0.a_0a_1\dots a_k\dots):=\{a_k10^k+1:k\in\mathbb N\}$, where the preimage is given by the _decimal expansion_ of the real number without repeating 9's. The rest is left to the reader.

## Exercises

>[!note] Exercises.
>
>Prove that the following sets all have size $\mathfrak c$.
>
>1. The set of infinite binary sequences.
>
>>[!hint]- Hint.
>>
>>The solution is found in these notes.
>
>2. The set of infinite sequences of real numbers.
>3. The _Cantor set_. (Will be formally defined in Topology.)
>4. The subsets of a countably infinite set.
>5. The infinite subsets of a countably infinite set.
>6. The countable subsets of $\mathbb R$.

>[!note] **Hard** exercises.
>
>1. If $A$ is countable and $|B|\leq\mathfrak c$, there are at most $\mathfrak c$-many functions $A\to B$.
>2. The set of _continuous_ functions $\mathbb R\to\mathbb R$ has size $\mathfrak c$, and the set of discontinuous functions $\mathbb R\to\mathbb R$ has size $2^\mathfrak c$.
>3. The product of countably many sets of size $\leq\mathfrak c$ has size $\leq\mathfrak c$.

