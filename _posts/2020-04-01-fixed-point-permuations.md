---
title:  "Fixed Point Permutations"
layout: post
tags: Permutation Number_Theory
categories: posts
---

Many problems in cryptography require counting a specific set of permutations which is vunerable to attack.
Those permutations can have some similarities with the original set.
We are interested in identifying the set of those weak permutations and its cardinality. 


The problem can be describe as follow:

Let $$ M = \{ 1, 2, 3, ..., n \} $$ and $$N$$ is a permutation of $$M$$

$$ N = \{ x_1, x_2, x_3, ..., x_n \} \quad x_i \in M \mid i = \overline{1,n} $$

$$N$$ is said to have $$k$$ fixed points if there are exactly $$k$$ elements \\( x_i \in N \\) statisfy $$ x_i = i $$

__Question__: How many permutations of $$N$$ in which there is no fixed point element exists ?

Let $$A$$ be the set in which each permutation has at least 1 fixed point element.

Choosing any permutation $$\lambda$$ of $$A$$, it contains $$k$$ fixed points for $$1\leq k\leq n$$. We have: 

\\[ - {k\choose 1 } + {k\choose 2} - {k\choose 3} + \cdots + (-1)^k{k\choose k} = -1 \label{bt}\tag{1} \\]

According to Binomial Theorem:

$$ (a+b)^k = \sum_{i=0}^k \binom{k}{i} a^i b^{k-i} $$

With $$a = 1$$ and $$b = -1$$:

\begin{equation}
\begin{split}
0 &= + {k\choose 0} - {k\choose 1} + {k\choose 2} - \cdots + (-1)^k {k\choose k} \\\\\
-1 &= - {k\choose 1} + {k\choose 2} - {k \choose 3} + \cdots + (-1)^k {k\choose k}
\end{split}
\end{equation}

Next, we contruct counting method for each permutation of $$A$$:
- From set $$M$$, there are $${n\choose i}$$ ways of choosing $$i$$ fixed point to construct.
- With $$(n-i)$$ slots remained, there are at most $$(n-i)!$$ states to match with each above.

There for, it could only be assured that each matching would contain at least $$i$$ fixed point.

Let $$P$$ be the number of matching:

\\[ P_i = {n\choose i}(n-i)! = \frac{n!}{i!} \\]

For $$i: 1\to n$$, the product $$P_i$$ implies two information:
- it should include $$\lambda$$ until $$i$$ reaches $$k$$, since $$\lambda$$ has $$k$$ fixed points and $$i\leq k\leq n$$.
- $$\lambda$$ was counted for exactly $$k\choose i$$ times, since the state of $$(n-k)$$ no fixed point elements \\
can be reproduced again each time a set of $$i$$ fixed point elements are chosen from $$k$$.

Along with formular \ref{bt}, we can conclude the following result:

\begin{equation}
\begin{split}
S &= (n! - \frac{n!}{1!} + \frac{n!}{2!} - \cdots + (-1)^n\frac{n!}{n!}) \\\\\
  &= (\frac{1}{0!} - \frac{1}{1!} + \frac{1}{2!} - \cdots + (-1)^n\frac{1}{n!}). n! \\\\\
  &= \lfloor \frac{n!+1}{e} \rfloor \quad (\text{using Taylor Expansion for} \hspace{1mm} e^{-1})
\end{split} \label{s} \tag{2}
\end{equation}

Example: $$ M = \\{ 1, 2, 3, 4, 5, 6, 7 \\} $$

Choosing: $$ \lambda = \\{ \textbf{1}, 6, \textbf{3}, 2, \textbf{5}, 4, \textbf{7} \\} \Rightarrow k = 4 $$

Examine all possible matching of $$P_i$$:

With $$i = 1$$:
- Fixed $$1$$ and permute all other element, $$\lambda$$ must be included only once (same for $$3, 5, 7$$)
- Fixed $$2$$ and permute all other element, $$\lambda$$ is not included since $$2$$ is not fixed in $$\lambda$$ (same for $$4, 6$$)

$$\Rightarrow \lambda$$ was counted for $$4$$ times, that is $$k\choose i$$ = $$4\choose 1$$, and $$P_1 = \frac{7!}{1!}$$

With $$i = 2$$:
- Fixed $$1$$ and $$3$$ and permute all other element, $$\lambda$$ must be included only once.\\
  Same for $$\\{1, 5\\}, \\{1, 7\\}, \\{3, 5\\}, \\{3, 7\\}, \\{5, 7\\}$$
- Any permutation included $$2, 4, 6$$ with at least one of them fixed can not be $$\lambda$$

$$\Rightarrow \lambda$$ was counted for $$6$$ times, that is $$k\choose i$$ = $$4\choose 2$$, and $$P_2 = \frac{7!}{2!}$$

Repeat the steps with $$i = 3$$ and $$i = 4$$, we get $$4\choose 3$$ and $$4\choose 4$$

With $$i = 5 \to 7$$, $$\lambda$$ is not counted in $$P$$, or it is counted $$0$$ times.

Sum up all above by formular \ref{bt}:

\\[ - {4\choose 1} + {4\choose 2} - {4\choose 3} + {4\choose 4} = - 4 + 6 - 4 + 1 = -1 \\]

Since there is only $$1$$ permutation of $$\lambda$$ in $$n!$$, we have subtracted $$\lambda$$ from $$N$$ without duplication.

In general, all permutations with $$k$$ fixed point elements will be subtracted only $$1$$ time.

The result $$S$$ will there for, be our final answer.
