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

>[!proof]+ Proof:
>
>Label rooms $0,1,\dots n-1$ and place each guest in room $i$ if they are friends with $i$ other guests. The result is proved when one room has at least two people. But notice that room $0$ and room $n-1$ cannot both be nonempty simultaneously. Thus there can only be at most $n-1$ nonempty rooms. The pigeonhole principle hence proves the claim.

>[!thm] The party problem.
>
>In any party with at least six guests, there are three mutual friends or three mutual strangers.

>[!proof]+ Proof:
>
>Fix a guest $x$ and denote by $F$ the set of guests that are friends with $x$ and by $S$ the set of guests that are not friends with $x$. By the pigeonhole principle, either $|F|\geq3$ or $|S|\geq3$. Without loss of generality (by interchanging all friends with strangers and vice versa), suppose the former happens. Then, select three guests in $F$. Either they are mutual strangers, in which case I am done, or two of them are friends, thus with $x$ the three are mutual friends.
 
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

>[!thm] The finite Ramsey theorem for graphs, 1930.
>
>For any $m,r$ positive integers with $2\leq m$, there is a natural $N\geq m$ such that for any function $\chi:[N]^2\to r$, there is an $H\in[N]^m$ such that $c|_{[H]^2}$ is constant.

>[!note] **Very hard** exercise.
>
>Prove the above theorem for $r=2$ colors.
>
>>[!hint]- Hint.
>>
>>Use induction on $m$. The case when $m=2$ is trivial. The case when $m=3$ is the Party problem from before (thus $N=6$ works). You need to repeat this idea by dividing $[N]^2$ into two pieces, like in the Party problem, but then each of those pieces needs to be further split into two smaller pieces.

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
- The _path_ of length $n$ is the graph $P_n=(n,\{(k,k+1):k+1<n\})$.
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
>A graph $H$ is a _subgraph_ of $G$ if $H$ is obtained from $G$ by removing edges or vertices. Formally, $V(H)\subseteq V(G)$ and $E(H)\subseteq E(G)$. I also say that $G$ _contains_ $H$. I employ the notation $H\leq G$ to denote that $H$ is a subgraph of $G$.

>[!note] Exercise.
>
>Let $G$ be a finite graph. Prove that if $\delta(G)\geq2$, then $G$ contains a cycle. Moreover, it contains a cycle with more than $\delta(G)$ edges.
>
>Show, with an example, that if $G$ is infinite then the conclusion might fail. What can you conclude in this case?
>
>>[!check] Solution in Tutorial 9.

A special case that deserves attention is that of _paths_ as subgraphs. There are two very natural ways of formalizing the idea of "getting from one vertex to another". For this, I need to introduce the following formality.

## Morphisms between graphs

>[!def] Definition.
>
>Let $G$ and $H$ be two graphs. A function $\varphi:V(G)\to V(H)$ is called a _graph homomorphism_ (also called an _adjacency-preserving map_) if
>
>$$
>\forall u,v\in V(G),\quad uv\in E(G)\implies\varphi(u)\varphi(v)\in E(H).
>$$
>
>I abbreviate the fact that $\varphi$ has this property by simply writing $\varphi:G\to H$. Note that this is a slight abuse of language, but this will never cause confusion.
>
>Moreover, if I don't want to specify what $\varphi$ is, I write $G\to H$ when there is such a graph homomorphism.

>[!abstract] Examples.
>
>1. The identity is always a graph homomorphism. Thus, $\operatorname{id}_{V(G)}:G\to G$. (_Reflexivity_)
>2. If $H\leq G$, then the inclusion map $i:V(H)\to V(G)$ is a graph homormorphism. In other words, if $H\leq G$ then $H\to G$.
>3. If $G\to H$ and $H\to J$, then $G\to J$. (_Transitivity_)
>4. Between any two cycles of even length there is a homomorphism. This is not true for odd-length cycles of **any** different lengths.

>[!def] Definition.
>
>Let $G$ be a graph and $u,v\in V(G)$ two distinct vertices. If $w:P_n\to G$ (recall that $P_n$ is the path of length $n$ defined earlier) satisfies that $w(0)=u$ (the _starting point_) and $w(n)=v$ (the _endpoint_), I call $w$ a _walk between $u$ and $v$_.
>
>If, in addition, $w$ happens to be injective, then I call $w$ a _path between $u$ and $v$_.

Intuitively, walks can repeat vertices and contain cycles. Paths cannot.

>[!abstract] Examples.
>
>1. Removing a single edge from a cycle produces a path.
>2. Draw a figure 8 and remove some edge $uv$ of endpoints of degree 2. The remaining graph is a walk between $u$ and $v$ that is not a path.

>[!note] Exercise.
>
>If there is a walk between two vertices, then there is a path between the same vertices.
>
>>[!check] Solution in Tutorial 9.

The most important types of morphisms are defined in the following subsection.
### Isomorphisms and automorphisms

>[!def] Definition.
>
>Two graphs $G$ and $H$ are _isomorphic_, denoted $G\simeq H$, if there is a bijection $\varphi:V(G)\to V(H)$ such that
>
>$$
>\varphi:G\to H\qquad\text{ and }\qquad\varphi^{-1}:H\to G.
>$$
>
>Such a function is called an _isomorphism_. Equivalently, $\varphi$ is an isomorphism if
>
>$$
>\forall u,v\in V(G),\quad uv\in E(G)\iff\varphi(u)\varphi(v)\in E(H).
>$$
>
>If in addition $G=H$, then $\varphi$ is called an _automorphism_.
>
>The _group_ (I didn't define group in this course, but calling this a set is sufficient for my purposes) of all automorphisms of $G$ is denoted by $\operatorname{Aut}(G)$.

>[!thm] Remark.
>
>In the class of all graphs, $\simeq$ is an equivalence relation.

>[!warning] Warning:
>
>You might be tempted to think that $G\to H$ and $H\to G$ if and only if $G\simeq H$, but you'd be wrong.
>
>>[!note] **Hard** exercise ($\to$ is not _antisymmetric_).
>>
>>Find two finite non-isomorphic graphs $G$ and $H$ such that $G\to H$ and $H\to G$.

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

>[!note] Exercise.
>
>Is there a graph $G$ such that $\overline G\simeq G$?
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

>[!abstract] Examples.
>
>1. The two endpoints of a path are similar. How many orbits are there?
>2. The center of an odd path is not similar to any vertex. Its orbit is a singleton.
>3. All vertices of a cycle are similar to each other, meaning there is a single orbit.
>4. The complete and discrete graphs have a single orbit.

One can define an analogous notion for _edge-similarity_.

>[!note] Exercise.
>
>Prove that vertex similarity is an equivalence relation on $V$.

Since the identity is an automorphism of any graph $G$, $\operatorname{Aut}(G)$ is always nonempty. In fact, if $n$ is the number of vertices of $G$, then $1\leq|\operatorname{Aut}(G)|\leq n!$.

>[!note] Exercise.
>
>Prove that for all graphs $G$, $1\leq|\operatorname{Aut}(G)|\leq|V(G)|!$. Then construct graphs $G$ and $H$ such that $|\operatorname{Aut}(G)|=1$ and $|\operatorname{Aut}(H)|=|V(H)|!$.
>
>**Hard.**  can you find an infinite such graph $G$?

A graph $G$ is called _asymmetric_ if $|\operatorname{Aut}(G)|=1$. Equivalently, if all its orbits are singletons, or if no pair of vertices are similar.

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
>
>Two vertices $u,v$ in a graph $G$ are said to be _connected_ if there is a path in $G$ between $u$ and $v$.

>[!abstract] Examples.
>
>1. Any two vertices on a path are connected by a subgraph of that path, which is also a path.
>2. Any two vertices on a cycle are connected by two paths whose edges are disjoint.

>[!note] Exercise.
>
>Prove that connectedness is an equivalence relation on $V$. The equivalence classes are called the _components_ of $G$.

>[!def] Definition.
>A graph $G$ is _connected_ if it has a single component. That is, if every pair of vertices is a pair of endpoints of some path in $G$.
>
>A _tree_ is a connected graph with no cycles.

>[!abstract] Examples.
>
>1. Any component of a graph, seen as a subgraph, is connected.
>2. Paths, cycles and complete graphs are all connected.
>3. Discrete graphs with more than one vertex are not connected.

>[!note] Exercise.
>
>1. Prove that any graph isomorphic to a connected graph is also connected.
>2. Any graph isomorphic to a tree is also a tree.

>[!thm] Theorem.
>
>Any finite tree with at least two vertices has at least two vertices of degree 1.

>[!proof] Proof in Tutorial 9.

>[!thm] Corollary.
>
>Let $G$ be a finite graph with $c$-many components. Then either $G$ contains a cycle or it contains $2c$ vertices of degree 1.

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