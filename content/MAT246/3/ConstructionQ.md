---
title: "3.1. Construction of Q"
draft: false
---
The construction of the rationals follows a very similar procedure to the [[ConstructionZ|construction of the integers]]. The main difference is that here, I am interested in learning how to _divide_ integers, rather than subtract naturals.

>[!hint] Note:
>
>I wrote this page assuming the reader is comparing it with the one linked before, it will double the benefit of reading this one. Most ideas are the same, changing the sum to a product and ensuring everything works well.

![common sets](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ef/Real_numbers.svg/500px-Real_numbers.svg.png)

Consider the following equation.

$$
a\cdot x=b
$$

In $\mathbb Z$, this will not always have a solution, for instance $5\cdot x=3$. How do I "add" the missing solution to produce a larger structure?

## The set of rationals is a quotient

I want to be able to talk about an object of the form $\frac mn$ from within the naturals. In the above example, such an object would indeed solve the equation, namely $\frac 35$. I will encode this sought behavior by means of an [[Relations#Equivalence relations|equivalence relation]] defined as follows.

>[!def] Definition.
>
>Let $\sim_q$ be the relation on $\mathbb Z\times(\mathbb Z\setminus\{0\})$ defined by $(m,n)\sim_q(p,q)$ if and only if $m\cdot q=p\cdot n$.

By now, this should be a routine exercise: $\sim_q$ is an equivalence relation. The equivalence classes are called _rational numbers_, and $\mathbb Q:=\mathbb Z\times(\mathbb Z\setminus\{0\})/\sim_q$.

>[!def] Definition (Addition and multiplication in $\mathbb Q$).
>
>>[!note] Exercise.
>

>[!thm] Lemma.
>
>The addition and multiplication of rationals is well-defined, associative, commutative and distribute over each other. (Definition for all these words is found [[ConstructionN|here]].)

## The rationals contain the integers

>[!thm] Theorem (Embedding of $\mathbb N$ in $\mathbb Z$).
>
>There is an injective function $e:\mathbb Z\to\mathbb Q$ that preserves the algebraic and order structures of $\mathbb Z$.

>[!proof] Proof:
>
>Define $e(n):=[(n,1)]_{\sim_q}$.

>[!thm] Theorem.
>
>There is a unique rational $x$ such that $a\cdot x=b$, whenever $a\neq 0$. Note here that the rational number $0$ really is $[(0,1)]_{\sim_q}$.

I denote the rational $x$ by the symbol $\frac ba$.

>[!proof] Proof:
>
>Suppose that $a=[(a_0,a_1)]_{\sim_q}$ and similarly for $b$, then take $x:=[(b_0a_1,b_1a_0)]_{\sim_q}$.

>Congratulations!
>You have learned to _divide_ numbers.

## The order of $\mathbb Q$

Unlike the integers, the order of my new structure $\mathbb Q$ is actually significantly more complex than that of the integers.

>[!thm] Theorem ($\mathbb Q$ is _dense_).
>
>Let $a<b$ be rationals. Then there exists a rational $c$ such that $a<c<b$.

>[!proof] Proof:
>
>Simply take $c:=\frac{a+b}2$. The details are left to the reader.

## The reals

The construction of the reals is considerably longer than the constructions I presented so far. I chose to skip it entirely.

In simple terms, the reals satisfy the same properties of _ordered field_ that the rationals do, with the added bonus that it has no holes. This idea is made precise in the Topology chapter of the course.

>[!thm] Lemma.
>
>Let $p,q$ be integers and $d$ their GCD. Then, $\frac pd\perp\frac qd$. Clearly, $\frac pq=\frac{p/d}{q/d}$. This is called the _reduced form_ of the fraction.

>[!proof] Proven [[GCD and LCM|here]].

>[!thm] Theorem.
>
>There is a real number $x$ such that $x^2=2$, but such a real cannot be rational.

>[!proof]+ Proof:
>
>I only focus on the second statement, as the existence is trickier than you might think.
>
>By contradiction, suppose that $x=\frac{p}{q}$ for $q\neq0$ and $p$ integers. By the lemma, I can assume that $p\perp q$, since otherwise, I can divide both numbers by their GCD until it is in reduced form.
>
>It follows from $x^2=2$ that $p^2=2q^2$ is an even number. Since 2 is prime, by Euclid's lemma, $p$ must also be even, say $p=2k$. But then, $2k^2=q^2$, which by the same argument means that $q$ must be even. This contradicts $p\perp q$.

>[!note] Exercise.
>
>Generalize this to: the $n$-root of a prime number is never rational.