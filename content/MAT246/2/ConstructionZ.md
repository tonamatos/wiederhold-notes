---
title: "2.1. Construction"
draft: true
---
Algebraically, I am interested in solving equations of the form

$$
a+x=b.
$$

In $\mathbb N$, this will not always have a solution, for instance $5+x=3$. How do I "add" the missing solution to produce a larger structure?

## The set of integers is a quotient

I want to be able to talk about an object of the form $m-n$ from within the naturals. In the above example, such an object would indeed solve the equation, namely $5+(3-5)=3$. I will encode this sought behavior by means of an [[Relations#Equivalence relations|equivalence relation]] $\sim_d$ defined as follows.

>[!def] Definition.
>
>1. A _difference_ is a pair $(m,n)\in\mathbb N\times\mathbb N$.
>2. A difference $(m,n)$ is _positive_ if $m>n$, that is, there is $a\in\mathbb N\setminus\{0\}$ such that $n+a=m$.
>3. Two differences $(m,n)$ and $(p,q)$ are related under $\sim_d$ if $m+q=p+n$.

>[!note] Exercise.
>
>Prove that $\sim_d$ is an equivalence relation.
>
>>[!hint]- Hint.
>>
>>To show transitivity, you will need to use that addition in $\mathbb N$ has the _cancellation property_. This course is not focused on algebra so I have not explicitly mentioned this, but it is one of the many properties that come with the naturals "out of the box."

As an example, the difference $(1,0)$ is equivalent to $(2,1)$, $(3,2)$, etc. and represents the integer $1$.

>[!thm] Lemma.
>
>Suppose that $(m,n)$ is positive.
>
>1. If $(m,n)\sim_d(p,q)$, then $(p,q)$ is also positive.
>2. There exists $p\in\mathbb N\setminus\{0\}$ such that $(m,n)\sim_d(p,0)$.

>[!def] Definition (Integer).
>
>An _integer_ is an equivalence class of $\sim_d$. I also denote $\mathbb Z:=\mathbb N\times\mathbb N/\sim_d$.
>
>A _positive integer_ is an integer whose class is represented by a positive difference. (By the above lemma, if one representative is positive, then so are all of them, so this is well-defined.)

Since, by the above lemma, every positive integer can be written as $[(p,0)]_{\sim_d}$ for some positive natural $p$, I will refer to said integer by just the variable $p$. In other words, positive integers are _identified_ as positive naturals. While it is incorrect to say that $\mathbb N\subseteq\mathbb Z$, this identification means I can abuse the language and say that the naturals are a subset of the integers. This is formalized by the theorem below.

>[!def] Definition (Addition in $\mathbb Z$).
>
>1. Given two differences, $(m,n)$ and $(p,q)$, their _sum_ is $(m,n)+(p,q):=(m,+p,n+q)$.
>2. The sum of two integers is the class of the sum of its representatives.

>[!question] Reflect.
>
>There is something slightly incomplete in the second definition above. _Which representatives?_ is the question you should be asking. Representatives are typically not unique, so how do you know you picked the right ones? Of course, in the end it does not matter and the resulting sum will be the same, but this is something that requires proof in a formal construction.

I skip the details that are analogous to addition.

>[!def] Definition (Multiplication in $\mathbb Z$).
>
>$$
>[(m,n)]_{\sim_d}\cdot[(p,q)]_{\sim_d}:=[(mp+nq,mq+np)]_{\sim_d}
>$$

>[!question] Reflect.
>
>If you find the definition arbitrary, recall that the integer $[(m,n)]_{\sim_d}$ is meant to represent the new object "$m-n$".

>[!thm] Lemma.
>
>The addition and multiplication of integers is well-defined, associative, commutative and distribute over each other. (Definition for all these words is found [[ConstructionN|here]].)

The following is the way to formalize the simple idea that the naturals are **inside** of the integers.

>[!thm] Theorem (Embedding of $\mathbb N$ in $\mathbb Z$).
>
>There is an injective function $e:\mathbb N\to\mathbb Z$ that preserves the algebraic and order structures of $\mathbb N$. Concretely, for all naturals $n$ and $m$,
>
>1. $e(n)+e(m)=e(n+m)$;
>2. $e(n)\cdot e(m)=e(n\cdot m)$; and
>3. if $n<m$, then $e(n)<e(m)$.

>[!proof] Proof:
>
>Take $e(n):=[(n,0)]_{\sim_d}$ and verify the rest yourself.

Finally, I reveal the reason I introduced this new structure $\mathbb Z$ in the first place.

>[!thm] Theorem.
>
>If $a$ and $b$ are integers, then there is a unique integer $x$ such that $a+x=b$.

I denote the integer $x$ by the symbol $b-a$.

>[!proof] Proof:
>
>Simply take $x:=[(b_0+a_1,b_1+a_0)]_{\sim_d}$ where $a=[(a_0,a_1)]_{\sim_d}$ and similarly for $b$.

>Congratulations!
>You have learned to _subtract_ numbers.