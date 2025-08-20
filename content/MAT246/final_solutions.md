---
title: "Final solutions"
draft: false
---
1. Let $X$ be an infinite set.

	(a) Could $\mathcal P(X)$ be countable?

	(b) Given any two subsets of $X$, $A$ and $B$, define $A\sim B$ if and only if $(A\setminus B)\cup(B\setminus A)$ is a countable subset of $X$. Prove that $\sim$ is an equivalence relation on $\mathcal P(X)$.

**Solution:**

(a) No. By Cantor's theorem, $|\mathbb N|\leq|X|<|\mathcal P(X)|$.

(b) From PS1: For reflexivity, notice that, $A\bigtriangleup A=\emptyset$ is ~~finite~~ countable, thus $A\sim A$.

If $A\sim B$ then, $B\bigtriangleup A=A\bigtriangleup B$ is ~~finite~~ countable, and hence $B\sim A$, so we have symmetry.

Suppose that $A\sim B$, $B\sim C$. First, notice that

$$
A\setminus C\subseteq(A\setminus B)\cup(B\setminus C)\quad\text{ and }\quad C\setminus A\subseteq (C\setminus B)\cup(B\setminus A).
$$

Finally,

$$
A\bigtriangleup C=(A\setminus C)\cup(C\setminus A)
$$
$$
\subseteq (A\setminus B)\cup(B\setminus C)\cup(C\setminus B)\cup(B\setminus A)
$$
$$
=(A\setminus B)\cup(B\setminus A)\cup(B\setminus C)\cup(C\setminus B)
$$
$$
=(A\bigtriangleup B)\cup(B\bigtriangleup C)
$$
is a ~~finite~~ countable set, and thus $A\sim C$.

---

2. 
	(a) State the fundamental theorem of arithmetic.

	(b) Let $n$ be a positive integer. Show that there exist naturals $p$ (possibly zero) and $q>0$ such that $n=2^p(2q-1)$.

	(c) Prove that the least common multiple of two relatively prime numbers $a$ and $b$ is equal to their product $ab$. In symbols, given positive integers $a$ and $b$ such that $\gcd(a,b)=1$, show that $\operatorname{lcm}(a,b)=ab$. You may **not** use the stronger result that $\gcd(a,b)\operatorname{lcm}(a,b)=ab$ unless you prove it first.

**Solution:**

(b) Let $p=\operatorname{mult}_2(n)$. Then $n/2^p$ must be odd, say $2q-1$ for some $q>0$. The result follows.

(c) **With FTA:** Since $\gcd(a,b)=1$, for every prime $p$, $p\mid a$ if and only if $p\not\mid b$. In other words, $\operatorname{mult}_p(a)>0$ if and only if $\operatorname{mult}_p(b)=0$. Consequently, $\max\{\operatorname{mult}_p(a),\operatorname{mult}_p(b)\}=\operatorname{mult}_p(a)+\operatorname{mult}_p(b)$.

Therefore, by FTA,

$$
\operatorname{lcm}(a,b)=\prod_pp^{\max\{\operatorname{mult}_p(a),\operatorname{mult}_p(b)\}}=\prod_pp^{\operatorname{mult}_p(a)+\operatorname{mult}_p(b)}=ab.
$$

**With Bézout:** Clearly, $a,b\mid\operatorname{lcm}(a,b)\mid ab$. By Bézout, there are $s,t$ integers with $1=as+bt$, so

$$
\operatorname{lcm}(a,b)=a\frac{b\operatorname{lcm}(a,b)}bs+b\frac{a\operatorname{lcm}(a,b)}at=ab\left(\frac{\operatorname{lcm}(a,b)}bs+\frac{\operatorname{lcm}(a,b)}at\right),
$$

from where $ab\mid\operatorname{lcm}(a,b)$. Hence, they are equal.

---

3. (a) Define what it means for a graph to be _connected_ and what it means for a graph to be a _tree_.
	(b) Argue, using a formal proof, that a connected graph with $n$ vertices and $n-1$ edges must be a tree.

**Solution:**

(a) Connected means any two vertices are the endpoints of some path/walk contained the graph. A tree is a connected graph with no cycles.

(b) I will prove by contradiction that a connected graph with _at most_ $n-1$ edges is a tree. By WOP, suppose that $G$ is a counterexample with the least positive number of cycles. Removing an edge from any cycle produces a graph with fewer cycles and $n-2$ edges, so by minimality it must either be a tree or be disconnected. But removing an edge from a cycle cannot disconnect the graph (a short justification is sufficient) and every tree has exactly $n-1$ edges (students can assume this, but having a proof is nice); a contradiction.

---

4. Let $A,B$ be subsets of $\mathbb R^n$. Prove or disprove each of the following.
	(a) $\operatorname{int}A=\mathbb{R}^n\setminus\overline{\mathbb{R}^n\setminus A}$. **True.**
	(b) $\overline{A\cup B}=\overline{A}\cup\overline{B}$. **True.**
	(c) If $A$ is a closed set, then $\overline{\operatorname{int}A}=A$. **False.**

---

5. Prove that out of any five lattice points, there are two whose midpoint is also a lattice point. In symbols, let $\{(x_i,y_i):i<5\}\subseteq\mathbb Z\times\mathbb Z$ be any five distinct lattice points on the plane. Argue that there exist $i<j<5$ such that $\left(\frac{x_i+x_j}2,\frac{y_i+y_j}2\right)\in\mathbb Z\times\mathbb Z$.

**Solution:**

By the pigeonhole principle, out of the five integers $x_i$, three must have the same parity. The sum of any two of these three is even. The same for $y_i$. Again by the pigeonhole, two out of these three two have $y$-coordinates with the same parity. These two points are such that their midpoint is an integer lattice point.

In symbols, the function $f:\{x_i:i<5\}\to\{0,1\}$ such that $f(x_i):=x_i\pmod2$ must have a _fiber_ of size 3 or more, that is $|f^{-1}\{b\}|\geq3$ for $b=0,1$. Without loss of generality, suppose that $x_0,x_1,x_2$ have the same parity. Now define $g:\{x_i:i<3\}\to\{0,1\}$ given by $g(x_i):=y_i\pmod2$. By the pigeonhole principle, $g$ is not injective, thus say $g(x_0)=g(x_1)$. But this means that $x_0+x_1$ is even and that $y_0+y_1$ is even, in other words, $\left(\frac{x_0+x_1}2,\frac{y_0+y_1}2\right)\in\mathbb Z\times\mathbb Z$.

---