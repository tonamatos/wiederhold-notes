---
title: "4.2. The pigeonhole principle"
draft: false
---
## The pigeonhole principle

Let us start with a simple example that motives the main result of the section.

A man enters an elevator with six other people. As he reaches to press the button to select his floor, he notices that seven buttons are already lit up. This doesn't add up, he thinks. If every person on the elevator selected one floor, there should be at most (possibly less, as different people could want to go to the same floor) six buttons selected. One of you pressed more than one button! He exclaims annoyed.

>[!note] Exercise.
>
>Suppose that $50$ people attend an event and some or all purchase tickets for a raffle. If tickets for $51$ different prizes were sold, prove that someone must get at least two prizes.
>
>>[!check]- Solution.
>>
>>Suppose otherwise, that is, that everyone gets at most one prize. Since there are $50$ people, that means that at most $50$ prizes are distributed. But this is false, as there are $51$ prizes.

The following important fact can be formalized using the language of [[Functions#Injectivity and surjectivity|injective functions]].

>[!thm] Pigeonhole principle.
>
>If there are $n$ pigeons to be distributed among fewer than $n$ pigeonholes, then at least one pigeonhole will have at least two pigeons.

Imagine that $1001$ people are standing in line to get the COVID vaccine. The line has $2000$ spots. Since it's the middle of the pandemic, the people are asked to leave one free space between every two people standing in line to ensure a safe distance. Show that this is impossible.

In a perhaps more mathematical language:

>[!note] Exercise.
>
>Consider the set $X$ of all integers $x$ satisfying $1\leq x\leq 2000$ (so, $X$ has $2000$ elements). Prove that every subset $A$ of $X$ of size more than $1000$ must contain two numbers that are consecutive. In symbols, there exists $n\in A$ such that $n+1\in A$.
>
>>[!check]- Solution.
>>
>>Consider the sets (the pigeonholes) $\{2n-1,2n\}$ for $1\leq n\leq 1000$. These are pairwise disjoint and there are $1000$ of them. If $A$ (the pigeons) is a set of more than $1000$ elements from $X$, then one of the above sets must contain two elements of $A$, say $2k-1$ and $2k$. This pair of integers has the desired property.

>[!note] Exercise.
>
>Prove the following versions of the pigeonhole principle.
>1. If $a_1,a_2,\dots,a_n, c$ are real numbers such that $\sum_{i=1}^na_i\geq c$, then there is at least one value of $i$ such that $a_i\geq c/n$.
>2. If $a_1,a_2,\dots,a_n$ are integers, and $c$ is a real number such that $\sum_{i=1}^na_i\geq c$, then there is at least one value of $i$ such that $a_i\geq\lceil c/n\rceil$.
>
>>[!check]- Solution.
>>
>>By contrapositive, if $a_i<c/n$ for all $i$, then $\sum_{i=1}^na_i<\sum_{i=1}^n\frac cn=n\cdot\frac cn=c$.
>>
>>If, in addition, each $a_i$ is an integer, then rounding up each side of the inequality yields the second result.

>[!note] Exercise.
>
>Color each point of the grid $\mathbb Z\times\mathbb Z$ in one of three colors. Prove that some rectangle has all four vertices of the same color. Moreover, argue that this rectangle can always be found within a fixed _compact_ region of the plane.
>
>>[!question] Reflect.
>>
>>Can you do this for more than three colors?
>
>>[!check]- Solution.
>>
>>Call the coloring $\chi$ and consider the rectangle $R=\{(x,y):0\leq x\leq 3,0\leq y\leq 3^4\}$.
>>
>>For every, $0\leq y_0<3^4$, call $F_{y_0}=\{(x,y)\in R:y=y_0\}$. There are $3^4+1$ rows in $R$ and each row can be colored in $3^4$ ways, so by the pigeonhole principle, the coloring function $\overline\chi:\{F_y:0\leq y\leq 3^4\}\to\mathcal P(3)$ given by $F_y\mapsto\chi[F_y]$ is **not** injective. That is, two rows $F_{y_0}$ and $F_{y_1}$ have the same coloring.
>>
>>Once again, by the pigeonhole principle and since each $|F_y|=4$, the function $\chi\restriction F_y$ is not injective. So, there are two points in the same row, $(x_0,y_0)$ and $(x_1,y_1)$, that are the same colour. It is clear that all four points formed by $(x_i,y_i)$ must then be the same colour, and so we are done.

>[!note] Exercise.
>
>Let $n$ be a positive integer and $X$ be a subset of size $n+1$ of the set $Y=\{1,2,\dots,2n\}$.
>
>1. Prove that there exist distinct $a,b\in X$ such that $a$ divides $b$.
>2. Show, with an example, that the conclusion is false if $X$ has size $n$ instead.

>[!note] Exercise.
>
>A bridge club has $10$ members. Every day, four members of the club get together and play one game of bridge. Prove that after two years, there is some particular set of four members that has played at least four games of bridge.
>
>>[!check]- Solution.
>>
>>There are ${10\choose 4}=210$ ways of picking four members of the club. If at most three of these choices repeat in the $365\cdot2=730$ days, then there were at most $3\cdot210=630<730$ matches, which is impossible if they play every day. Hence, some choice of four players repeated at least four times.

## Generalized pigeonhole principles

>[!note] Exercise.
>
>Show that if more than $mr$ elements are put into $r$ sets, some set contains $m$ elements.

>[!note] Exercise.
>
>Among any 200 positive integers, there are 29 of them that are pairwise congruent mod 7.

>[!note] Exercise.
>
>Show that if $a_1,\dots,a_n$ are positive integers and more than $(a_1+\cdots+a_n)-n$ pigeons are put in $n$ pigeonhole, for some $i$, the $i$th pigeonhole contains at least $a_i$ pigeons.

>[!note] Exercise.
>
>Prove this generalized pigeonhole principle:
>
>If you put $Nk+1$ pigeons into $N$ pigeonholes, one hole has $k+1$ pigeons.

>[!note] Exercise.
>
>Every point on the plane $\mathbb R^2$ is colored red or blue. Prove that there are always two points exactly one unit apart that have the same color.

>[!note] Exercise.
>
>Any five points placed inside a unit square contain a pair of points at distance at most $\sqrt2/2$.

>[!note] Exercise.
>
>Any subset of $\{1,2,\dots,2n\}$ of size at least $n+1$ contains two relative primes.

>[!note] Exercise.
>
>Among any $n+1$ positive integers, two of them have a distance divisible by $n$.

>[!note] **Hard** exercise (special case of the [Erdős-Szekeres theorem](https://en.wikipedia.org/wiki/Erd%C5%91s%E2%80%93Szekeres_theorem)).
>
>Prove that any sequence of $n^2+1$ different naturals contains a monotonic subsequence of length $n+1$.
>
>For every $n$, construct a sequence of $n^2$ naturals containing no monotonic subsequence of length $n+1$.

>[!note] **Hard** exercise (IMO 1972).
>
>From a set of ten two-digit decimal numbers, two disjoint subsets have the same sum.