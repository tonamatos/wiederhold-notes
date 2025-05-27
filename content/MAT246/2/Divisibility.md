---
title: "2.2. Divisibility"
draft: false
---
## The division algorithm

When reading this section, ask yourself why is this called an _algorithm_? You have not understood the main result below until you can confidently answer this question.

>[!thm] Theorem (Division algorithm / Q-R formula).
>
>Let $a$ and $d\geq1$ be integers. Then, there are $q,r\in\mathbb Z$ such that
>	(1) $a=dq+r$; and
>	(2) $0\leq r<d$.
>
>And any two integers $q$ and $r$ satisfying (1) and (2) above are unique.

The integers $q$ and $r$ are called the _quotient_ and the _remainder_, respectively, of the division of $a$ by $d$. The next section is dedicated to the special case when $r=0$; here I denote $q$ by the symbol $\frac ad$.

```python
# Most programming languages have built-in methods to compute these
# The most common notation is:

q = a // d # The double / means integer division, as opposed to float.
r = a %  d # Read as "a mod d".
```

>[!abstract] Examples.
>
>|$a$|$d$|$q$|$r$|
>|---|---|---|---|
>|17|8|2|1|
>|17|3|5|2|
>|-17|8|-3|7|


>[!proof] Proof of the division algorithm.
>
>Let $a$ and $d\geq1$ be integers. I only focus on proving the existence of $q$ and $r$ in the case when $a$ is non negative, as this is the only part of the argument that requires induction. Concretely, the uniqueness argument should be done separately, and the general case when $a$ is an integer follows from the discussion presented here.
>
>The case when $a=0$ is clear, since $a=d\cdot0+0$ for any $d$. Now, assume that the statement holds for all naturals smaller than $a$ and consider the following cases.
>
>If $a<d$, then writing $a=d\cdot0+a$ fulfills the sought conditions, and no induction is needed.
>
>If, on the other hand, $d\leq a$, then applying the inductive hypothesis to the natural $a-d$, which is of course less than $a$, I get $q',r$ integers such that $a-d=dq'+r$. But then, $a=d(q'+1)+r$ so letting $q=q'+1$ I am done.

This is another illustrative example of how strong induction can be useful. Attempting to prove this by weak induction, one runs into the problem of having to use the fact that $a$ can be written as $a=dq+r$ to accomplish the same for $a+1$, which is cumbersome and not intuitive.

>[!note] Exercises.
>
>(For CS students) Implement this proof as an actual recursive **algorithm**.

>[!warning] Note:
>
>Illustrative examples are seen in the lectures.

## Divisibility

>[!def] Definition.
>
>Let $a$ and $b$ be integers. I say $a$ _divides_ $b$, in symbols $a\mid b$, if there is an integer $s$ such that $b=sa$. Under these circumstances, I also say that $a$ is a _divisor_ or _factor_ of $b$, and that $b$ is a _multiple_ of $a$.

>[!question] Reflect.
>
>How are this definition and the Q-R formula related? Could I have defined the relation $\mid$ in terms of the quotient and remainder? How?

An important observation is that the integer $s$ above, if it exists, must be unique by the Q-R formula.

As an example, $2\mid 4$ because $4=2\cdot 2$. Also, $3\mid 24$ because $24=8\cdot3$. On the other hand, $3$ does not divide $4$, because there is no integer $s$ such that $4=s\cdot 3$.

Let us prove some elementary properties of divisibility before I leave some exercises.

>[!question] Reflect.
>
>As an exercise in abstraction, reflect on the fact that the first two properties of divisibility proved below are shared by other relations such as $\subseteq$ among sets, and $\leq$ among numbers.

>[!thm] Proposition.
>
>Let $a,b,c$ be integers.
>
>1. Every integer divides itself. In symbols, $a\mid a$. (_Reflexivity_)
>2. If $a\mid b$ and $b\mid c$, then $a\mid c$. (_Transitivity_)
>3. If $c\mid a$ and $c\mid b$, then for any $s,t\in\mathbb Z$, $c\mid sa+tb$. (_Linearity_, not to be confused with the Linear Algebra concept for transformations!)

>[!proof] Proof:
>
>1. Since $n=1\cdot n$, $n\mid n$. The same equality proves that $1\mid n$.
>2. Assume that $a\mid b$ and $b\mid c$. By definition, there are integers $s$ and $t$ such that $b=sa$ and $c=tb$. Then, using the associative properties of the product of integers, $c=t(sa)=(ts)a$, and so $a\mid c$.
>3. Solved in Tutorial 4.

An integer $n$ is called _even_ if $2\mid n$ and _odd_ otherwise. That is, even integers are of the form $2k$ for some $k\in\mathbb Z$. By the division algorithm, an odd integer can be written as $2k+1$ for some integer $k$. Convince yourself of this fact before moving forward.

>[!note] Exercises.
>
>1. For all $n\in\mathbb Z$, $1\mid n$ and $n\mid 0$.
>2. If $n$ is even, then $4\mid n^2$; but if $n$ is odd, then $8\mid n^2-1$.

>[!note] **Hard** problem.
>
>The product of $n$ consecutive integers is divisible by $n!$. ($n!$, read as _$n$ factorial_ is the product $1\cdot2\cdots n$.) 
>
>>[!hint]- Hint.
>>
>>Use that ${n\choose k}={n-1\choose k-1}+{n-1\choose k}$ and apply induction. Alternatively, use the result proved in Tutorial 4.

## Prime numbers

Numbers with precisely four divisors (two positive and two negative) are called _prime_. Integers bigger than $1$ that are not prime are called _composite_. For example, $7$ is a prime number: its four divisors are $-1,1$ and $-7,7$. $1$ is neither prime nor composite because it has two divisors: $-1$ and $1$. $4$ is composite because it has six divisors; the positive ones are $1,2,4$.

To decide if a number is prime, it is not necessary to check for all numbers smaller than it for possible divisors.

>[!note] Exercise.
>
>Show that if an integer $n>1$ has no divisors $k$ satisfying $2\leq k\leq\sqrt n$, then $n$ must be prime. Give an example as to why the bound on $k$ is the best possible. In other words, the statement fails when I replace the bound by $2<k\leq\sqrt n$ or $2\leq k<\sqrt n$.

>[!note] Exercise.
>
>There are arbitrarily large gaps between primes. Concretely, show that for any positive integer $k$, you can find $k-1$ consecutive composite integers.
>
>>[!hint]- Hint.
>>
>>Show that $k!+2,k!+3,\dots,k!+k$ are always composite.

## The lattice of integer divisibility

>[!warning] Note:
>
>The concept of _lattice_ is not explicitly part of the course, but several important examples are seen in the lectures. These follow informal discussions (and are hence inadequate for these notes) that summarize large portions of theory.