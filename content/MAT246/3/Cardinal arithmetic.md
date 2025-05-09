---
title: "3.1. Cardinal arithmetic"
draft: false
---
>[!fail] Incomplete.

---

## Injectivity and surjectivity

>[!def] Definition.
>
>A function $f:X\to Y$ is called:
>
>1. _injective_, or _one-to-one_ if for all $x,y\in X$, $f(x)=f(y)$ implies $x=y$.
>2. _surjective_, or _onto_, if $f[X]=Y$.
>3. _bijective_ if it is both injective and surjective.

Write the _contrapositive_ statement of the first definition above. When would you use the contrapositive rather than the direct statement? Write out the second definition as a _quantified_ statement.

>[!note] Exercise.
>
>Out of all the examples mentioned in [[Functions|this page]], decide which ones are injective, which ones are surjective? Write a proof for each claim.

>[!hint] Problem.
>
>Let $f:X\to Y$ be a surjective function and define $x\sim y$ if $f(x)=f(y)$. Prove that $\sim$ is an equivalence relation on $X$. Where is surjectivity needed?
>
>Conversely, show that if if $\sim$ is an [[Relations#Equivalence relations|equivalence relation]] on $X$, then there is a set $Y$ and a surjective function $f: X\to Y$ such that $f(x)=f(y)$ if and only if $x\sim y$.

>[!hint] Problem.
>
>I say $P$ is a _partition_ of $X$ if $\bigcup P=X$, $\emptyset\notin P$ and the elements of $P$ are pairwise disjoint. Prove that any quotient on $X$ is a partition of $X$.
>
>Conversely, show that for any partition, there is an equivalence relation whose quotient is equal to the partition.

## An algebra of functions

For this section, suppose that $f:A\to B$ and $g:B\to C$ are functions.

>[!def] Definition.
>
>The _composition of $f$ and $g$_ is the function $g\circ f:A\to C$ given by $g\circ f(a):=g(f(a))$.

>[!note] Exercises.
>
>1. Prove that the composition of injective (surjective) functions is again injective (surjective).
>
>2. Assume that $g\circ f$ is injective (surjective). What can you say about the injectivity (surjectivity) of $f$ and $g$? 

If $f$ is bijective, the _inverse of $f$_ is the function $f^{-1}=\{(b,a):(a,b)\in f\}$ from $B$ to $A$. Why is bijectivity, that is the fact that $f$ be both injective and surjective, important here?

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
>For the sake of intuition, you can think of a _cardinal number_ as precisely the equivalence classes of this relation.

