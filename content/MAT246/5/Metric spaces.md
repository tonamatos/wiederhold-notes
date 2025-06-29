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

For example, if $G$ is a connected graph, define $d(u,v)$ as the minimum length of a path with endpoints $u$ and $v$. $(G,d)$ is then a metric space.

Another example: $\mathbb R^n$ with the Euclidean metric given by

$$
d(\vec x,\vec y):=\sqrt{\sum_{i=1}^n(x_i-y_i)^2}.
$$
When $n=1$, this is just $d(x,y)=|x-y|$. This is not the only metric that works for $\mathbb R^n$. For example,

$$
d(\vec x,\vec y):=\sum_{i=1}^n|x_i-y_i|
$$

gives a different metric space, but all of these metrics will give rise to the same _topology_, which is sort of the point. I don't really care about a specific number that measures the distance, I just want to distinguish objects that are similar or _close_ from those that are different or distant.
## Open and closed sets

>[!warning] Note:
>
>Most intuitive examples are done in details in the lectures. They involve many sketches, which is why they are not included in these notes.

From now on, let $(X,d)$ be an abstract metric space. Since my course only deals with a very short introduction, for the most part you can safely assume that $X=\mathbb R$ with the Euclidean metric.

>[!def] Definition (Open).
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

>[!def] Definition (Closed).
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


## Sequences

Most of the theory of metric spaces involves sequences. Since I want to transcend this and move to more abstract and simpler concepts, I will only use sequences for examples. Recall that a _sequence in $X$_ is just a function $f:\mathbb N\to X$, which I denote by its indices $x_n=f(n)$ when convenient.

>[!def] Notation (Limit).
>
>Let $\lim_{n\to\infty}x_n=x$ abbreviate the following statement.
>
>$$
>\forall r>0\quad\exists N\in\mathbb N\quad\forall n\geq N\quad x_n\in B(x,r)
>$$

>[!abstract] Example.
>
>I will prove that $\lim_{n\to\infty}\frac1n=0$. Let $r>0$, then, by the Archimedean property, there is an $N\in\mathbb N$ such that $N>\frac1n$. But then $\frac1n<r$, so obviously $\frac1n\in B(0,r)$ for all $n\geq N$.

>[!thm] Theorem ("In metric spaces, _sequential closure_ and closure is the same").
>
>For any set $A\subseteq X$, $\overline A=\{x\in X:\exists\{x_n\}_n\subseteq A\ \lim_{n\to\infty}x_n=x\}$.