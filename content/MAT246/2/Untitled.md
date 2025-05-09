\begin{theorem}[Division algorithm]\label{teo:division_algorithm}
Given are $a$ and $d\geq 1$ integers. Then, there are unique $q,r\in\mathbb Z$ such that $a=dq+r$ and $0\leq r\leq d-1$.
\end{theorem}

The integer $q$ is called the \textit{quotient} and $r$ the \textit{remainder} of the division of $a$ by $d$.

\begin{problem}\exer{Prove Theorem~\ref{teo:division_algorithm} using strong induction.

\emptybox{4in}}
\end{problem}

\begin{problem}\exer{
\fullchili\!\!\fullchili Let $n$ be a positive natural number. Prove that $$\sqrt{3n}\prod_{k=1}^n\frac{2k-1}{2k}\leq1.$$

\cmt{This question is especially challenging because if attempted by weak induction, when reducing the case from $n+1$ to $n$, one would wish to show that $$\frac{\sqrt{3n+3}}{\sqrt{3n}}\cdot\frac{2n+1}{2n+2}\leq1,$$ but this is false even when $n=1$.}}
\end{problem}