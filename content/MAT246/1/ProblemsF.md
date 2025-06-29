---
title: "1.7. Practice problems"
draft: false
---
## Logic

### Negating quantified statements

Negate the following statements.

>[!note] Exercise.
>
>For every $x\in\mathbb N$, $x^2-5>0$.
>
>>[!check]- Solution.
>>
>>There exists an $x\in\mathbb N$ such that $x^2-5\leq0$.

>[!note] Exercise.
>
>There exists an $x\in\mathbb N$ such that $x^2<10$.
>
>>[!check]- Solution.
>>
>>For every $x\in\mathbb N$, $x^2\geq10$.

>[!note] Exercise.
>
>For every $x\in\mathbb R$, there exists $y\in\mathbb R$ such that $2x-y=0$.
>
>>[!check]- Solution.
>>
>>There exists an $x\in\mathbb R$ such that for every $y\in\mathbb R$, $2x-y\neq0$.

>[!note] Exercise.
>
>Let $S$ be a subset of $\mathbb R$. For every open interval, $I$, containing $a$, there exists a point $p\in I$ that is also in $S$.
>
>>[!check]- Solution 1.
>>
>>There exists an open interval, $I$, containing $a$, such that the intersection of $I$ and $S$ is the empty set.
>
>>[!check]- Solution 2.
>>
>>There exists an open interval, $I$, containing $a$, such that for every $p$ in $I$, $p$ is not an element of $S$.

Below is the definition of _continuous function_.

>[!note] Exercise.
>
>Let $c$ be a fixed real number. For all $\varepsilon >0$, there exists a $\delta >0$ such that $|f(x)-f(c)|< \varepsilon$ for all $x$ satisfying $|x-c|< \delta$.
>
>>[!check]- Solution.
>>
>>There exists an $\varepsilon>0$ such that for every $\delta >0$ there exists an $x$ such that $|x-c|<\delta$ and $|f(x)-f(c)| \geq \varepsilon$.

>[!question] Reflect.
>
>What happens when you negate a quantifier? What happen when you negate an **and** statement? What happens when you negate an implication?

### Contrapositive

Find the _contrapositive_ of the following implications.

>[!note] Exercise.
>
>If $x>3$ then $x+2 > 5$.
>
>>[!check]- Solution.
>>
>>If $x+2 \leq 5$, then $x \leq 3$.

>[!note] Exercise.
>
>If today is Tuesday, then tomorrow is Wednesday.
>
>>[!check]- Solution.
>>
>>If tomorrow is not Wednesday, then today is not Tuesday.

>[!note] Exercise.
>
>If $n$ is an even natural number, then $f(n)$ is an odd natural number.
>
>>[!check]- Solution.
>>
>>If $f(n)$ is an even natural number, then $n$ is an odd natural number.

>[!note] Exercise.
>
>If $f(x)$ is differentiable at $x=c$, then $f(x)$ is continuous at $x=c$.
>
>>[!check]- Solution.
>>
>>If $f(x)$ is not continuous at $x=c$, then $f(x)$ is not differentiable at $x=c$.

>[!note] Exercise.
>
>If $n$ is a multiple of 6, then $n$ is a multiple of 3.
>
>>[!check]- Solution.
>>
>>If $n$ not a multiple of 3, then $n$ is not a multiple of 6.

>[!question] Reflect.
>
>Come up with more examples of contrapositive statements from your everyday life. People mention implications all the time in the news, lectures and casual conversation.

## Set theory

### Weak induction

>[!note] **Hard** problem (Rédei, 1934).
>
>Let $n$ be a positive natural and $\rightarrowtail$ be a relation on a set $X$ of size $n$ such that
>
>1. for all $x,y\in X,\quad x\neq y$ implies $x\rightarrowtail y$ or $y\rightarrowtail x$, but not both.
>
>Prove that there is a function $f:\{1,\dots,n\}\to X$ such that
>
>2. for all $1\leq i<n,\quad f(i)\rightarrowtail f(i+1)$.
>
>>[!hint]- Hint.
>>
>>Think of $X$ as a set of villages, and $\rightarrowtail$ as one-way roads connecting every pair. The conclusion says that you can make a path $f$ to traverse all villages: $f(1)\rightarrowtail f(2)\rightarrowtail\cdots\rightarrowtail f(n)$. Make a diagram.
>
>>[!check]- Solution.
>>
>>I proceed by induction on $n$. If $n=1$, the statement holds vacuously. Now suppose that the statement holds for $n>1$.
>>
>>>[!hint] Hint.
>>>
>>>Write down the precise inductive hypothesis: **for every** set $X$ of size $n$, **for every** relation $\rightarrowtail$ satisfying (1.), there exists a function $f$ satisfying (2.).
>>
>>Suppose that $X$ is a set of size $n+1$ and that $\rightarrowtail$ is a relation on $X$ such that (1.). Pick $x\in X$ and notice that $\rightarrowtail$ restricted to $X\setminus\{x\}$ satisfies (1.). By the inductive hypothesis, there is a function $f:\{1,\dots,n\}\to X\setminus\{x\}$ such that (2.).
>>
>>>[!hint] Hint.
>>>
>>>Translate the proof into the language of villages and roads if you find this easier.
>>
>>Consider $f(1)$ and $f(n)$.
>>
>>>[!hint] Hint.
>>>
>>>The first and last villages of the path $f$ must be connected to $x$ somehow, and I need to figure out how to add $x$ to this plan. This will depend on the direction of the roads. If the road leads from $x$ to $f(1)$, the first village, then clearly I can start at $x$ and then do the path $f$. Similarly, if $f(n)$ leads into $x$, I can do the path $f$ and then go to $x$ last. These two cases are made precise as follows. The overline on $\overline f$ is just notation.
>>
>>If $f(n)\rightarrowtail x$, I define $\overline f:\{1,\dots,n+1\}\to X$ given by
>>
>>$$
>>\overline f(i)=\begin{cases}
>>f(i) & 1\leq i\leq n \\
>>x & i=n+1
>>\end{cases}
>>$$
>>
>>$\overline f$ satisfies (2.) and so I am done in this case.
>>
>>>[!hint] Hint.
>>>
>>>The responsible reader will verify these claims.
>>
>>The case when $x\rightarrowtail f(1)$ is analogous letting
>>
>>$$
>>\overline f(i)=\begin{cases}
>>x & i=1 \\
>>f(i-1) & 1<i\leq n+1
>>\end{cases}
>>$$
>>
>>By (1.), if neither of the two cases above happen, then
>>
>>$$
>>f(1)\rightarrowtail x\quad\text{ and }\quad x\rightarrowtail f(n).\qquad(3)
>>$$
>>
>>>[!hint] Hint.
>>>
>>>How do you incorporate $x$ into the path in this case? Well, you cannot add $x$ at the beginning or the end, since the roads point the wrong way. Logically, you must make a detour to $x$ somewhere in the middle of the path: you need a road from some village $f(i)$ to $x$, and a road from $x$ into the next village $f(i+1)$. Then, $f(1)\rightarrowtail\cdots\rightarrowtail f(i)\rightarrowtail x\rightarrowtail f(i+1)\rightarrowtail\cdots\rightarrowtail f(n)$ is a valid path.
>>
>>I claim that there is $1\leq i<n$ such that $f(i)\rightarrowtail x\rightarrowtail f(i+1)$.
>>
>>By contradiction, suppose not. That is, assume that
>>
>>$$
>>\text{for all }1\leq i<n,\quad x\rightarrowtail f(i)\text{ or }f(i+1)\rightarrowtail x.\qquad(4)
>>$$
>>
>>I now show that $f(n)\rightarrowtail x$ by an inductive argument, contradicting (3). When $j=1$, by (3) and (4), $f(j+1)\rightarrowtail x$. If $j+1<n$ is such that $f(j+1)\rightarrowtail x$, then by (4), $f(j+2)\rightarrowtail x$. Thus, by induction, $f(n)\rightarrowtail x$.
>>
>>>[!hint] Hint.
>>>
>>>Hidden inductions like these appear all the time in more elaborate proofs. The precise statement I proved is that for all $j\in\mathbb N$, if $j<n$, then $f(j+1)\rightarrowtail x$. Thus, in particular (taking $j=n-1$), $f(n)\rightarrowtail x$.
>>
>>Therefore, the claim is true and I define
>>
>>$$
>>\overline f(k)=\begin{cases}
>>f(k) & 1\leq k\leq i\\
>>x & k=i+1\\
>>f(k-1) & i+1<k\leq n+1
>>\end{cases}
>>$$

### Strong induction

>[!note] **Very hard** problem.
>
>Let $n$ be a positive natural number. Prove that
>
>$$
>\sqrt{3n}\prod_{k=1}^n\frac{2k-1}{2k}\leq1.
>$$
>
>>[!hint]- Hint.
>>
>>This question is especially challenging because if attempted by weak induction, when reducing the case from $n+1$ to $n$, one would wish to show that
>>
>>$$
>>\frac{\sqrt{3n+3}}{\sqrt{3n}}\cdot\frac{2n+1}{2n+2}\leq1,
>>$$
>>
>>but this is false even for $n=1$.