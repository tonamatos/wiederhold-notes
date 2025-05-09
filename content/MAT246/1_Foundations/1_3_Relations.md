---
title: "1.3. Relations"
draft: false
---
>[!def] Definition.
>Any subset of $A\times B$ is called a _relation_.

There are many important types of relations such as _orders_, _equivalence relations_ and _functions_. For the first two, I am only interested in $A=B$, in which case I call it a _relation on_ $A$; for the latter, I often want different sets.
Depending on the context, I may abbreviate $(a,b)\in R$ by $aRb$.

>[!note] Exercise.
>
>Say $X$ is the set of students of MAT246. Determine which of the following are relations on $X$.
>1. Friendship. That is, $aRb$ if $a$ is a friend of $b$.
>2. Blood. That is, $aRb$ if $a$ is a blood relative of $b$.
>3. The empty set.
>4. Every possible ordered pair of students.
>5. The collection of subsets of $X$.
>6. The collection $R$ defined by the formula: $(a,b)\in R$ if and only if the first names of $a$ and $b$ start with the same letter of the alphabet.

## Equivalence relations

It will be more convenient to denote these types of relations by the symbol $\sim$ instead of $R$.

>[!def] Definition.
>
>A relation $\sim$ on a set $A$ is called an _equivalence relation on $A$_ if the following three things hold for any $a,b,c\in A$.
>1. $a\sim a$ (_Reflexivity_, like the reflection of a mirror);
>2. $a\sim b$ implies $b\sim a$ (_Symmetry_, as in, you can flip the order); and
>3. $a\sim b$ and $b\sim c$ implies that $a\sim c$ (_Transitivity_, like there are shortcuts in the transit).

>[!note] Exercise.
>
>In the examples above, decide which satisfy each of the three conditions in the definition. Which are equivalence relations? **Prove** all your claims.

>[!note] Exercise.
>Compare the above properties with the [[1_2_Elementary set theory#^thm-basic-subseteq|basic properties]] of the $\subseteq$ relation.

>[!note] Exercise.
>
>For each subset of the above properties (e.g., non-**reflexive**, **symmetric** and non-**transitive**), find an example of a relation that satisfies exactly those properties.

>[!hint] Hard problem.
>
>Given any relation $\sim$ on a set $X$, you should find it easy to _extend_ it (that is, to find a relation $\sim'\supseteq\sim$) to a relation that is reflexive. You should also find it straightforward to extend it to a reflexive relation. Can you extend it to a transitive one? How?
>
>**Note:** This problem has a "trivial" solution if you consider the equivalence relation $aRb$ iff $a,b\in X$. The idea is to find a solution that is _minimal_. That is, one that contains the given relation $\sim$, but no other relation satisfying the properties.