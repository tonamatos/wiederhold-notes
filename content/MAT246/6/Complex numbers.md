---
title: "6. Complex numbers"
draft: false
---
## Algebraic motivation

In $\mathbb N$, I was unable to solve all equations involving _addition_ (which is repeated successor), for instance

$$
5+x=2,
$$

so I introduced an equivalence relation that "emulates" what the difference between two naturals is, and that is how I constructed the integers $\mathbb Z$. Now, I can solve the above equation $5+\boxed{-3}=2$, essentially by inventing _negative_ numbers.

Not all equations involving _multiplication_ (which is repeated addition) have integer solutions (the ones that do are studied in the [[Divisibility]] chapter), for instance

$$
2\cdot x=3
$$

has no solutions in $\mathbb Z$. I followed a similar construction and solved this by introducing _fractions_: $2\cdot\boxed{\frac32}=3$ in the bigger space of rationals $\mathbb Q$.

But even in $\mathbb Q$, not all equations have solutions, for instance those involving _powers_ (repeated multiplication):

$$
x^2=2
$$

This construction is out of scope of this course as it is considerably different and more complicated, but the general idea holds: I invented _positive roots_ to solve it: $(\sqrt2)^2=2$. This much bigger space (this one is uncountable) is the reals $\mathbb R$.

What equations have no solutions in the reals? One example involves _negative roots_, like $x^2=-1$. So to construct the next stage, the complex numbers $\mathbb C$, I simply invent a solution for it and call it the _imaginary unit_ $i$.

>[!info] Opinion.
>
>I argue that the only reason this seems more arbitrary (or even like I'm cheating) is because of habit, and not due to any theoretical barrier. Remember how negative numbers make no sense in elementary school and now you find them trivial. The same way, had you been introduced to imaginary numbers earlier, you would find them just as **sensible**.

I will skip the more formal construction of $\mathbb C$ as a quotient over $\mathbb R\times\mathbb R$ in favor of a simpler construction of more immediate use.

The set of complex numbers is given by

$$
\mathbb C:=\{a+ib:a,b\in\mathbb R\}
$$

where $i^2=-1$. The operations are given by

$$
(a+ib)+(c+id)=(a+c)+i(b+d)
$$
$$
(a+ib)\cdot(c+id)=(ac-bd)+i(ad+bc)
$$

Complex numbers are used in many places, from electrical engineering to solving difficult **real** integration problems and, perhaps surprisingly, in number theory and combinatorics:

>[!note] **Very hard** exercise.
>
>(Andreescu-Feng) In how many ways can you pick distinct positive integers less than $2000$ such that their sum is a multiple of 5?
>
>>[!check]- Solution.
>>
>>[This 3b1b video](https://youtu.be/bOXCLR3Wric?si=IctOBc5as_AXBhlc) has the best explanation.

Notice that if you restrict the product to multiplying only reals on the left, then this is a real scalar product on the set of complex numbers. Moreover, the following is true.

>[!abstract] Remark.
>
>If you know linear algebra, prove that $(\mathbb C,+,\cdot|_{\mathbb R\times\mathbb C})$ and $\mathbb R^2$ are isomorphic as vector spaces over $\mathbb R$.

As I will show later, the space $\mathbb C$ is also a topological space with the metric described, and this space is identical (formally, this is called _homeomorphic_) to $\mathbb R^2$. The result below is much more important for my purposes.

>[!thm] Theorem.
>
>$(\mathbb C,+,\cdot)$ is a [[Fields|field]].

>[!proof]+ Proof:
>
>I will only proof the interesting parts which is first noting that $0$ and $1$ are identity elements for the sum and product respectively, and also the existence of inverses:
>
>If $a+ib\neq 0$, then
>
>$$
>(a+ib)^{-1}=\frac a{a^2+b^2}-i\frac b{a^2+b^2}.
>$$

An important difference between $\mathbb R$ and $\mathbb C$ is that the former is a _linearly ordered_ field, but the latter is not. There are other insightful differences more relevant to algebra, such that the fact that all complex polynomials have roots. This is the _fundamental theorem of algebra_, which I do not cover in this course.

>[!note] Exercise.
>
>Prove that there is no _strict linear order_ (that is, an irreflexive, asymmetric, transitive relation where any two distinct elements are related) on $\mathbb C$ that preserves the operations.
>
>>[!check]- Solution.
>>
>>By contradiction, suppose that $\prec$ is such a relation on $\mathbb C$. Then compare $i$ and $0$. Without loss of generality, suppose that $0\prec i$. But then, $0=0^2\prec i^2=-1$.
>>
>>>[!warning] This is **not** yet a contradiction, since $\prec$ is an arbitrary order that might just think that $-1$ is a "positive" number.
>>
>>Squaring both sides again, $0\prec(-1)^2=1$, from where $0=0-0\prec 1-1=0$. Now this contradicts the irreflexivity.

The first result about the complex numbers I will prove to you is that square roots exist.

>[!thm] Proposition.
>
>For all $z\in\mathbb C$, there is a $w\in\mathbb C$ such that $w^2=z$.

>[!proof] Proof:
>
>Suppose that $z=a+ib$. It is sufficient to find reals $x$ and $y$ such that
>
>$$
>(x^2-y^2)+i(2xy)=(x+iy)^2=a+ib\quad\iff\quad\begin{cases}x^2-y^2=a\\2xy=b\end{cases}.
>$$
>
>Squaring and adding, $(x^2+y^2)^2=a^2+b^2$, from where $x^2+y^2=\sqrt{a^2+b^2}$, meaning I have reduced the problem to applying the quadratic formula (for real roots). Therefore, $x=\pm\alpha$ and $y=\pm\beta$ where
>
>$$
>\alpha=\sqrt{\frac{a+\sqrt{a^2+b^2}}2}\qquad\beta=\sqrt{\frac{-a+\sqrt{a^2+b^2}}2}.
>$$
>
>Finally, the two (possibly equal) roots are $w=\pm(\alpha+\mu i\beta)$ where $\mu=\begin{cases}1&b\geq0\\-1&b<0\end{cases}$.

>[!abstract] Example.
>
>The square roots of $z=8-6i$ are given by $\alpha=3,\beta=1$, and thus $w=\pm(3-i)$.

>[!warning] Warning:
>
>Be careful not to assume statements about the complex numbers that you know are true for the reals. Here is an example:
>
>$$
>-1=i\cdot i=\sqrt{(-1)}\sqrt{(-1)}=\sqrt{(-1)(-1)}=\sqrt{1}=1
>$$

## Geometry of the complex plane

From now on, $z=a+ib$ and $w$ are complex numbers.

>[!def] Real and imaginary parts.
>
>1. The _real part of $z$_ is $\Re(z):=a$; and
>2. the _imaginary part of $z$_ is $\Im(z):=b$.

>[!thm] Basic properties of real and imaginary parts.
>
>1. The real and imaginary parts of a complex number are always real numbers.
>2. Two complex numbers are equal if and only if their real and imaginary parts are equal.
>3. $\Re(z)=\Im(iz)$ and $\Im(z)=-\Re(iz)$.
>4. For all $r\in\mathbb R$, $\Re(rz+w)=r\Re(z)+\Re(w)$, and the same for $\Im$. (_Linearity_)

>[!def] Complex conjugate.
>
>The _conjugate of $z$_ is $\overline z:=a-ib$.

>[!thm] Basic properties of conjugates.
>
>5. $\overline{\overline z}=z$. (The conjugate is an _involution_, also mentioned in this [[Graphs#Connectivity and trees|hard exercise]])
>6. $\overline{z+w}=\overline z+\overline w$ and $\overline{zw}=\overline z\cdot\overline w$.
>7. $\overline{\frac zw}=\frac{\overline z}{\overline w}$ when $w\neq 0$.
>8. $\Re(z)=\frac{z+\overline z}2$ and $\Im(z)=\frac{z-\overline z}{2i}$.
>9. $\overline z=z$ if and only if $\Im(z)=0$ if and only if $z\in\mathbb R$.

>[!def] Complex modulus.
>
>The _modulus of $z$_ is $|z|:=\sqrt{a^2+b^2}$.
>
>>[!hint] Note:
>>
>>$|z-w|$ is equivalent to the Euclidean metric of $\mathbb R^2$ seen in [[Metric spaces]].

>[!thm] Basic properties of moduli.
>
>10. $|z|=|\overline z|$ and $|z|^2=z\overline z$.
>11. $|zw|=|z||w|$ and $\left|\frac zw\right|=\frac{|z|}{|w|}$ whenever $w\neq0$.
>12. $|\Re(z)|,|\Im(z)|\leq|z|\leq|\Re(z)|+|\Im(z)|$.
>13. $|z+w|\leq|z|+|w|$ and $\left||z|-|w|\right|\leq|z\pm w|$.

>[!def] Complex arguments.
>
>For $z\neq0$, the _principal argument of $z$_ is the unique $\arg(z)\in(-\pi,\pi]$ that measures the angle between $z$ and the positive real axis. Also, I denote $\operatorname{Arg}(z):=\{\arg(z)+2\pi k:k\in\mathbb Z\}$.

>[!abstract] Example.
>
>$\arg(-i)=-\frac\pi2$.

>[!def] Polar representation.
>
>Every complex number $z$ can be represented as $z=|z|(\cos\theta+i\sin\theta)$ where $\theta\in\operatorname{Arg}(z)$.

>[!thm] Basic properties of polar representation.
>
>14. Suppose that $\theta=\arg(z)$ and $y_0\in\mathbb R$. Show that there is a unique integer $k$ such that $\theta+2\pi k\in(y_0,y_0+2\pi]$.
>15. If $z=r(\cos\theta+i\sin\theta)$, then $|z|=r$ and $\theta\in\operatorname{Arg}(z)$.
>16. For $z=r(\cos\theta+i\sin\theta)$ and $w=\rho(\cos\varphi+i\sin\varphi)$, $\operatorname{Arg}(zw)=\operatorname{Arg}(z)+\operatorname{Arg}(w)$ and
>
>$$
>zw=r\rho(\cos(\theta+\varphi)+i\sin(\theta+\varphi)).
>$$
>
>17. If $z=r(\cos\theta+i\sin\theta)$ with $r>0$, then for every $n\in\mathbb N$, $z^n=r^n(\cos(n\theta)+i\sin(n\theta))$.

>[!note] **de Moivre's formula**.
>
>Prove 17 above changing $n\in\mathbb N$ to $n\in\mathbb Z$.

>[!thm] Complex roots.
>
>For nonzero $z$, $w^n=z$ has exactly $n$ complex solutions for $w$. A solution is called an _$n$th root of $z$_ and the **set** of all solutions is denoted by $z^{1/n}$.

>[!proof]+ Proof:
>
>
>Let $w_k:=r^{1/n}\left(\cos\left(\frac{\theta+2k\pi}n\right)+i\sin\left(\frac{\theta+2k\pi}n\right)\right)$. Then $w_k$ is a solution for every integer $k$. Moreover, $w_{k}=w_{k'}$ if and only if $k\equiv k'\pmod n$.
>
>Finally, if $A$ is a set of $n$ pairwise incongruent integers, then $\{w_k:k\in A\}$ is the set of all $n$ solutions.

>[!note] Exercise.
>
>Prove that $(zw)^{1/n}=z^{1/n}w^{1/n}$, where $A\cdot B:=\{a\cdot b:a\in A, b\in B\}$.

>[!abstract] Example (_complex roots of unity_).
>
>Let $z=1$. Then the $n$th roots are $w_k=\cos\left(\frac{2k\pi}n\right)+i\sin\left(\frac{2k\pi}n\right)$ for $k=0,1,\dots,n-1$, and hence if $u:=w_1$, then $1^{1/n}=\{u^j:0\leq j<n\}$ are all roots of unity.

>[!thm] Proposition.
>
>Let $z$ be nonzero. If $z_0$ is an $n$th root of $z$, then $z^{1/n}=\{z_0u^j:0\leq j<n\}$ is the set of **all** $n$th roots.

To make $z^{\frac pq}$ give a unique value, as opposed to a set of values, I need to restrict the domains to fixed intervals for the angles. This is called picking a _branch_ of the function. The fact that these exist is part of the reason complex analysis is so different from real analysis.

This finishes the extension of the exponential function to all rational numbers. Further extending this to all complex numbers requires knowledge of power series and differentiability, which is out of scope of the course. Doing so is where this famous equality appears:

$$
\boxed{e^{i\pi}+1=0}
$$

Very curious identity, as it combines the simplest equivalence relation (equality), the three fundamental operations (addition, multiplication and exponentiation) with the four fundamental constants (the two identities, the imaginary unit, and the transcendental numbers $\pi$ and $e$) all exactly once.

## Topology of the complex plane

I already established that $\mathbb C$ is a metric space with the metric given by the difference of the modulus. Thus, the section on [[Metric spaces|metric spaces]] applies to $\mathbb C$ as well.

>[!note] Exercise.
>
>Prove that a sequence of complex numbers $z_n$ converges to $z$ if and only if the sequences of reals $\Re(z_n)$ and $\Im(z_n)$ converge to $\Re(z)$ and $\Im(z)$ respectively.

It is convenient to introduce a new symbol and extend the existing operations to it.

>[!def] Definition.
>
>The _extended complex plane_ is the set $\mathbb C^*:=\mathbb C\cup\{\infty\}$. I convene that $z+\infty=\infty$, and for $z\neq0$, $z\cdot\infty=\infty$, $\frac z\infty=0$, $\frac \infty z=\infty$ and $\infty\cdot\infty=\infty$.

I want to endow $\mathbb C^*$ with a topology given by some metric $\delta$. For this to be useful, I want the following conditions satisfied. I delay the construction of $\delta$ until after understanding why I need it.

>[!thm] Basic properties of $\mathbb C^*$.
>
>1. Open sets of $\mathbb C$ are open in $\mathbb C^*$. In symbols, $\tau(\mathbb C)\subseteq\tau(\mathbb C^*)$.
>2. For every open $U\subseteq\mathbb C^*$, $U\cap\mathbb C$ is open in $\mathbb C$.
>3. For all $\varepsilon>0$ there is an $m>0$ such that for all $z\in\mathbb C$, $\delta(z,\infty)<\varepsilon\iff|z|>m$.

The intuition behind the last condition is that points far from the origin should be close to the point at infinity. I denote by $B^*(z,r)$ the open balls of $\mathbb C^*$. Now here comes the big reveal:

>[!thm] Theorem.
>
>$\mathbb C^*$ is compact.

The following lemma is left as an exercise.

>[!thm] Lemma.
>For every $U\in\tau(\mathbb C^*)$ if $\infty\in U$, then $\mathbb C\setminus U$ is compact in $\mathbb C$.

>[!proof] Proof of the theorem:
>
>Take $\mathcal U$, an open cover of $\mathbb C^*$, and split it as $\mathcal U_\infty:=\{U\in\mathcal U:\infty\in U\}$ and $\mathcal U_0:=\mathcal U\setminus\mathcal U_\infty$. Note that the former cannot be empty by the definition of cover. Also, $U_\infty:=\bigcup\mathcal U_\infty$ is an open set of $\mathbb C^*$ containing $\infty$. Then, by the lemma, $\mathbb C\setminus U_\infty$ is a compact subset of $\mathbb C$. Note that $\mathcal U_0=\{U\cap\mathbb C:U\in\mathcal U_0\}$ and so by basic property (2), the elements of $\mathcal U_0$ are open in both $\mathbb C$ and $\mathbb C^*$.
>
>It follows that $\mathcal U_0$ is an open cover (in $\mathbb C$) for the compact set $\mathbb C\setminus U_\infty$ and thus, by definition, it has a finite subcover $\mathcal F$. By basic property (1), the members of $\mathcal F$ are also open in $\mathbb C^*$. Thus, it is clear that $\mathcal F\cup\{U_\infty\}$ is then a finite subcover of $\mathbb C^*$.

>[!hint] Remark.
>
>There are examples of sequences in $\mathbb C$ that diverge in $\mathbb C$ but converge in $\mathbb C^*$. In fact, by the theorems proved about [[Compactness#Sequential compactness|sequential compactness]], **every** sequence in $\mathbb C^*$ has a convergent subsequence.

This section just presented the simplest example of what topologists call the _Alexandroff compactification_ of a Hausdorff space. The explicit metric is constructed below, but following the spirit of "avoiding calculations", I leave reading this to you. 

### Stereographic projection

>[!warning] Note:
>
>This section requires lots of sketches on the board.

Let $S_2:=\{(x,y,z)\in\mathbb R^3:x^2+y^2+z^2=1\}$ be the three-dimensional unit sphere and consider the map $E:S_2\to\mathbb C^*$ given by $E(0,0,1)=\infty$ and

$$
E(x_1,x_2,x_3)=\frac{x_1}{1-x_3}+i\frac{x_2}{1-x_3}
$$

in any other case.

>[!note] Exercise.
>
>Show that $E$ is a bijection and find the inverse $E^{-1}$.

>[!def] Extended metric.
>
>The metric $\delta$ on $\mathbb C^*$ is defined by $\delta(z,w):=d(E^{-1}(z),E^{-1}(w))$ where $d$ is the Euclidean metric on $\mathbb R^3$.

>[!note] Exercise.
>
>1. Prove that $\delta$ is a metric.
>2. Show that $\delta(z,\infty)=\frac2{\sqrt{|z|^2+1}}$ and $\delta(z,w)=\frac{2|z-w|}{\sqrt{|z|^2+1}\sqrt{|w|^2+1}}$.

>[!note] Exercise (out of scope).
>
>Prove that for any $U\subseteq\mathbb C$, $U$ is open in $\mathbb C$ if and only if it is open in $\mathbb C^*$.
>
>>[!hint]- Hint.
>>
>>Use your knowledge of Calculus to show that $E$ is bi-continuous.

The last exercise shows that $E$ is a _homeomorphism_, which is a map that preserves all topological properties. Note, if you knew this beforehand, then that the fact that $S_2$ is a compact subset of the three-dimensional space immediately gives that $\mathbb C^*$ is compact as well.