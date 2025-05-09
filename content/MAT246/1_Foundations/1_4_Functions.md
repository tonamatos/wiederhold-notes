---
title: "1.4. Functions"
draft: false
---
A _function_ is a special type of relation and, consequently, a set itself.

>[!def] Definition.
>
>A relation $f\subseteq A\times B$ is called a _function from $A$ to $B$_ if for all $a\in A$, there is a unique $b\in B$ such that $(a,b)\in f$.
>
>1. I abbreviate these circumstances by the symbol $f:A\to B$.
>2. The set $A$ is called the _domain of $f$_, and $B$ is called the _codomain of $f$_.
>3. The element $b$ is called the _image of $a$ under $f$_ and always denoted by $f(a)$, and $a$ is called a _preimage of $b$_.

>[!note] Exercise.
>
>Determine which of these relations is a function from $\{0,1,2,3\}$ to $\mathbb N$.
>
>1. $\{(0,1),(0,2),(1,0),(2,0),(3,3)\}$
>2. $\{(0,1),(1,2),(2,3),(3,4)\}$
>3. $\{(0,0),(1,0),(2,0),(3,0)\}$
>4. $\{(0,0)\}$

>[!abstract] Examples.
>
>Let $X$ be a nonempty set.
>
>1. A function of the form $X\times\{c\}$ is called a _constant function_.
>2. The _identity on $X$_ is the function $\{(x,x):x\in X\}$. I denote this by $\operatorname{id}_X$.
>3. If $X\subseteq Y$, the function $\{(x,x):x\in X\}$ is called the _inclusion map from $X$ to $Y$_. I denote this by $X\hookrightarrow Y$.

>[!note] Exercises.
>
>1. In the examples above, are 2 and 3 the same? What is the difference?
>2. Rewrite all the above examples by defining the functions using only their _rule of correspondence_, that is, exhibiting a formula of the form $f(x)=\ ?$.

## Direct and inverse images

Recall that the symbol $\exists$ represents "exists." Also, I use the symbol $:=$ instead of $=$ when I want to remind the reader that I am not just claiming the sets are equal, I am **declaring** it as part of a definition.

>[!def] Definition.
>
>Let $f:X\to Y$ and $A$ be any set.
>
>1. The _direct image of $A$ under $f$_ is the set $f[A]:=\{y\in Y:\exists a\in A\ (a,y)\in f\}$.
>2. The _inverse image of $A$ under $f$_ is the set $f^{-1}[A]:=\{x\in X:\exists a\in A\ (x,a)\in f\}$.
>3. The set $f[X]$ is called the _image of $f$_. Some textbooks might use the word _range_.

My definition does not require any assumptions about the set $A$ and still makes perfect sense. However, most textbooks require $A\subseteq X$ for the direct image and $A\subseteq Y$ for the inverse image. How do these definition change in this case?

>[!warning] Warning:
>
>Most textbooks will use the notation $f(A)$ to denote the direct image of $A$ under $f$. In most cases (e.g., analysis, linear algebra, etc.) this will not cause confusion. But in general, this notation is **ambiguous** if, for instance, the domain of $f$ also consists of sets in the same language as its powerset. In this case, $f(A)$ could either mean the _image_ or the _direct image_, and these could have **different values**.

>[!note] Exercises.
>
>For the functions mentioned in the above examples, find the direct and inverse images of the following sets under those functions. Assume that $Y=\mathbb N$ and that $X=\{0,2,4,\dots\}$. Prove your claims if you want to learn.
>
>4. $\emptyset$.
>5. $\{0\}$.
>6. $\{0,1,2\}$.
>7. $\{0,2,4\}$.
>8. $X$.

## Injectivity and surjectivity

>[!def] Definition.
>
>A function $f:X\to Y$ is called:
>
>1. _injective_, or _one-to-one_ if for all $x,y\in X$, $f(x)=f(y)$ implies $x=y$.
>2. _surjective_, or _onto_, if $f[X]=Y$.
>3. _bijective_ if it is both injective and surjective.

Write the _contrapositive_ statement of the first definition above. When would you use the contrapositive rather than the direct statement? Write out the second definition as a _quantified_ statement.

