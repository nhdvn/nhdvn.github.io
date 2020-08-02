---
title:  "Fermat's Little Theorem"
layout: post
tags: fermat modulus prime math number-theory
---

In the world of cryptography, we will have to deal a lot problems with modulus arithmetic and prime numbers. 
Fermat's Theorems are the most common knowledge in number theory to get start with.
Let's discuss first about Fermat's Little Theorem. 

The problem can be describe as follow:

Given $p$ is prime and $a\perp p$. Prove that $a^{p-1} \equiv 1 \pmod p$


Examine a set of positive integer $P = \\{1, 2, ..., p-1\\}$

Multiply each element of $P$ with $a$ in $\mathbb{Z}_p$, we recieved:

\\[ R = \\{ a\bmod p, 2a\bmod p, ..., (p-1)a\bmod p \\}\\]

Choosing any $x$ and $y$ from $R$, we know that:

\begin{cases}
x \equiv ai \pmod p, \quad 1\leq i\leq p-1 \\\\\
y \equiv aj \pmod p, \quad 1\leq j\leq p-1
\end{cases}

With $i\neq j$, proving $x\neq y$ would indicates that all elements of $R$ are pairwise distinct.

Base on contrapositive law: $P\rightarrow Q \Leftrightarrow \overline{Q} \rightarrow \overline{P}$

Assume that $x\equiv y \pmod p$, we have: 

\\[ ai \equiv aj \pmod p \\]

Because $a\perp p$, there exists $a^{-1}$ in $\mathbb{Z}_p$. Multiply both sides of equation with $a^{-1}$:

\begin{equation}
\begin{split}
(a^{-1})ai & \equiv (a^{-1})aj \pmod p \\\\\
i & \equiv \hspace{14mm} j \pmod p
\end{split}
\end{equation}

Since $1\leq i,j\leq p-1$, $i$ must be equal to $j$. But $i$ is multiplied by $a$ only once.

There for, $x$ must be distinct to $y$ if $i\neq j$, which implies all elements of $R$ are distinct.

We conclude $R$ is a permutation of $P$.

Multiplying all elements in $R$ and $P$ respectively, we have:

\begin{equation}
\begin{split}
\[a \cdot 2a \cdot 3a \cdot \cdots  (p-1)a \] \bmod p & = 1\cdot2\cdot3\cdot \cdots (p-1) \\\\\
a^{p-1} (p-1)! & \equiv (p-1)! \pmod p
\end{split}
\end{equation}

Every integer from $1$ to $(p-1)$ is coprime with $p$, hence all exists an inverse in $\mathbb{Z}_p$.

\\[ \Rightarrow a^{p-1} \equiv 1 \pmod p \\]

