---
title: "5.2. Compactness"
draft: false
---
In this section, you can substitute $\mathbb R^n$ for a metric space $(X,d)$ (or even a _topological space_ in most cases). For ease of notation, I will denote the topology of $\mathbb R^n$ by the letter $\tau$.

Recall the most important property about the real numbers. Given a set $E\subseteq\mathbb R$, I say that the real $r$ is an _upper bound_ of $E$ if for all $e\in E$, $e\leq r$. If $E$ has a least upper bound, I call that $\sup E$. The completeness axiom states that any nonempty set of reals with an upper bound has a **least** upper bound:

>[!thm] Supremum axiom ("$\mathbb R$ is a _complete_ metric space").
>
>Every nonempty upper bounded set of reals has a least upper bound (called the _supremum_).

>[!note] Exercise.
>
>Suppose that $a=\sup A$. Prove that $a\in\overline A$.

## Open covers

>[!def] Definition.
>
>Let $A\subseteq\mathbb R^n$.
>
>1. I say that $A$ is _bounded_ if it is contained in some open ball. I say $A$ is _unbounded_ otherwise.
>2. An _open cover of $A$_ is a family $\mathcal O\subseteq\tau$ such that $A\subseteq\bigcup\mathcal O$.
>3. Given an open cover $\mathcal O$ of $A$, a _subcover_ is just a set $\mathcal S\subseteq\mathcal O$ that is also an open cover of $A$.

>[!abstract] Examples.
>
>1. Any open ball is bounded.
>2. Any finite set is bounded.
>3. There are uncountable bounded sets.
>4. There are countably infinite unbounded sets.
>5. The _Archimedean principle_ mentioned in the last section says that $\mathbb N$ is unbounded in $\mathbb R$.
>6. If $F$ is a finite set, then $\{B(f,1):f\in F\}$ is a finite open cover of $F$.
>7. The finite union of open balls is bounded.
>8. The finite union of bounded sets is bounded.
>9. If $A$ is bounded, then $\mathbb R^n\setminus A$ is unbounded.
>10. There are unbounded sets with unbounded complements.
>11. $\mathcal O:=\{B(\vec0,r):r\in\mathbb R, r>0\}$ is an open cover of any set and $\mathcal S:=\{B(\vec0,n):n\in\mathbb N\}$ is a countable subcover of $\mathcal O$.
>12. $\mathcal O:=\{B(\vec x,2):\vec x\in\mathbb R^n\}$ is an open cover of any set and $\mathcal S:=\{B(\vec x,2):\vec x\in\mathbb N^n\}$ is a countable subcover of $\mathcal O$.
>13. If $\mathcal A$ and $\mathcal B$ are open covers of $A$ and $B$ respectively, then $\mathcal A\cup\mathcal B$ is an open cover of $A\cup B$. $\{x\cup y:x\in\mathcal A,y\in\mathcal B\}$ is also an open cover of $A\cup B$.

>[!note] Exercise.
>
>Fill in the details for the examples above you do not find obvious.
## Compact sets

>[!def] Definition.
>
>A set $K\subseteq\mathbb R^n$ is called _compact_ if every open cover of $K$ has a finite subcover.

>[!abstract] Examples.
>
>1. The cover $\mathcal O$ in either 11 or 12 from above are open covers of $\mathbb R^n$ without any finite subcovers. Therefore, $\mathbb R^n$ is not compact.
>2. Any finite set $F$ is compact.
>3. The finite union of compact sets is compact.

I need to give a much simpler characterization of compactness in $\mathbb R$ before I can provide more interesting examples. The following lemmas have this goal.

>[!thm] Lemma.
>
>Compact sets are always closed and bounded.

>[!proof]+ Proof:
>
>Let $K$ be a compact set.
>
>**Closed:** I show that $\mathbb R^n\setminus K$ is open. Let $x\in\mathbb R^n\setminus K$. For every $y\in K$, since obviously $x\neq y$, by the Hausdorff separation property I can find disjoint open sets $U_y$ and $V_y$ such that $x\in U_y$ and $y\in V_y$. Notice that $\{V_y:y\in K\}$ is an open cover of $K$, so by compactness, there is a finite set $F\subseteq K$ such that $\{V_y:y\in F\}$ is also an open cover.
>
>>[!note] Exercise.
>>
>>Show that $U:=\bigcap_{y\in F}U_y$ is an open set satisfying
>>
>>$$
>>x\in U\subseteq\mathbb R^n\setminus K.
>>$$
>
>Since $U$ is open, there exists $r>0$ with $x\in B(x,r)\subseteq U$. But by the above containment, this proves that $\mathbb R^n\setminus K$ is open, and thus that $K$ is closed.
>
>**Bounded:** Take the open cover $\mathcal S$ from 11 above. $\mathcal S$ is an open cover of $K$, thus if $K$ is compact, there must be a finite subcover. In other words, there exists a finite nonempty set of naturals $F$, such that $\{B(\vec 0,n):n\in F\}$ is an open cover of $K$. Let $N$ be the largest element of $F$ and notice that $K\subseteq B(\vec 0,N)$. Thus, $K$ is bounded.

>[!thm] Lemma.
>
>Closed subsets of compact sets are compact.

>[!proof]+ Proof:
>
>Let $C$ be a closed subset of a compact set $K$ and let $\mathcal O$ be an open cover of $C$. It follows that $\mathcal O\cup\{\mathbb R^n\setminus C\}$ is an open cover of $K$. Thus, by compactness, there are $U_1,\dots,U_n\in\mathcal O$ such that
>
>$$
>C\subseteq K\subseteq\bigcup_{i=1}^n U_i\cup\mathbb R^n\setminus C.
>$$
>
>Finally, $\{U_1,\dots,U_n\}$ is a finite open cover of $C$, proving $C$ is compact.

Now I can provide the first non-trivial example of a compact set.

>[!thm] Theorem.
>
>The closed interval $[0,1]$ is a compact subset of $\mathbb R$.

![intervals|300](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7c/Compact.svg/800px-Compact.svg.png)

The proof is trickier than you might think. Luckily, once we know this, almost all compact sets of reals are easy to describe.

>[!proof]+ Proof:
>
>Let $\mathcal O$ be an open cover of $[0,1]$ and define
>
>$$
>E:=\{x\in[0,1]:[0,x]\text{ can be covered by finitely many elements of }\mathcal O\}.
>$$
>
>Note that $0\in E$ and that $E$ is bounded, so it must have a supremum $c$.
>
>>[!note] Exercise.
>>
>>Prove that $c=1$.
>
>Then, by the definition of $E$, $[0,1]$ is compact.

Substituting $0$ and $1$ for arbitrary reals $a$ and $b$ above yields that all closed intervals of the form $[a,b]$ are compact. I only prove the next theorem for $\mathbb R$ even though it also holds in higher dimensions. Interestingly, the proofs are not the same however, and the general case is out of scope of this course.

>[!thm] Heine-Borel theorem.
>
>A set of reals is compact if and only if it is closed and bounded.

>[!proof]+ Proof:
>
>$\boxed\Longrightarrow$ is one of the above lemmas.
>
>$\boxed\Longleftarrow$ Suppose that $C$ is a closed and bounded subset of $\mathbb R$. Then clearly one can find an open ball containing $C$. In particular, $C$ is a closed subset of some closed interval $[a,b]$. By the other lemma and the theorem succeeding it, $C$ is a closed subset of a compact set and thus compact as well.

## The nested set theorem

Arguably the most interesting property about compact sets of reals is the following result. Again, I only do this for $\mathbb R$ even though it holds in much more generality.

>[!thm] Nested set theorem.
>
>Let $\{K_n\}_n$ be a family of nonempty compact sets of reals such that $K_0\supseteq K_1\supseteq\cdots\supseteq K_n\supseteq\cdots$ (that is, the sets are _nested_). Then,
>
>$$
>\bigcap_{n\in\mathbb N}K_n\neq\emptyset.
>$$

>[!proof]+ Proof:
>
>By contradiction, assume that the hypotheses hold but that the intersection is empty. Then,
>
>>[!note] Exercise.
>>
>>$\{\mathbb R\setminus K_n:n\in\mathbb N\}$ is an open cover of $K_0$.
>
>By compactness, there is a nonempty finite $F\subseteq\mathbb N$ such that $\{\mathbb R\setminus K_n:n\in F\}$ is an open cover of $K_0$. By the hypothesis that the compact sets are all nested, if I let $m:=\min F$, then $K_m\subseteq K_n\subseteq K_0$ for all $n\in F$.
>
>But being a subcover, $K_0\subseteq\mathbb R\setminus K_m$, which can only happen if the compact sets are all empty. This is a contradiction.

### An application: Google maps inside of Google maps

Go to Google maps on your phone and look up any place that contains the location of the device, say Toronto or North America. So, every point on your screen corresponds to some point on Earth. I claim that there is exactly one point where they match. That is, there is exactly one point on the screen that corresponds to itself in space. This works even if your screen isn't flat or laid out horizontally; you can print out the map as a huge billboard and crumble it up or stretch it and the statement still holds. Let me prove this to you.

Start with any point $x_0$ in space, for instance, you can pick your own location. Now look at the position of $x_0$ on the map, call this point in space $x_1$. If you chose your own location, then these will not match unless you are standing right on top of your own location on the map. Next, zoom into the map until you find the location of the map within the map. In the map inside the map, draw out the location of $x_1$ and call this point in space $x_2$. Again, these could be different points in space. Now repeat these steps to find $x_3$, the point in space corresponding to the point $x_2$ in the map inside the map, but now in the map inside the map inside the map. If can keep going forever without ever finding a point that maps to itself. But the **limit** of the sequence must map to itself. Let me formalize this a bit more since the map analogy can only take me so far.

Suppose that $f:\mathbb R^n\to\mathbb R^n$ is any function such that for all $x,y$, $d(f(x),f(y))<\lambda d(x,y)$, for some $0\leq\lambda<1$. For example, $f$ is the function that takes the city of Toronto and draws a map of it inside Toronto, and $\lambda$ is the scaling factor (so all I ask is for the map to be smaller than the real life location). The goal is to prove that there is a unique point $x^*$ such that $f(x^*)=x^*$. Intuitively, the paragraph above describes the construction as $x^*:=f(f(\cdots f(x_0)\cdots))$. After applying the map $f$ (_map_, get it?) infinitely many times, applying it once more makes no difference. Hence $x^*$ is _fixed_. But this is all very informal; I don't even know if this limit exists.

>[!proof]+ Proof idea:
>
>Pick any point $x_0\in\mathbb R^n$ and define $x_{n+1}:=f(x_n)$ recursively. Consider $K_n:=\overline{B(x_n,\lambda^n\frac{d(x_1,x_0)}{1-\lambda})}$ and observe that the sets $K_n$ have the following properties:
>
>**Compact nonempty.** This follows from Heine-Borel as the closure of a ball is a bounded closed set that contains its center.
>
>**Nested.** 
>
>Therefore, by the nested set theorem, there is a point $x^*$ such that for all $n$, $j$

>[!note] **Hard** exercise.
>
>Complete the proof. The calculations are easier to write if you assume that $\lambda=\frac12$.

>This was an informal discussion of the Banach fixed-point theorem, and it has concrete uses ranging from reinforcement learning to economics.

### Another application: Baire category theory

>[!info] Proving this was a question in last year's MAT246 final.

Recall that a set $E\subseteq\mathbb R$ is _dense_ if for every $x$ and every $r>0$, $E\cap(x-r,x+r)\neq\emptyset$. Let $\{U_n:n\in\mathbb N\}$ be a family of open dense subsets of $\mathbb R$. Let $W$ be an open bounded interval.

1. Prove that there exist $r_0>0$ and $x_0\in\mathbb R$ such that the closed interval $[x_0-r_0,x_0+r_0]$ is contained in  $W\cap U_0$.
2. Construct sequences $r_n$ and $x_n\in\mathbb R$ such that for all $n$, $0<r_n$ and $[x_{n+1}-r_{n+1},x_{n+1}+r_{n+1}]\subseteq[x_n-r_n,x_n+r_n]\cap U_n$.
3. Use the nested set theorem to conclude that some real number $x$ satisfies $x\in W\cap U_n$ for all $n$.
4. Conclude that $\bigcap_{n\in\mathbb N}U_n$ is dense.

>[!thm] Baire category theorem.
>
>The intersection of countably many open dense sets of reals is dense in $\mathbb R$.
## Sequential compactness

Recall that a sequence in $\mathbb R^n$ is just a function $s:\mathbb N\to\mathbb R^n$.

>[!def] Definition of subsequence.
>
>Given a sequence $s$ and any strictly increasing function $i:\mathbb N\to\mathbb N$, I call $s\circ i$ a _subsequence_ of $i$.

For an informal example, consider the sequence $s$ be $0,1,2,3,4,\dots$. A subsequence could be $0,2,4,6,\dots$ or $0,1,2,8,9,\dots$. The sequence $1,0,2,3,4,\dots$ is **not** a subsequence of $s$.

A classic fact from Calculus, which you should attempt to prove from the definition of limit if you don't know how is as follows.

>[!thm] Proposition.
>
>All subsequences of a convergent sequence converge to the same limit.

In particular, a sequence is convergent if and only if all of its subsequences converge.

>[!info] Remark.
>
>There are divergent sequences with convergent subsequences. An example is $(-1)^n$, which is a bounded and divergent sequence, but the even-indexed terms converge to $1$.

Another result you are probably familiar with is below.

>[!thm] Proposition.
>
>Convergent sequences are bounded.

For me, a _bounded_ sequence is just one that is bounded as a set. That is, the sequence $s$ is bounded if its image forms a bounded subset of reals. I am now ready to prove the main result that connects compactness with sequences.

>[!thm] Bolzano-Weierstrass theorem.
>
>Every bounded sequence has a convergent subsequence.

>[!thm] Theorem ("in $\mathbb R^n$, sequential compactness is the same as compactness").
>
>Let $K\subseteq\mathbb R$. Then $K$ is compact if and only if every sequence $\{x_n\}_n\subseteq K$ has a subsequence that converges **in $K$**.

>[!proof]+ Proof:
>
>$\boxed\Longrightarrow$ Let $K$ be compact and $\{x_n\}_n$ a sequence in $K$. So, $K$ is bounded and closed. Since it's bounded, it has a convergent subsequence; and since it's closed, the limit must be in $K$.
>
>$\boxed\Longleftarrow$ By Heine-Borel, it is sufficient to show two things:
>
>**$K$ is closed:** Let $x\in\overline K$. By the sequential closure theorem, $x$ is the limit of a sequence in $K$, which by hypothesis has a subsequence that converges in $K$. But said subsequence must also converge to $x$, thus necessarily $x\in K$. This shows that $\overline K\subseteq K$.
>
>**$K$ is bounded:** By contrapositive, if it weren't, then for every $n\in\mathbb N$, $B(\vec0,n)$ witnesses this fact and so there exists $x_n\in K\setminus B(\vec0,n)$.
>
>>[!note] Exercise.
>>
>>Show that every subsequence of $\{x_n\}_n$ diverges.