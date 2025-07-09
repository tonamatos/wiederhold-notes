---
title: "4.1. Enumeration"
draft: false
---
I use the following convention throughout this chapter: for $n$, a natural number, $n=\{0,1,\dots,n-1\}$ when $n>0$, and $0=\emptyset$.

Previously in this course, it was established that there are exactly $n^k$ functions from any set of size $k$ to any set of size $n$. Let me show you an example. Consider the following set of distinct objects.

$$
X=\{A,B,C,D\}
$$
In how many ways can you choose **two** objects from $X$? I have to be more specific. For example, are you allowed to grab the same element twice, e.g. $AA$? Am I distinguishing $AB$ from $BA$?

In general, without further specification, there are $|X^2|=|X|^2=4^2=16$ ways to make a selection. But maybe not all of them are relevant for your purposes.

|     |        |        |        |
| --- | ------ | ------ | ------ |
| AA  | **AB** | **AC** | **AD** |
| BA  | BB     | **BC** | **BD** |
| CA  | CB     | CC     | **CD** |
| DA  | DB     | DC     | DD     |
The diagonal $AA,BB,CC,DD$ contains the repeated elements. The **highlighted** selections consist of those where order is not distinguished and repetitions are not counted. In this example, there are $\frac{12}2=6$ such selections.

>[!def] Definition.
>
>Denote by $PR_k^n$ the number of choices of $k$ elements from a set of size $n$ with repetitions and with order.
>
>Denote by $P_k^n$ the number of choices of $k$ elements from a set of size $n$ with no repetitions and with order.

Based in my previous discussion, $PR_k^n=n^k$.

>[!thm] Theorem.
>
>For $k\leq n$,
>
>$$
>P_k^n=\frac{n!}{(n-k)!}
>$$

>[!proof]+ Informal proof:
>
>Proceed by induction on $n$. The base case $n=0$ is clear since $0!=1$.
>
>The inductive step follows from the observation that $P_k^n=n\cdot P_{k-1}^{n-1}$. Indeed, for every choice counted by the left hand size, I can fix the first element which has $n$ possible values. The remaining elements are chosen from a set of size $n-1$ (since there is no repetition) and there are $k-1$ of them. Thus the product of $n$ and this other amount gives me the total number of possible choices.

>[!warning] Note:
>
>Formalize the above proof using a bijection between the permutations of $n$ and a set of size $P_k^n(n-k)!$. An example of such a proof is seen below and you are expected to know how to write these types of formal proofs.

>[!thm] Corollary.
>
>There are $P_n^n=n!$ bijections from any set of size $n$ to itself. These are called _permutations_.

## Combinations

Let $X$ be a set and $\lambda$ a cardinal (usually a natural number). I will denote by $[X]^\lambda$ the collection of subsets of $X$ of size exactly $\lambda$. That is, $[X]^\lambda:=\{A\subseteq X:|A|=\lambda\}$.

>[!def] Definition.
>
>The number of subsets of a given size is read as "$n$ choose $k$" and denoted as follows.
>
>$$
>{n\choose k}:=\left|[n]^k\right|
>$$

>[!abstract] Examples.
>
>1. ${n\choose n}=|\{n\}|=1$
>2. ${n\choose 0}=|\{\emptyset\}|=1$
>3. when $k>n$, ${n\choose k}=0$
>4. ${n\choose 1}=|\{\{k\}:k<n\}|=n$
>5. ${n\choose n-1}=|\{n\setminus\{k\}:k<n\}|=n$

You are expected to know how to prove the following exercises from the definition, **not** from the formula, which prove afterwards.

>[!note] Exercise.
>
>Prove that for $k\leq n$, ${n\choose n-k}={n\choose k}$.

>[!note] Exercise.
>
>$$
>\sum_{k=0}^n{n\choose k}=2^n
>$$

>[!thm] Combinations formula.
>
>Assume $k\leq n$.
>
>$$
>{n\choose k}=\frac{n!}{k!(n-k)!}
>$$

>[!proof]+ Proof:
>
>For every $A\in[n]^k$, let $\Phi_A$ be the set of all permutations on $A$. For simplicity, let me write $A=\{a_1,\dots,a_k\}$. By definition, the set
>
>$$
>\beth:=\{(\varphi(a_1),\dots,\varphi(a_k)):\varphi\in\Phi_A,\ A\in[n]^k\}
>$$
>
>has size $P_k^n$. It is straightforward to show that, for any fixed $A$ (since they all have the same size), $|\beth|=|[n]^k|\cdot|\Phi_A|={n\choose k}k!$. The result follows.

>[!question] Reflect.
>
>It isn't even immediately obvious that the right-most expression above is an **integer** to begin with. This is proved in Tutorial 3.