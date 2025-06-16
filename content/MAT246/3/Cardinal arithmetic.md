---
title: "3.2. Cardinal arithmetic"
draft: false
---
## An algebra of functions

For this section, suppose that $f:A\to B$ and $g:B\to C$ are functions.

>[!def] Definition (Composition).
>
>The _composition of $f$ and $g$_ is the function $g\circ f:A\to C$ given by $g\circ f(a):=g(f(a))$.

>[!note] Exercises.
>
>1. Prove that the composition of injective (surjective) functions is again injective (surjective).
>
>2. Assume that $g\circ f$ is injective (surjective). What can you say about the injectivity (surjectivity) of $f$ and $g$? 

If $f$ is bijective, the _inverse of $f$_ is the function $f^{-1}=\{(b,a):(a,b)\in f\}$ from $B$ to $A$. Why is bijectivity, that is the fact that $f$ be both injective and surjective, important here?

>[!def] Definition (Restriction).
>
>The _restriction of $f$ to $D\subseteq A$_ is the function $f|_D:D\to B$ defined by $f|_D(x)=f(x)$.

>[!abstract] Examples.
>
>1. The restriction of a constant function is constant.
>2. The restriction of an injective function is injective.
>3. The restriction of the identity on a set $X$ to any subset of $X$ is the identity on that subset.

>[!def] Notation.
>
>The set of all functions $A\to B$ is denoted by $B^A$. This choice of symbol is motivated in the tutorials, where it is shown that for finite sets $|B^A|=|B|^{|A|}$.
## Equinumerosity

>[!warning] Note:
>
>This topic is introduced in the lectures. The discussion is inadequate for these notes.

>To measure is to compare.

>[!def] Notation.
>
>I abbreviate the phrase "there exists a bijective function $X\to Y$" by writing $|X|=|Y|$. I will also say $X$ and $Y$ are _equinumerous_, or _have the same size_.

This symbol has the following properties, which you should verify yourself.

>[!thm] Proposition.
>
>For any set $X$,
>
>1. $|X|=|X|$ (Reflexivity).
>2. If $|X|=|Y|$, then $|Y|=|X|$ (Symmetry).
>3. If $|X|=|Y|$ and $|Y|=|Z|$, then $|X|=|Z|$ (Transitivity).

Compare these properties with others mentioned in previous chapters, such as [[Relations|here]].

>[!warning]- Metamathematical warning (safe to ignore):
>
>Despite appearances, it is **not** correct to say that this symbol defines an equivalence relation. An explanation for this goes well beyond the scope of this course but will be mentioned in the lectures.
>
>For the sake of intuition, you can think of _cardinal numbers_ as precisely the equivalence classes of this relation.

## Finite sets revisited

Earlier I defined the word _finite_ in terms of natural numbers. Indeed, a way to rewrite my earlier definition is that a set $X$ is finite if there is a natural $n$ such that $|X|=|\{0,\dots,n-1\}|$. In this case, it is shorter to just write $|X|=n$, but I must first convince you that this is well-defined.

>[!question] Reflect.
>
>Well-defined, in this instance, means that there could be more than one natural satisfying the definition. How do you know which one to pick? Of course this does not happen, but I must prove this to you.

It wasn't until 1888 that [Dedekind](https://en.wikipedia.org/wiki/Dedekind-infinite_set) came up with a definition of _finite set_ that did not need the naturals to be constructed first. I will not use the definition, but if you are curious, one can prove that a set is finite if and only if it is not equinumerous with a proper subset of itself. This can be used to define finiteness without reference to any numbers. The fact that $\mathbb N$ is infinite in this context is known as _Galileo's paradox_.

A subset $A$ of a set $B$ is called a _proper_ subset, denoted $A\subsetneq B$ if $A\subseteq B$ but $A\neq B$.

>[!thm] Lemma.
>
>For every natural $n$, there is no bijection from $\{0,\dots,n\}$ to a proper subset of it.

>[!proof]+ Proof:
>
>By induction on $n$.
>
>The base case $n=0$ is vacuously true. Suppose that $n>0$ and let $N:=\{0,\dots,n\}$ and $N':=N\setminus\{n\}=\{0,\dots,n-1\}$.
>
>By contrapositive, suppose that $f:N\to X\subseteq N$ is a bijection. If $n\notin X$, then $f|_{N'}$ is a bijection onto $X$. But the domain has size $n-1$, so by the inductive hypothesis, $N=X$.
>
>If, on the other hand, $n\in X$, then define $g:N'\to X\setminus\{n\}$ by the rule
>
>$$
>g(i):=
>\begin{cases}
>f(i) & i\neq f^{-1}(n)\\
>f(n) & i=f^{-1}(n).
>\end{cases}
>$$
>
>$g$ is a bijection, so by inductive hypothesis, $N'=X\setminus\{n\}$. Adding the element $n$ to both sets, I get the sought equality.

>[!thm] Corollary.
>
>1. If $n$ and $m$ are two naturals witnessing the finiteness of the same set $X$, then $n=m$.
>2. $\mathbb N$ is infinite.

This really is the classic children's game "my number is your number plus one."

>[!proof] Proof of 2:
>
>By contradiction, suppose that $f:\mathbb N\to\{0,\dots,n\}$ is a bijection. Obviously $n>0$; then the function $f|_{\{0,\dots,n\}}$ is a bijection onto its image. The number $f(n+1)$ belongs to the domain but not the image and thus $f$ contradicts the lemma.

>[!note] Exercise.
>
>Prove that the set of prime numbers is an infinite subset of $\mathbb Z$.
>
>>[!hint]- Hint.
>>
>>Let $F$ be a finite collection of primes, then notice that $n:=\prod F$ and $n+1$ are relative primes. Conclude using FTA that no finite set of primes contains all primes.

I can finally formalize the idea that finite plus finite is finite:

>[!thm] Theorem.
>
>The union of finite sets is finite.

Other than the union, what other operations on sets preserve finiteness?

>[!thm] Theorem.
>
>The powerset of a finite set $X$ is finite. Moreover, it has size $2^{|X|}$.

>[!proof] Proofs in tutorials.

>[!note] *Hard* exercise.
>
>Prove from the definition that a subset of a finite set is finite.