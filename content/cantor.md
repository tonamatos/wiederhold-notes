---
title: "Cantor's theorem"
draft: false
---
Cantor's proof that there are uncountably many reals uses a _diagonalization_ argument that may be generalized in the following way.

>[!thm] Cantor's Theorem.
>Let $A$ be any set. There is no surjective function $f:A\to\mathcal{P}(A)$.
^cantor

>[!proof]- Proof:
>
>Assume towards contradiction that $f$ is surjective. Define $B=\{a\in A:a\notin f(a)\}$.
>
>Clearly, $B\subseteq A$, so by surjectivity there is some $b\in A$ such that $f(b)=B$.
>
>Now, if $b\in B$, then by definition $b\notin f(b)=B$, contradiction. Similarly, if $b\notin B$, then by definition $b\in f(b)=B$, contradiction.
>
>Thus, no such surjection can exist.