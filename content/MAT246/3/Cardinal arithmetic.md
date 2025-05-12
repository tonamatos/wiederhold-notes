---
title: "3.1. Cardinal arithmetic"
draft: true
---
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
>For the sake of intuition, you can think of _cardinal numbers_ as precisely the equivalence classes of this relation.

