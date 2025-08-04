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

- There is always a set of size 2: **Schur, 1916**. (This is slightly stronger than the above, can you see why?)
- There is a set of any arbitrarily large finite size: **Folkman-Rado-Sanders, 1969.**
- You can always find an infinite such set: **Hindman, 1974.** (This requires significantly heavy machinery from set theory.)

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
>
>When there is risk of confusion, I write $V(G)$ and $E(G)$ to clarify to the reader what graph I am referring to.

Instead of writing an edge as $\{u,v\}$, I will write $uv$.

>[!def] Common properties of graphs.
>
>1. The _neighbors_ of a vertex $v\in V$ are the elements of $N_G(v):=\{u\in V:uv\in E\}$.
>2. The _degree_ of a vertex is the number of neighbors. $d_G(v):=|N_G(v)|$. For a finite nonempty graph $G$, the minimum and maximum degree are denoted by $\delta(G)$ and $\Delta(G)$ respectively.
>3. If $\delta(G)=\Delta(G)$, $G$ is called $\delta(G)$_-regular_.
>4. $|V|$ and $|E|$ are called the _order_ and _size_ of $G$ respectively; in the context of graphs, these are always denoted by $n$ and $m$ respectively.

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
>Reduce the equality given in the handshaking lemma modulo 2.

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
>2. If $H\leq G$, then the inclusion map $i:V(H)\to V(G)$ is a graph homormorphism. In other words, if $H\leq G$ then $H\to G$. (_Monotonicity_)
>3. If $G\to H$ and $H\to J$, then $G\to J$. (_Transitivity_)

As another example, the pigeonhole principle may be stated as $K_n\not\to K_m$ whenever $m<n$.

>[!note] Exercise.
>
>For two cycles, $C_k\to C_\ell$ if and only if $k$ is even, or $\ell$ is odd and $\ell\leq k$.

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

You might be interested to learn that something as simple as deciding whether for an arbitrary graph $G$, $G\to K_3$ or $G\not\to K_3$, is an _NP-complete problem_, meaning that if you discover a deterministic polynomial time algorithm that decides it, you will have effectively solved **every** NP problem and answered one of the most important [open problems](https://en.wikipedia.org/wiki/P_versus_NP_problem) in the history of mathematics and computer science.
### An application: scheduling problems

Your university has a bunch of courses: MAT224, MAT246, MAT237, etc. Students can be enrolled in multiple courses. You need to schedule the exams so that every student can attend without conflicts.
- Some students take both MAT224 and MAT246,
- (make up some other restrictions yourself, I'm lazy...)

If you model this problem as a graph $G$, where $V$ are the courses and $E$ is determined by whether some students take those courses at the same time, then finding a homomorphism $\varphi:G\to K_t$ for a minimal $t$ is equivalent to solving this scheduling problem efficiently. Here, $t$ is the number of timeslots you need to assign and the vertices of $K_t$ label these timeslots. So, for instance, you can find a trivial solution with $t:=|V|$ where every course gets its own unique timeslot. But, if you want to save time and money, you should schedule exams for disjoint courses at the same time, saving one timeslot.

>[!note] Exercise.
>
>What is the optimal $t$ for when $G$ is a cycle?

>[!note] Exercise.
>
>1. What if you don't care about students taking MAT246 and MAT224 at the same time because, say, those students can take a single exam for both courses or something. How do you model additional restrictions where some pairs of courses are allowed to conflict with each other?
>2. What if two or more courses share the same coordinator and must be scheduled at different times independently of the students? How do you model this?
>3. **Hard.** What if the timeslots are all fixed but some of them are close together, and you want to avoid students writing finals on consecutive days. How do you model this situation?
>
>>[!hint]- Hint.
>>
>>1. Remove edges from $G$.
>>2. Add edges to $G$.
>>3. Remove edges from $K_t$.

### Isomorphisms and automorphisms

The most important types of morphisms are defined here.

>[!def] Definition.
>
>Two graphs $G$ and $H$ are _isomorphic_, denoted $G\simeq H$, if there is a bijection $\varphi:V(G)\to V(H)$ such that
>
>$$
>\varphi:G\to H\qquad\text{ and }\qquad\varphi^{-1}:H\to G.
>$$
>
>Such a function is called an _isomorphism_. Equivalently, a bijection between vertex sets $\varphi$ is an isomorphism if
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
>>Find two finite non-isomorphic graphs $G$ and $H$ such that $G\to H$ and $H\to G$. You can even find such graphs of different orders.

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
>Prove that vertex similarity is an equivalence relation on $V$, and that orbits are precisely the equivalence classes.

>[!note] **Hard** exercise.
>
>Prove that in a finite graph $G$, the number of elements of any orbit divides $|\operatorname{Aut}(G)|$.

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
>
>>[!hint]- Hint.
>>
>>Yes, there is. The smallest such graph has 10 vertices.

>[!note] Exercise.
>
>Is there a non-trivial graph where all vertices are similar but not all the edges?
>
>**~~Very hard.~~ Actually easy.** What about the other way around?

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
>If $n\geq2$, then $T$ contains a vertex of degree 1 $v$. Then $T-v$ must satisfy the inductive hypothesis, but this new tree has exactly one vertex and one edge fewer than $T$, so the result follows.

>[!note] Exercise.
>
>Is the converse of the above theorem true? That is, if $G$ is connected and has one edge fewer than vertices, must it be a tree?

>[!note] **Hard** exercise (symmetries of finite trees).
>
>1. Prove that if $T$ is a finite tree, then either $\operatorname{Aut}(T)$ contains only the identity, or it contains an element $\varphi$ such that $\varphi\circ\varphi$ is the identity (also called an _involution_).
>
>2. Construct a finite graph $G$ with one cycle in which the above conclusion fails. That is, such that $\operatorname{Aut}(G)$ contains more than one element, and for every $\varphi\in\operatorname{Aut}(G)$, $\varphi\circ\varphi$ is **not** the identity.
>
>>[!hint]- Hint.
>>
>>2. Start with a cycle and append subgraphs to the vertices to break the reflection symmetries but preserving some rotational symmetries.

>[!note] **Very hard** exercise (infinite trees).
>
>A _branch_ is an infinite path in a tree $T$, that is, an injection $\mathbb N\to T$.
>
>1. Prove that every infinite tree with $\Delta<\infty$ has a branch (**König**).
>2. Construct an infinite tree with no branches.
>3. Construct a tree such that $V$ is countable, but with uncountably many branches.
>
>>[!hint]- Hint.
>>
>>1. Pick a starting vertex $x_0$ and recursively apply the infinite pigeonhole principle: some $x_{n+1}\in N(x_n)$ must be such that $N(x_{n+1})$ is infinite.
>>2. Define the tree on the decreasing sequences in $\mathbb N^\mathbb N$. A branch would violate the well-ordering principle.
>>3. Consider $2^{<\infty}$ ordered by extension. The branches correspond to $2^\mathbb N$.

## Bipartite graphs

>[!def] Definition.
>
>A graph $G$ is called _bipartite_ if $G\to K_2$.

Recall that $K_2$ is a just an edge. As an exercise, try proving the following result on your own to understand the intuition behind bipartite graphs.

>[!thm] Proposition.
>
>Prove that the following are equivalent for any graph $G$.
>
>1. $G$ is bipartite.
>2. Any component of $G$ is bipartite.
>3. There is a set $C\subseteq V(G)$ such that every edge of $G$ has an endpoint in $C$ and the other in $V(G)\setminus C$.
>4. You can color the vertices of $G$ in two colors such that adjacent vertices always get different colors.

>[!abstract] Examples.
>
>1. Paths are bipartite.
>2. Complete bipartite graphs are bipartite.
>3. Even cycles are bipartite but odd cycles are not. A much stronger result is true, see below.

>[!thm] Theorem.
>
>A finite graph is bipartite if and only if it contains no odd cycle.

>[!proof]+ Proof:
>
>Suppose that $G$ is bipartite, that is $G\to K_2$. If $G$ contained an odd cycle $C$, then in particular $C\to G$. By transitivity, $C\to K_2$, contradicting the above example.
>
>Conversely, suppose that all cycles of $G$ are even. For every component $C$ of $G$, fix a vertex $v_C\in V(G)$ and define $d(v)$ as the length of the shortest path between $v$ and whatever vertex of the form $v_C$ is in the same component as $v$. Define $\varphi(v):=d(v)\pmod2$ and convince yourself that $\varphi:G\to K_2$, as desired.

>[!info] Remark.
>
>The theorem above and corollary below are also true for infinite graphs by a compactness argument, for example the [De Bruijn–Erdős theorem](https://en.wikipedia.org/wiki/De_Bruijn%E2%80%93Erd%C5%91s_theorem_(graph_theory)). The proof is outside of the scope of the course.

>[!thm] Corollary.
>
>All finite trees are bipartite.

## The hypercube

This section deals with a graph I personally find interesting, as it lies in the intersection of the chapters Infinity, Combinatorics, and Topology.

First, let me define the _Boolean lattice graph_ $B_n$. Consider $2^n$, the set of all binary sequences of length $n$, as vertex set and make two sequences adjacent if they differ in exactly one coordinate (or _bit_). Thus, for instance, $10\boxed110$ and $10\boxed010$ are adjacent in $B_5$, but $00000$ and $10001$ are not.

For instance, $B_1$ has just a single edge $\{0,1\}$. $B_2$ is isomorphic to the square $C_4$. $B_3$ when drawn looks like a three-dimensional cube. $B_4$ looks like a tesseract. You get the idea.

>[!thm] Proposition.
>
>For all positive integers $n$,
>1. $B_n$ is connected;
>2. $B_n$ is $n$-regular; and
>3. $B_n$ is bipartite.

>[!proof] Proof:
>
>For 3, define $C$ as the set of sequences with an even number of $1$'s. Then every edge has an endpoint in $C$ and the other in the complement.

Now I introduce the protagonist of this section. Let $B_\infty$ be the graph on $2^\mathbb N$, the set of all countably infinite binary sequences, with the adjacencies defined the same way as for $B_n$.

>[!thm] Theorem.
>
>$B_\infty$ is bipartite. But, perhaps surprisingly, $B_\infty$ is **not** connected. In fact, it has uncountably many components.

>[!proof]- Proof:
>
>>[!hint] Hint: show that all cycles are even.

>[!note] Exercise.
>
>Two sequences are connected in $B_\infty$ if and only if they differ by finitely many coordinates. Equivalently, if their difference is eventually zero, in the sense of PS3-4.