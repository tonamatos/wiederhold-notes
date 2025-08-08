---
title: "2.7. Non-linear congruences"
draft: false
---
The exercise presented here connects the most important results seen so far. It is a summary.

## Exercise.

>Find all integers $x$ such that
>
>$$
>717x^2\equiv23^{95}\pmod{970}.
>$$

>[!hint]- Hint.
>
>$97$ is a prime.

>[!warning] Warning:
>
>As always, if you read the solution before trying to solve the exercise yourself, you are likely wasting your time.

### Solution.

#### Step 1: Linearize

I use the Euclidean algorithm to find the inverse of $717$ mod $970$. First, I iterate the Q-R formula:

| Step | Equation                       |
| ---- | ------------------------------ |
| 1    | $970 = 717 × 1 + 253$          |
| 2    | $717 = 253 × 2 + 211$          |
| 3    | $253 = 211 × 1 + 42$           |
| 4    | $211 = 42 × 5 + \boxed1$       |
| 5    | $42 = 1 × 42 + 0$ *(optional)* |

Second, I plug the remainders back in reverse order:

| Step | Equation                                                    |
| ---- | ----------------------------------------------------------- |
| 4    | $1 = 211 + (-5)42$                                          |
| 3    | $= 211 + (-5) [253 + (-1) 211] = 6 × 211 + (-5)253$         |
| 2    | $= 6  [717 + (-2) 253] + (-5) 253 = (6) 717 + (-17)  253$   |
| 1    | $= (6) 717 + (-17) [970 + (-1) 253] = (23) 717 + (-17) 970$ |

Reducing mod $970$, I have $1\equiv23\cdot717$, hence the inverse is $23$. Substituting $y=x^2$, the congruence to solve becomes

$$
y\equiv23^{96}\pmod{970}.
$$

#### Step 2: Divide

Factoring $970=2\cdot 5\cdot 97$. By the Chinese remainder theorem, solving the above is equivalent to solving the system

$$
y\equiv23^{96}\pmod2\qquad
y\equiv23^{96}\pmod5\qquad
y\equiv23^{96}\pmod{97}
$$

The middle congruence easily reduces to $y\equiv_223^{96}\equiv_21^{96}=1$. And the only integer whose square is 1 mod 2 is 1, thus $x\equiv_21$.

The right congruence simplifies to $y\equiv_523^{96}\equiv_5(-2)^{96}=2^{96}$.

>[!hint] Hint.
>
>The latter can easily be solved by cases since $5$ is small. However, if the prime factor were large, such as the case of $97$, guessing and checking is unfeasible.

By Fermat's little theorem, $2^4\equiv_5 1$, and since $4\mid96$,

$$
2^{96}=2^{4\cdot(96/4)}=(2^4)^{96/4}\equiv_51^{96/4}=1.
$$

In the lectures I prove that the only square roots of 1 mod a prime are $\pm1$. Then, $x\equiv_51,4$.

Now, again by Fermat's little theorem, $23^{96}\equiv1\pmod{97}$. Therefore, the system reduces to

$$
x\equiv1\pmod2\qquad x\equiv1,4\pmod5\qquad x\equiv1,96\pmod{97}
$$

>[!hint] Hint.
>
>What do the commas in the last two congruences mean precisely? I am no longer trying to solve one system, but **four**. Here is the precise logical statement:
>
>$$
>\left(x\equiv_21\quad\land\quad
>x\equiv_51\quad\land\quad
>x\equiv_{96}1\right)
>$$
>
>$$
>\lor
>$$
>
>$$
>\left(x\equiv_21\quad\land\quad
>x\equiv_51\quad\land\quad
>x\equiv_{96}95\right)
>$$
>
>$$
>\lor
>$$
>
>$$
>\left(x\equiv_21\quad\land\quad
>x\equiv_54\quad\land\quad
>x\equiv_{97}1\right)
>$$
>
>$$
>\lor
>$$
>
>$$
>\left(x\equiv_21\quad\land\quad
>x\equiv_54\quad\land\quad
>x\equiv_{97}96\right)
>$$

#### Step 3: Conquer

Clearly $x=1$ solves one of the systems, so by the Chinese remainder theorem, $x=1$ is the only solution mod $970$ to the first system. $x=-1$ is a solution to another one of the systems.

Since the first congruence only says $x$ is odd, I omit it to reduce clutter. The remaining two systems are

$$
x\equiv1\pmod5\qquad
x\equiv96\pmod{97}
$$

$$
x\equiv4\pmod5\qquad
x\equiv1\pmod{97}
$$

The top one is solved by taking the second congruence as $x=97k-1$ for some $k$, and plugging it into the second one: $1\equiv x=97k-1\equiv 2k-1\pmod{5}$, from where $k=5\ell+1$ for some $\ell$. Hence, $x=97(5\ell+1)-1$; but I want $x$ to be odd, so I can pick $\ell=1$ and get $x=581$.

>[!question] Reflect.
>
>**Any** value of $\ell$ that makes $97(5\ell+1)-1$ odd produces a valid solution $x$. You have understood how to solve systems of congruences when you can explain why. Also, why did I plug the second congruence into the first one and not the other way around?

The bottom one is solved exactly the same way to get $x=389$.

#### Step 4: Multiply

By the Chinese remainder theorem, the final answer is

$$
x\equiv1,389,581,969\pmod{970},
$$

so the set of all integer solutions is

$$
\boxed{\{970n+m:n\in\mathbb Z,m\in\{1,389,581,969\}\}}.
$$

---

>[!note] Exercise.
>
>What is the shortest computer program you can write that solves this problem? What about the fastest?
>
>>[!check]- Solution.
>>
>>```python
>># This is Python3.
>>*[x for x in range(970) if (717*x**2)%970 == 23**95%970]
>>>>>1, 389, 581, 969
>>```

>[!note] Exercise.
>
>Try solving the same initial congruence but with $x^3$ instead of $x^2$. Do you expect to find more solutions or fewer mod $970$?