---
title: "2.5. Modular arithmetic"
draft: false
---
## Informal introduction

>[!warning] Note:
>
>Informal discussions are inadequate for these notes.

## The ring of congruences modulo $m$

>[!def] Definition.
>
>Let $m\geq1$ and $a,b\in\mathbb Z$. I say $a$ and $b$ are _congruent modulo $m$_, in symbols, $a\equiv_mb$ or $a\equiv b\pmod m$, if $m\mid a-b$.

>[!note] Exercise.
>
>Prove that $\equiv_m$ is an [[Relations#Equivalence relations|equivalence relation]] on $\mathbb Z$. Remind yourself of the definitions of _equivalence class_ and _quotient_ before you continue reading.

Instead of writing $[a]_{\equiv_m}$ to denote a class, I write $[a]_m$ in this chapter. I also denote by $\mathbb Z_m$ the quotient $\mathbb Z/\equiv_m$. Prove any of the examples below if you do not find them obvious.

>[!abstract] Examples.
>
>1. $[0]_2$ is the set of even numbers, and $[1]_2$ contains all odd numbers.
>2. The set $\mathbb Z_2$ has two elements.
>3. In general, $[a]_m=\{a+km:k\in\mathbb Z\}$ and $\mathbb Z_m$ has exactly $m$ elements.
>4. $a$ is divisible by $m$ if and only if $a\equiv_m0$.

The algebra of classes is straightforward to define. I leave to the reader proving that these are well-defined. Moreover, the reader should play around with these operations and convince themselves that the basic rules of arithmetic (_associativity_, _commutativity_, existence of an _additive_ and _multiplicative_ _inverses_, etc.) translate to this new structure as well. Instead of memorizing a long list of properties, the best way to learn to use this tool is to, well, **use it**.

>[!def] Definition.
>
>$$
>[a]_m+[b]_m:=[a+b]_m\qquad[a]_m\cdot[b]_m:=[a\cdot b]_m
>$$

As an example, I compute the multiplication table modulo 5.

### Multiplication Table Modulo 5

| × mod 5 | 0 | 1 | 2 | 3 | 4 |
|--------:|--:|--:|--:|--:|--:|
| **0**   | 0 | 0 | 0 | 0 | 0 |
| **1**   | 0 | 1 | 2 | 3 | 4 |
| **2**   | 0 | 2 | 4 | 1 | 3 |
| **3**   | 0 | 3 | 1 | 4 | 2 |
| **4**   | 0 | 4 | 3 | 2 | 1 |

>[!warning] Note:
>
>An informal discussion is presented during the lectures that compares different multiplication tables and highlights insights about major theorems in the field.

Having addition and multiplication, exponentiation follows.

>[!thm] Proposition.
>
>For every natural $k$, if $a\equiv_mb$, then $a^k\equiv_mb^k$.

>[!proof]- Proof idea:
>
>Induction on $k$.

>[!note] Exercise.
>
>Use the above to compute $497^{1003}$ mod $498$.

The following is proved as part of the above discussion in the lectures.

>[!thm] Proposition.
>
>Let $m\geq1$ and $a$ be integers. There exists $b\in\mathbb Z$ such that $ab\equiv_m1$ if and only if for every $t\in\mathbb Z$, there is a $b_t\in\mathbb Z$ such that $ab_t\equiv_mt$.

Such a $b$, when it exists, is unique modulo $m$ and is called the _inverse of $a$ modulo $m$_. I denote this element by $a^{-1}$. When this exists I also say that $a$ is _invertible modulo $m$_.

## Applications of modular arithmetic: divisibility criteria

A fact known to you since learning to write numbers in the _decimal system_ is that any natural number can be represented by its _decimal positional notation_ $d_0\cdots d_k$. Formally, this is means that

$$
n=\sum_{i=0}^kd_i\cdot10^i.
$$

I do not prove that this exists, but with the number-theoretic tools I have developed so far, it should be straightforward. For example, the number $4'574$ (i.e., "four thousand five hundred and seventy-four") really is $\underline4\cdot10^3+\underline5\cdot10^2+\underline7\cdot10^1+\underline4\cdot10^0$.

In this section, I show you how to quickly check if a number is divisible by a small integer based on its decimal representation.

>[!question] Reflect.
>
>Other numeral systems exist. For example _binary_, or _hexadecimal_. In your head, try rewriting this section in a different numeral system. How do the criteria change?

For the rest of the section, suppose that

$$
n=\sum_{i=0}^kd_i\cdot10^i.
$$

#### When is $n$ even?

>[!thm] Claim.
>
>$n$ is even (i.e. $2\mid n$) if and only if its unit digit, $d_0$ is even.

Indeed, reducing $n$ mod $2$ cancels out all positive powers of $10$, since $10$ is even and thus $10\equiv_20$. Concretely,

$$
n=d_k\cdot10^k+\cdots+d_1\cdot10+d_0\equiv_2d_k\cdot0+\cdots+d_1\cdot0+d_0=d_0;
$$

and the result follows.
#### When is $n$ divisible by $3$?

Proceed exactly as above, only this time the powers of $10$ do not cancel out. Instead, they become $1$'s since $10\equiv_31$. Hence,

$$
n=d_k\cdot10^k+\cdots+d_1\cdot10+d_0\equiv_3d_k\cdot1+\cdots+d_1\cdot1+d_0=\sum_{i=0}^kd_i.
$$

>[!thm] Claim.
>
>$n$ is divisible by $3$ if and only if the sum of its digits is divisible by $3$.

Moreover, notice that once you computed the sum of digits, you get a new, smaller number you want to check if it's divisible by $3$, so you can keep applying the same procedure over and over again until you have a single digit number, in which case this digit has to be either $0$, $3$, $6$ or $9$.

---

I leave the rest to you.
#### When is $n$ divisible by $4$?

When the number obtained from the last two digits, i.e. $d_1\cdot10+d_0$ is divisible by 4.

#### When is $n$ divisible by $5$?

When the last digit, $d_0$, is either zero or $5$.

#### When is $n$ divisible by $6$?

When it is divisible by $2$ and by $3$.

>[!hint]- Hint.
>
>Euclid's lemma.

#### When is $n$ divisible by $8$?

You need one more digit than for $4$.

#### When is $n$ divisible by $9$?

If you understood the one for $3$, this one should be clear.

#### When is $n$ divisible by $10$?

You probably know this one intuitively already. As a hint, only the last digit matters.

## Solving linear congruences

Consider the equation $ax=b$. In the integers, this almost never has a solution, since the integers have no _division_. In the rationals, this almost always has a solution, namely the _fraction_ $x=\frac ba$. The equation in $\mathbb Z_m$ however is much more interesting. I now show you how to solve it. Consider

$$
ax\equiv_mb.
$$

Where to begin? A common technique in mathematics is to assume that a solution exists, and try to derive properties from it. This either

- produces enough properties so that you can narrow down and eventually find the solution; or
- yields a contradiction, in which case you can guarantee no solution exists.

>[!warning] Note:
>
>In the lectures, I guide students through this process interactively. Here I just spoil the whole solution for the sake of completeness.

### Solution criterion

>[!thm] Theorem.
>
>The congruence has a solution if and only if $\gcd(a,m)\mid b$.

>[!proof]+ Proof:
>
>$\boxed{\Longrightarrow}$ Suppose that $x$ is a solution. Since $\gcd(a,m)\mid a$ and $m\mid b-ax$, linearity gives us $\gcd(a,m)\mid b$.
>
>$\boxed{\Longleftarrow}$ Now suppose that $\gcd(a,m)\mid b$. By [[GCD and LCM#Bézout's identity|Bézout's identity]], there are integers $s$ and $t$ such that
>
>$$
>\gcd(a,m)=as+mt\equiv_mas.
>$$ 
>
>The fact that $x:=\frac{sb}{\gcd(a,m)}$ is (an integer and) a solution is left to the reader.

Notice that, by the above discussion, the congruence **always** has a solution when $a$ is invertible. Moreover, a solution is $a^{-1}b$, where $a^{-1}$ is the inverse of $a$ mod $m$.

>[!thm] Corollary.
>
>The integer $a$ is invertible modulo $m$ if and only if it is [[GCD and LCM|relatively prime]] with $m$.

You now have a criterion to decide if a solution exists or not. But from the argument above, it is not immediately obvious how to find it explicitly.
### Finding a solution in five easy steps

1. Use the [[GCD and LCM#The extended Euclidean algorithm|extended Euclidean algorithm]] to compute $\gcd(a,m)$.
2. Check if it divides $b$.
3. If it doesn't, there is no solution; if it does, proceed to Step 4.
4. Continue with the extended Euclidean algorithm and find $s$ and $t$ such that $\gcd(a,m)=as+tm$. Discard $t$, as you don't need it.
5. If you understand the $\boxed{\Longleftarrow}$ part of the proof above, you should now know how to find a solution $x$.

>[!note] Exercise.
>
>Find the inverse of $2$ mod $17$.

## Solving linear systems

A **must-know** technique for modular arithmetic is presented in this section. I first show you how to solve two congruences simultaneously, then it is your job to use induction to generalize this to multiple congruences. If you have made it this far, you should find this task straightforward.

>[!thm] Lemma.
>
>Let $a,b$ and $n,m\geq1$ be integers. There exists an integer $x$ such that **both** $x\equiv_ma$ **and** $x\equiv_nb$ if and only if $a\equiv b\pmod{\gcd(n,m)}$. Moreover, if $x$ exists, then it is unique modulo $\operatorname{lcm}(n,m)$.
>
>In particular, if $n\perp m$, then such an $x$ always exists, regardless of $a$ and $b$, and is unique modulo $nm$.

>[!proof]+ Proof:
>
>$\boxed{\Longrightarrow}$ Suppose there is such an $x$. Then, there must be $s,t\in\mathbb Z$ such that $x=sm+a=tn+b$, from where $a-b=tn-sm$. The latter is a linear combination of $n$ and $m$, thus by _linearity_ $\gcd(n,m)\mid a-b$. This is the definition of $a\equiv b\pmod{\gcd(n,m)}$.
>
>$\boxed{\Longleftarrow}$ Now suppose that $a\equiv b\pmod{\gcd(n,m)}$, that is, $c\gcd(n,m)=a-b$ for some integer $c$. By Bézout's identity, there are integers $k$ and $\ell$ such that $\gcd(n,m)=nk+m\ell$. Thus, $a-b=n(kc)-m(-c)$, from where $a+m(-\ell c)=n(kc)+b$; let me call this integer $x$. Reducing mod $n$ and mod $m$, it is clear that $x$ is a solution to the system of congruences.

### An example

I will solve the system

$$
\begin{cases}
x\equiv5\pmod{21}\\
x\equiv19\pmod{56}
\end{cases}
$$
using two different techniques.

#### Technique: brute force

First, use FTA to compute $\gcd(21,56)=\gcd(3\cdot7,2^3\cdot7)=7$ and notice that $5\equiv_719$, so there is a unique solution mod $2^3\cdot3\cdot7$.

I really want to find an element in the intersection $[5]_{21}\cap[19]_{56}$, so I can list out representatives until there is a match:

$x=5,26,47,68,89,110,\boxed{131}$
$x=19,75,\boxed{131}$

Therefore, $x$ is a solution to the system if and only if $x=131+2^3\cdot3\cdot7k$ for some integer $k$. Or, in other words,

$$
[5]_{21}\cap[19]_{56}=\{131+2^3\cdot3\cdot7k:k\in\mathbb Z\}
$$

#### Technique: substitution

Start by picking the congruence with the largest modulus (why?) and rewrite it as $x=56s+19$ for some integer $s$. Reducing mod $21$, we have $x\equiv14s+19\pmod{21}$. The final step is left to the reader.

### The Chinese remainder theorem

For the scope of this course, it is important that you know that this theorem exists and that you can prove it with the material covered so far. For more applications, details and variations, you can consult my notes for [[MAT315]].

>[!thm] Chinese remainder theorem (CRT).
>
>If $m_1,\dots,m_k$ are pairwise coprime and $a_1,\dots,a_k\in\mathbb Z$, then there is an integer $x$, unique mod $m_1\cdots m_k$ such that for all $i$, $x\equiv_{m_i}a_i$.

>[!proof] Proof idea:
>
>Use induction on $k$ and apply the above lemma.

>[!warning] Warning:
>
>Careful when using online calculators (or worse, AI) to compute these solutions. They are often wrong or incomplete. In the lectures, I show how the top 3 Google searchable calculators give wrong answers.