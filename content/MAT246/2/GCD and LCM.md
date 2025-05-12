---
title: "GCD and LCM"
draft: true
---
>[!def] Definition.
>
>Let $a$ and $b$ be naturals that are not both zero. The _greatest common divisor_ of $a$ and $b$}, denoted $\gcd(a,b)$ is the largest integer that divides both $a$ and $b$. Similarly, the _least common multiple_, denoted $\operatorname{lcm}(a,b)$ is the smallest integer that is divided by every element both.
>
>Two integers $a$ and $b$ are called _coprime_ or _relatively prime_ if $\gcd(a,b)=1$. I denote this phenomenon by $a\perp b$.

>[!note] Exercises.
>
>1. If a prime $p$ does not divide $a$, then $p\perp a$.
>2. Prove that consecutive integers are coprime.
>3. If $p$ is prime and $\gcd(p,n)>1$, then $p\vert n$. If, moreover $n$ is also prime, then necessarily $p=n$.
>4. Different primes are always coprime. Show with an example that the converse does not hold. That is, show that coprime numbers need not be prime.

## The Euclidean algorithm

I now introduce on of many examples in mathematics where the statement of the theorem is not that important, but the proof is crucial to understand the material.

>[!thm] Theorem (Euclidean algorithm).
>
>Assume that, for naturals $a$ and $d\geq1$, the Q-R formula gives $a=dq+r$. Then,
>
>$$
>\gcd(a,d)=\gcd(d,r)
>$$

>[!question] Reflect.
>
>Again, spend some time thinking why is this called an _algorithm_. There aren't any steps.

>[!note] Exercise.
>
>Use the theorem to implement this as an actual computer program that computes the $\gcd$.
>
>>[!check]- Solution.
>>
>>Recursion is **elegant**.
>>
>>```python
>>def gcd(a, b):
>>	if b==0:
>>		return abs(a) # absolute value
>>	return gcd(b, a%b)
>>```

I will answer the important question of how to use this in the following subsection. More importantly, I will skip the proof for now, since understanding a particular case should make the proof idea apparent.

### The extended Euclidean algorithm

>[!warning] Note:
>
>These sort of examples with many moving steps are best understood during a **live lecture**, not reading them on a static site.

Let me do an example where I compute $\gcd(56,15)$ using the Euclidean algorithm.

First I divide and find the remainder: $56=15\cdot3+\boxed{11}$. Thus, $\gcd(56,15)=\gcd(15,11)$.

Now I repeat these steps until I reach something trivial. **Note:** if you do not know _why_ this must happen eventually, you have not understood the theorem and should go back to the previous section.

$$
15=11\cdot1+4\qquad\text{dividing }15\text{ by }11
$$
$$
11=4\cdot2+3\qquad\text{dividing }11\text{ by }4
$$
$$
4=3\cdot1+\boxed1\qquad\text{dividing }4\text{ by }3
$$
$$
3=1\cdot3+0
$$

The last remainder before reaching zero is **always** the $\gcd$; in this case $\gcd(56,15)=1$.

>[!question] Reflect.
>
>What would happen if I wanted to compute $\gcd(15,56)$ instead? Obviously it should give me the same answer, but the algorithm does something different, since it always divides the left by the right. How does this work?

Notice that I can do the steps in reverse and obtain the remainder as a linear combination of the two previous rows. Repeatedly doing this backwards, I can write the final remainder in terms of the first two terms, $56$ and $15$. The math paragraph below should be read from bottom to top, so it aligns with the math paragraph above.

$$
1=(-4)56+(3)15\qquad\text{in terms of }56\text{ and }15
$$
$$
1=(3)15+(-4)11\qquad\text{in terms of }15\text{ and }11
$$
$$
1=(-1)11+(3)4\qquad\text{in terms of }11\text{ and }4
$$
$$
\boxed1=4+(-1)3\qquad\text{in terms of }4\text{ and }3
$$

Therefore, $\gcd(56,15)=1=(-4)56+(3)15$. The fact that the $\gcd$ is a linear combination of the numbers can be proved more directly too. This is the purpose of the next section.

## Bézout's identity

Here is an **important** result that can be proved using [[Induction]].

>[!thm] Theorem (Bézout's identity)
>
>The least linear combination of two integers, not both zero, $a$ and $b$ is precisely $\gcd(a,b)$.
>
>In particular, $a$ and $b$ are coprime if and only if there exist integers $x,y$ such that $ax+by=1$.

>[!note] Exercise.
>
>Prove that the product of two relative primes that divide $n$, divides $n$.
 
The following consequences follow rather easily, but are non trivial if proved from just the definitions.

>[!note] Exercise (Euclid's lemma 1).
>
>If $p$ is prime and $p\vert ab$, then either $p\vert a$ or $p\vert b$.
 
The same idea can be used to prove the slightly more general result:
 
>[!thm] (Euclid's lemma 2)
>
>Suppose that $a\perp b$ and $a\vert bc$, then $a\vert c$.

>[!note] Exercise.
>
>Prove that for every integer at least 5 of the form $n=6k\pm1$, $n^2-1$ is divisible by 24.