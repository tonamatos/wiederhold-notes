---
title: "Home page"
draft: false
---

This page serves as an example of what this website creator is capable of. It can render `markdown` language, which is plain text with minimal but powerful formatting options.

We can render inline math using $\LaTeX$ such as $\aleph_0=\omega$. Or

$$
\sum_{i=1}^\infty\alpha_i<\frac1{2^n}=\begin{pmatrix}0&1&0&2\\0&4&0&0\\5&9&3&7\end{pmatrix}
$$

I also defined some common environments such as:

>[!thm] Theorem 1.
>Here goes the statement of a theorem

>[!proof]- Proof: (collapsible, click the button!)
>
>Here goes the argument or counterexample...

These can be nested, cited, automatically numbered, etc.

My favorite feature is link previewing. For example, hover your mouse over [[cantor#^cantor|Cantor's theorem]].

---

We can also write code formatted according to specific languages:

```python
# This is python
from sympy import isprime
for i in range(k):
	print(isprime(k))
```

```sql
-- This is SQL
graphs( id INTEGER PRIMARY KEY, graph6 TEXT NOT NULL, iso_invariant TEXT NOT NULL, num_nodes INTEGER NOT NULL, num_edges INTEGER NOT NULL, is_connected BOOLEAN, is_tree BOOLEAN, is_local BOOLEAN, is_global BOOLEAN, fer_group BLOB, UNIQUE(graph6))
```