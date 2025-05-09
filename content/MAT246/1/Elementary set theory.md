---
title: "1.2. Elementary set theory"
draft: false
---
Following the discussion in the [[Introduction|Introduction]], I will assume that we intuitively know what a _set_ is, and that I can reasonably talk about the relation $\in$ in the language of sets. I write $x\in A$ if the set $x$ is _element of_ $A$, or in other words if $x$ _belongs to_ $A$.
## Basic properties of sets

I denote by $\emptyset$ the set with no elements. That is, the set satisfying that (recall that $\forall$ represents "for all")

$$
\forall x,\quad x\notin\emptyset.
$$

>[!def] Definition.
>
>Given two sets $A$ and $B$, we say _$A$ is a subset of $B$_, or _$A$ is contained in $B$_, in symbols, 
>$$
>A\subseteq B
>$$
>if for all $x$, $x\in A$ implies $x\in B$.
>I say the sets $A$ and $B$ are _equal_, in symbols,
>$$
>A=B,
>$$
>if they are subsets of each other. That is, $A\subseteq B$ and $B\subseteq A$.

>[!info] Remark.
>
>The sets $A$ and $B$ are equal if and only if for all $x$,
>$$
>x\in A\iff x\in B.
>$$ 

This is a great moment to develop some skills that will serve you in learning math in general. Whenever encountering a **definition** for the first time, always do the following exercise:

>[!hint] Exercise scheme.
>1. What is the negation of the definition? In this case, what does it mean for $A$ to **not** be a subset of $B$? We can use the symbol $A\not\subseteq B$.
>2. What are examples and non-examples of the situation? In this case, can you say list out all subsets of the set $\{0,1\}$?
>3. Write down a proof of a set being a subset of another set. Write down a proof of a set not being subset of a given set. What techniques did you use to prove these different statements?

>[!thm] Basic properties of subsets.
>
>For any sets $A,B$ and $C$,
>1. $A\subseteq A$ (_Reflexivity_);
>2. $\emptyset\subseteq A$ (_Minimum element_ / _Vacuous truth_);
>3. if $A\subseteq B$ and $B\subseteq C$, then $A\subseteq C$ (_Transitivity_); and
>4. if $A\subseteq B$ and $B\subseteq A$, then $A=B$ (_Anti-symmetry_).
^thm-basic-subseteq

>[!note] Exercise.
>Prove the above properties from the definition.

## Basic operations on sets

Below, _family_ is just another word for set, to avoid saying "set of sets."

>[!def] Definition.
>
>The _powerset_ of a set $X$, denoted by $\mathcal P(X)$, is the family of all subsets of $X$.

>[!abstract] Examples.
>1. $\mathcal P(\emptyset)=\{\emptyset\}$.
>2. $\mathcal P(\{\emptyset\})=\{\emptyset,\{\emptyset\}\}$.

In this course, I do not formally define the _ordered pair_ $(a,b)$, but all you need to know about it is that $(a,b)=(c,d)$ if and only if $a=c$ and $b=d$. So, for instance, $(0,1)\neq(1,0)$ even though $\{0,1\}=\{1,0\}$.
 
>[!def] Definition.
>
>Let $A$ and $B$ be sets. I define the following operations.
>1. The _union_ $A\cup B=\{x:x\in A\lor x\in B\}$. ($\lor$ represents "or")
>2. The _intersection_ $A\cap B=\{x:x\in A\land x\in B\}$. ($\land$ represents "and")
>3. The _Cartesian product_ $A\times B=\{(a,b):a\in A\land b\in B\}$.
>4. The _difference_ $A\setminus B=\{a\in A:a\notin B\}$.

>[!note] Exercise.
>
>Show that for any $A$, $B$ and $C\in\{A,B\}$,
>$$
>A\cap B\subseteq C\subseteq A\cup B.
>$$

## Finite sets (informal discussion)

This definition is **informal** and this concept will be formalized in a later chapter, but it is good enough to give examples and exercises now.

>[!def] Definition.
>
>A set $A$ is _finite_ if there exist $x_1,x_2,\dots,x_n$ such that $A=\{x_1,x_2,\dots,x_n\}$.
>
>A set is _infinite_ if it is not finite.

>[!thm] Proposition.
>
>1. Subsets of finite sets are finite.
>2. The union of two finite sets is finite.

## The lattice of subsets

>[!warning] Note:
>
>The concept of _lattice_ is not explicitly part of the course, but several important examples are seen in the lectures. These follow informal discussions (and are hence inadequate for these notes) that summarize large portions of theory.