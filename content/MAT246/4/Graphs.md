---
title: "4.4. Graph theory"
draft: false
---
>[!warning] Note:
>
>The following results are all proved informally in lectures.

>[!thm] Proposition.
>
>In any party with at least two people, there are two people that are friends with the exact same number of guests.

>[!thm] The party problem.
>
>In any party with at least six guests, there are three mutual friends or three mutual strangers.

## A glimpse into Ramsey theory (out of scope of this course)

>[!thm] Corollary (Schur, 1916).
>
>Split the naturals into two disjoint sets. Then, there are naturals $a,b$ and $c$ in the same set such that $a+b=c$.

Another way of interpreting the above result is: I can find a set of size two all of whose finite sums are inside the same set. What is the largest size of such a set guaranteed to exist?

>[!thm] Theorem (Folkman-Rado-Sanders, 1969).
>
>The set can have any arbitrarily large finite size.

This can actually be extended using some significantly heavy machinery from set theory.

>[!thm] Theorem (Hindman, 1974).
>
>You can always find an infinite such set.

Perhaps the result that gives this theory its name is the one below.

>[!thm] The finite Ramsey theorem, 1930.
>
>For any $m,n,r$ naturals with $1\leq r$ and $n\leq m$, there is a natural $N\geq m$ such that for any function $\chi:[N]^n\to r$, there is an $H\in[N]^m$ such that $c|_{[H]^n}$ is constant.

>[!note] **Very hard** exercise.
>
>Prove the above theorem for $n=r=2$.
>
>>[!hint]- Hint.
>>
>>Use induction on $m$. The case when $m=2$ is trivial. The case when $m=3$ is the Party problem from before (thus $N=6$ works). You need to repeat this idea by dividing $[N]^2$ into two pieces, like in the Party problem, but then each of those pieces needs to be further split into two.

## Graphs

>[!def] Definition of graph.
>
>A _graph_ is a pair $G=(V,E)$ where $V$ is any set, called the _vertex set_, and $E\subseteq[V]^2$ is called the _edge_ set.

Instead of writing an edge as $\{u,v\}$, I will write $uv$.

>[!def] Common properties of graphs.
>
>1. The _neighbors_ of a vertex $v\in V$ are the elements of $N_G(v):=\{u\in V:uv\in E\}$.
>2. The _degree_ of a vertex is the number of neighbors. $d_G(v):=|N_G(v)|$. For a finite nonempty graph $G$, the minimum and maximum degree are denoted by $\delta(G)$ and $\Delta(G)$ respectively.
>3. If $\delta(G)=\Delta(G)$, $G$ is called $\delta(G)$_-regular_.
>4. $|V|$ and $|E|$ are called the _order_ and _size_ of $G$ respectively.

### Named examples of graphs

- The _complete graph_ of order $n$ is the graph $K_n$ where $n$ is the vertex set and $E=[n]^2$.
- The _discrete graph_ of order $n$ is the graph $(n,\emptyset)$.
- The _path_ of length $n$ is the graph $P_n=(n+1,\{(k,k+1):k<n\})$.
- The _cycle_ of order $n$ is the graph $C_n=(n,\{(k,k+1\pmod n):k<n\})$.
- The _complete bipartite_ graph of size $q,\ell$ is the graph $K_{q,\ell}$ that consists of two disjoint sets of sizes $q$ and $\ell$, where two vertices are connected if and only if they are in different sets.

>[!note] Exercise.
>
>Determine all the common properties of the graphs mentioned in this subsection.

>[!thm] Handshaking lemma.
>
>For any finite graph $G$,
>
>$$
>\sum_{v\in V}d(v)=2|E|.
>$$

This proof illustrates an important combinatorial technique called _double counting_.

>[!proof]- Proof:
>
>>[!warning] In lectures.

Say a vertex is _odd_ if it has odd degree.

>[!thm] Corollary.
>
>In any graph, the number of odd vertices is even.

>[!proof]- Proof:
>
>Reduce the equation given in the handshaking lemma modulo 2.

## Subgraphs

>[!def] Definition.
>
>A graph $H$ is a _subgraph_ of $G$ if $H$ is obtained from $G$ by removing edges or vertices. Formally, $V(H)\subseteq V(G)$ and $E(H)\subseteq E(G)$. I also say that $G$ _contains_ $H$.

>[!note] Exercise.
>
>Prove that if $\delta(G)\geq2$, then $G$ contains a cycle. Moreover, it contains a cycle with more than $\delta(G)$ edges.
## Isomorphisms and automorphisms

>[!def] Definition.
>
>Two graphs $G$ and $H$ are _isomorphic_, denoted $G\simeq H$, if there is a bijection $\varphi:V(G)\to V(H)$ such that for all $u,v\in V(G)$, $uv\in E(G)$ if and only if $\varphi(u)\varphi(v)\in E(H)$. Such a function is called an _isomorphism_. If $G=H$, then $\varphi$ is called an _automorphism_.
>
>The _group_ (I didn't define group in this course, but calling this a set is sufficient for my purposes) of all automorphisms of $G$ is denoted by $\operatorname{Aut}(G)$.

>[!thm] Remark.
>
>In the class of all graphs, $\simeq$ is an equivalence relation.

>[!warning] Note:
>
>Most examples are seen in lectures as it requires sketching on the board.

>[!note] Exercise.
>
>Given a graph, you can extract a sequence of naturals called the _degree sequence_, which is all the degree written in decreasing order. Prove that isomorphic graphs have equal degree sequence.
>
>Then construct two non-isomorphic graphs with the same degree sequence.

>[!note] Exercise.
>
>Let $G$ be a graph. The _complement_ of $G$, denoted $\overline G$ is the graph on the same vertex set where $E(\overline G)=\{uv:uv\notin E(G)\}$.
>
>Prove that $\operatorname{Aut}(G)=\operatorname{Aut}(\overline G)$.

### More named examples of graphs 

- The _Kneser graph_ $KG_{m,n}$ where $n>2m$ is the graph with vertex set $[n]^m$, where two sets are adjacent if and only if they are disjoint.
- The _line graph_ of a graph $G$ is the graph $L(G)$ with vertex set $E(G)$, where two edges of $G$ are adjacent in $L(G)$ if and only if they share a vertex (their intersection is a singleton).

>[!note] Exercise.
>
>1. Prove that $KG_{1,n}\simeq K_n$ for $n>2$.
>2. Prove that $KG_{2,n}\simeq L(K_n)$ for $n>4$.

## Symmetry

>[!def] Definition.
>
>Two vertices $u,v\in V$ are called _similar_ if there is $\varphi\in\operatorname{Aut}(G)$ such that $\varphi(u)=v$.
>
>The set of all vertices similar to $v$ is called the _orbit_ of $v$.

One can define an analogous notion for _edge-similarity_.

>[!note] Exercise.
>
>Prove that vertex similarity is an equivalence relation on $V$.

A graph $G$ is called _asymmetric_ if $|\operatorname{Aut}(G)|=1$.

>[!note] **Hard** exercise.
>
>Prove that all asymmetric graphs have order $6$ or more. Prove that for ever $n\geq6$ there is an asymmetric graph of order $n$.
>
>**Very hard.** Is there a regular asymmetric graph?

>[!note] Exercise.
>
>Is there a non-trivial graph where all vertices are similar but not all the edges?
>
>**Very hard.** What about the other way around?

>[!note] Exercise.
>
>Suppose that $G\simeq\overline G$. Join the first and third vertices of the path $P_3$ to every vertex of $G$ to obtain a new graph $H$. Prove that $H\simeq\overline H$.

## Connectivity and trees

>[!def] Definition.
>A graph $G$ is _connected_ if every pair of vertices is a pair of endpoints of some path contained in $G$.
>
>A _tree_ is a connected graph with no cycles.

>[!note] Exercise.
>
>Prove that any graph isomorphic to a connected graph is also connected.
>
>Any graph isomorphic to a tree is also a tree.

>[!thm] Theorem.
>
>Any finite tree with at least two vertices has at least two vertices of degree 1.

>[!note] Exercise.
>
>Is the above theorem true if you remove the word 'finite'?

>[!thm] Theorem.
>
>For any finite tree $T$, $|E(T)|+1=|V(T)|$.

>[!proof]+ Proof:
>
>By induction on the order of the tree. Clearly, if $n=1$, the result holds.
>
>If $n\geq2$, then $T$ contains a vertex of degree 1 $v$. Then $T-v$ must satisfy the inductive hypothesis, but this new tree has exactly one vertex and one edge fewer than $T$. so the result follows.