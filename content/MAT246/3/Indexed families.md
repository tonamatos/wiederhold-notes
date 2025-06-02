---
title: "3.3. Indexed families of sets"
draft: false
---
This section is meant to be used as a reference, rather than as lecture content. You may cite results from here for your problem sets or tests, but it is not expected you know all of this specifically.

## Union and intersection

>[!def] Notation.
>
>Let $X$ be a set.
>The _union_ of $X$, denoted $\bigcup X$ is the set
>
>$$
>\{x:\exists A\in X,\ x\in A\}.
>$$ 
>
>If $X$ is nonempty, the _intersection_ $\bigcap X$ is the set
>
>$$
>\{x:\forall A\in X,\ x\in A\}.
>$$

You are likely familiar with the following particular cases of union and intersection.

>[!abstract] Example.
>
>1. If $X=\{A,B\}$, then $\bigcup X=A\cup B$ and $\bigcap X=A\cap B$.
>2. If $X=\{A_0,A_1,\dots,A_n\}$, then
>
>$$
>\bigcup X=\bigcup_{i\leq n}A_i\qquad\text{ and }\qquad\bigcap X=\bigcap_{i\leq n}A_i.$$

I am in need of more general notation. An _indexed family_ of sets is a set of the form $\mathcal F=\{x_\alpha:\alpha\in I\}$. $I$ is called the _indexing set_, and $\alpha$ is called the _index_.

The intersection and union over indexed families is treated the same way as above.

$$
\bigcup\mathcal F=\bigcup_{\alpha\in I}x_\alpha\qquad\text{ and, if } I\neq\emptyset,\qquad\bigcap\mathcal F=\bigcap_{\alpha\in I}x_\alpha.
$$

Here is a concrete example: let $\mathcal F$ be the collection of all open intervals of the form $(a,b):=\{x\in\mathbb R:a<x<b\}$ for all $0<a<b$. I claim that $\bigcup\mathcal F=\mathbb R^+:=\{x\in\mathbb R:x>0\}$. To prove this, notice that every element of the left set is a real number, by definition. Thus I only focus on the $\boxed{\supseteq}$ containment.

Let $x$ be a positive real. Then $a:=x/2$ is also positive. Therefore, $x\in(a,x+1)\subseteq\bigcup\mathcal F$, and I am done.

## Products

I defined the Cartesian product of two sets $A\times B$. Here is how to define the generalized Cartesian product.

>[!def] Definition (Cartesian product).
>
>Let $\mathcal F=\{X_i:i\in I\}$ be an indexed family. The _product_ is defined as
>
>$$
>\prod_{i\in I}X_i:=\left\{f\in\left(\bigcup_{i\in I}X_i\right)^I\ :\ \forall i\in I,\ f(i)\in X_i\right\}.
>$$

That is, the elements of the product are all the functions $f:I\to\bigcup_{i\in I}X_i$ that for each index _choose_ an element out of each set $X_i$. (These $f$ are often called _choice functions_.)

It is clear that the product of two nonempty sets is always empty. However for the general case, it is possible for the product to be empty even if all the $X_i$ are nonempty. This requires failure of the axiom of choice, and thus it is also impossible for me to give you an example using any of the tools developed so far in this course.

I will use the following meta-symbols $\clubsuit$ and $\spadesuit$. Let one of them by the union $\bigcup$ and the other one the intersection $\bigcap$. The theorems below are true for any nonempty indexed family of sets.

>[!thm] Generalized distributivity laws.
>
>
>$$
>\mathop{\Huge\clubsuit}_{i\in I}\ \mathop{\Huge\spadesuit}_{j\in J}A_{i,j}=\mathop{\Huge\spadesuit}_{f\in\prod_{i\in I}J_i}\ \mathop{\Huge\clubsuit}_{j\in J}A_{i,f(i)};
>$$
>
>and
>
>$$
>\prod_{i\in I}\left(\mathop{\Huge\spadesuit}_{J_i}A_{i,j}\right)=\mathop{\Huge\spadesuit}_{f\in\prod_{i\in I}J_i}\left(\prod_{i\in I}A_{i,f(i)}\right).
>$$

>[!thm] Generalized commutativity laws.
>
>Let $\Phi:\mathcal F\to\mathcal F$ be a bijection. Then,
>
>$$
>\mathop{\Huge\spadesuit}\mathcal F=\mathop{\Huge\spadesuit}\Phi[\mathcal F].
>$$
>
>Equivalently, if $\varphi:I\to I$ is a bijection, then
>
>$$
>\mathop{\Huge\spadesuit}_{i\in I}A_i=\mathop{\Huge\spadesuit}_{i\in I}A_{\varphi(i)}.
>$$

>[!thm] Generalized associativity laws.
>
>Let $\sim$ be an equivalence relation on $\mathcal F$. Then,
>
>$$
>\mathop{\Huge\clubsuit}\mathcal F=\mathop{\Huge\clubsuit}\ \mathop{\Huge\clubsuit}\frac{\mathcal F}\sim.
>$$
>
>Equivalently, if $\sim$ is an equivalence relation on $I$,
>
>$$
>\mathop{\Huge\clubsuit}_{i\in I}A_i=\mathop{\Huge\clubsuit}_{C\in I/\sim}\ \mathop{\Huge\clubsuit}A_{i\in C}.
>$$

>[!thm] Laws for products.
>
>All of the above are true when $\mathop{\Huge\clubsuit}$ is $\prod$, but both sides of every equality need to be enclosed in vertical bars (cardinality).

## Basic exercises

>[!note] Exercise.
>
>Prove that for any set $X$, $X=\bigcup_{x\in X}\{x\}$.

>[!note] Exercise.
>
>Let $A_k:=\{n\in\mathbb Z:n>k\}$ for any integer $k$. What is $\bigcap_{k\in\mathbb Z}A_k$?

>[!note] Exercise.
>
>If $\emptyset\neq\mathcal A\subset\mathcal B$, what is the relation between $\bigcap\mathcal A$ and $\bigcap\mathcal B$?

>[!note] Exercise.
>
>Show that the powerset operator commutes with the intersection but not the union. That is,
>
>$$
>\bigcap_{i\in I}\mathcal P(A_i)=\mathcal P\left(\bigcap_{i\in I}A_i\right)\qquad\bigcup_{i\in I}\mathcal P(A_i)\subseteq\mathcal P\left(\bigcup_{i\in I}A_i\right).
>$$

>[!note] Exercise.
>
>1. For any set $X$, $\bigcap\mathcal P(X)=\emptyset$.
>2. $\bigcup X=\emptyset$ if and only if $X=\emptyset$ or $A\in X$ implies $A=\emptyset$ for all $A$.

