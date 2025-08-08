---
title: "5.1. Metric spaces"
draft: false
---
Topology plays in important role in one of the two learning objectives for this course: **Abstraction**. Concretely, there will be some technical definitions, such as the one below, that I will swiftly "forget" and leave behind in favor of more general, much more powerful ideas. The most important takeaway of this chapter is:

>Topology allows to talk about _closeness_ without having to talk about _distance_.

>[!def] Definition.
>
>A _metric space_ is a structure $(X,d)$ where $X$ is any set and the function $d:X\times X\to\mathbb R$, called the _metric_, has the following properties for any $x,y,z\in X$.
>1. $d(x,x)=0$;
>2. $d(x,y)>0$ whenever $x\neq y$ (_Positivity_);
>3. $d(x,y)=d(y,x)$ (_Symmetry_); and
>4. $d(x,z)\leq d(x,y)+d(y,z)$ (_Triangle inequality_).

### Example: graphs

If $G$ is a connected graph, define $d(u,v)$ as the smallest length of a path with endpoints $u$ and $v$. $(G,d)$ is then a metric space.

>[!note] Exercise.
>
>If $\varphi:G\to H$ is a graph homomorphism, then for all $x,y\in V(G)$, $d(\varphi(x),\varphi(y))\leq d(x,y)$.
>
>If $\varphi$ is an isomorphism, then the above inequality becomes an equality.

For a more concrete example, define in any component $B$ of the hypercube $B_\infty$, where $s$ and $t$ are countably infinite binary sequences, $h(s,t)$ as the number of coordinates that $s$ and $t$ differ in. That is,

$$
h(s,t):=|\{n\in\mathbb N:s(n)\neq t(n)\}|.
$$
$(B,h)$ is then a metric space. This particular $h$ is known as the [Hamming distance](https://en.wikipedia.org/wiki/Hamming_distance), and it plays an important role in error-correcting codes.

### Example: the reals

Another example: $\mathbb R^n$ with the _Euclidean metric_ given by

$$
d(\vec x,\vec y):=\sqrt{\sum_{i=1}^n(x_i-y_i)^2}.
$$
When $n=1$, this is just $d(x,y)=|x-y|$.

For a different example,

$$
d'(\vec x,\vec y):=\sum_{i=1}^n|x_i-y_i|
$$

is sometimes referred to as the _taxicab metric_. To see why, draw $\mathbb R^2$ as a grid and imagine roads connecting the lattice points.

## Open and closed sets

>[!warning] Note:
>
>Most intuitive examples are done in details in the lectures. They involve many sketches, which is why they are not included in these notes.

From now on, let $(X,d)$ be an abstract metric space. Since my course only deals with a very short introduction, for the most part you can safely assume that $X=\mathbb R$ with the Euclidean metric.

>[!def] Definition of open.
>
>The _open ball_ centered at $x$ and of radius $r>0$ is the set $B(x,r):=\{y\in X:d(x,y)<r\}$.
>
>A set $A\subseteq X$ is _open_ if for every $x\in A$, there is some $r>0$ such that $B(x,r)\subseteq A$.
>
>The collection of all open sets is denoted by $\tau(X)$ and is called the _topology_ of $X$.

An immediate remark is that open balls are open.

>[!abstract] Examples.
>
>1. In $X=\mathbb R$, open balls are open intervals of the form $(x-r,x+r)$.
>2. Furthermore, show that every open interval is open.
>3. $(-\infty,-1)\cup(1,\infty)$ is an open set that is not an interval.
>4. Draw an open ball centered at the origin of radius 1 in $X=\mathbb R^n$ for $n=2,3$.
>5. What are the open balls in a connected graph?
>6. Now draw open balls with the other metrics mentioned above. How are they different?

>[!def] Definition of closed.
>
>Given $x\in X$ and $A\subseteq X$, I say $x$ is a _point of closure of $A$_ if for all $r>0$, $B(x,r)\cap A\neq\emptyset$. The set of all these points is called the _closure of $A$_ and is denoted by $\overline A$.
>
>I say $A$ is _closed_ if $\overline A\subseteq A$.

It is obvious that $A\subseteq\overline A$.

>[!abstract] Examples.
>
>1. The interval $(0,1)$ does not contain $0$ or $1$, but these are points of closure.
>2. What are the points of closure of all of the sets mentioned in the previous example?
>3. What are the points of closure of the set $\{1/n:n>1\}$?
>4. $\overline{[0,1]}=[0,1]$, so this set is closed.
>5. $\overline Q=\mathbb R$ (_Density_).

>[!note] Exercise.
>
>Prove that $\overline{\overline A}=\overline A$ (_Idempotency_). In particular, closures are always closed. Put in different words, a set is closed if and only if it is equal to some closure.

>[!info] Note:
>
>Sadly, I will not have time to talk about general topology, but many examples I will cover can be extended to much more general structures. In fact, a good portion of the results I will show you hold in these spaces. Given the scope of this course, I will only deal with very select metric spaces as examples, however.

The following theorem is the actual definition of an abstract _topology_, which I will not cover in this course.

>[!thm] Theorem ("Metric spaces are _topological spaces_").
>
>1. $X$ and $\emptyset$ are open.
>2. The union of open sets is open.
>3. The intersection of finitely many closed sets is closed.

>[!proof]- Proof:
>
>>[!info] In lectures.

From now on, I will denote the collection of all open subsets of $X$ by $\tau(X)$. This set is typically called the _topology_ of $X$.

An important connection between open and closed sets is the following.

>[!thm] Proposition.
>
>A set $A$ is open if and only if $\mathbb R^n\setminus A$ is closed.

>[!proof] Proved in PS5-1.

Another easy-to-prove property of metric spaces is seen below.

>[!thm] Theorem ("Metric spaces have the _Hausdorff separation property_").
>
>For any distinct $x,y\in X$, there are disjoint open balls $B$ and $B'$ such that $x\in B$ and $y\in B'$.

>[!proof]+ Proof:
>
>Since $x\neq y$, $r:=\frac12d(x,y)>0$. Thus $B(x,r)$ and $B(y,r)$ have the desired property.

## Interior and closure operators

>[!def] Definition of interior.
>
>Let $A\subseteq X$. Then $\operatorname{int}A$ is the union of all open sets contained in $A$.

>[!thm] Basic properties of interior and closure.
>
>1. $\operatorname{int}A\subseteq A\subseteq\overline A$ and the three sets are equal if and only if $A\in\{\emptyset,X\}$.
>2. If $A\subseteq B$, then $\overline A\subseteq\overline B$ and $\operatorname{int}A\subseteq\operatorname{int}B$. (_Monotonicity_)
>3. $\operatorname{int}A$ is the union of all open balls contained in $A$.
>4. $A\in\tau$ if and only if $A\subseteq\operatorname{int}A$. In particular, the interior is always open and the closure is always closed.
>5. $\operatorname{int}A\cap\operatorname{int}B=\operatorname{int}(A\cap B)$ and $\overline A\cup\overline B=\overline{A\cup B}$.
>6. $\operatorname{int}(X\setminus A)=X\setminus\overline A$ and $\overline{X\setminus A}=X\setminus\operatorname{int}A$.

>[!note] Exercises.
>
>1. Prove the above proposition.
>2. Find counterexamples for the converse implications of (2).
>3. Find counterexamples for (5) interchanging union and intersection.
>4. Prove that if $A$ is closed and $B$ has empty interior, then $\operatorname{int}(A\cup B)=\operatorname{int}A$.
>5. Give a counterexample of the above after removing the word **closed**.

## Sequences

Recall that a _sequence in $X$_ is just a function $f:\mathbb N\to X$, which I denote by its indices $x_n=f(n)$ when convenient.

>[!def] Notation/Definition of limit.
>
>Let $\lim_{n\to\infty}x_n=x$ abbreviate the following statement.
>
>$$
>\forall r>0\quad\exists N\in\mathbb N\quad\forall n\geq N\quad x_n\in B(x,r)
>$$

>[!abstract] Example.
>
>I will prove that $\lim_{n\to\infty}\frac1n=0$. Let $r>0$, then, by the Archimedean property, there is an $N\in\mathbb N$ such that $N>\frac1r$. But then $\frac1N<r$, so obviously $\frac1n\in B(0,r)$ for all $n\geq N$.

>[!note] Exercise.
>
>If $A$ is a closed set and $\{x_n\}_n\subseteq A$ has a limit $x$, then $x\in A$.

>[!thm] Theorem ("In metric spaces, _sequential closure_ and closure are the same").
>
>For any set $A\subseteq X$, $\overline A=\{x\in X:\exists\{x_n\}_n\subseteq A\ \lim_{n\to\infty}x_n=x\}$.

>[!proof]+ Proof:
>
>$\boxed\subseteq$ Let $x\in\overline A$. For every natural $n$, pick $x_n\in A\cap B(x,\frac1{n+1})$, then clearly $\{x_n\}_n\subseteq A$.
>
>>[!note] Exercise.
>>
>>Verify that $\lim_{n\to\infty}x_n=x$.
>
>Therefore, $x$ is a member of the set on the right-hand side.
>
>$\boxed\supseteq$ Suppose that $\lim_{n\to\infty}x_n=x$ for some $\{x_n\}_n\subseteq A$. Let $r>0$. Then, for some large natural $N$, $x_N\in B(x,r)$. Clearly this implies that $B(x,r)\cap A\neq\emptyset$ and so $x\in\overline A$.