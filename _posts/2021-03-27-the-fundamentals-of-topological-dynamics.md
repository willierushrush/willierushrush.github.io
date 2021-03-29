---
title: 'The fundamentals of topological dynamics'
date: 2021-03-27
permalink: /posts/2021/03/the-fundamentals-of-topological-dynamics.md
tags:
  - Dynamical Systems
---

A discrete topological dynamical system is a continuous self map $f: X \to X$ on a topological space $X$. The main interest in topological dynamics is to observe how different values of $x$ behave under iteration $f^n(x)$ for $n\geq 0$ without any further regularity assumptions on $f$ and $X$. In this post, I aim to summarise the very basic definitions and propositions in topological dynamics.

For every $x\in X$,
1. $x$ is a **periodic point** of some period $p\geq 1$, that is, $f^p(x) = x$ and $f^n(x)\neq x$ whenever $1\leq n < p$. If $p=1$, then we call $x$ a **fixed point** of $f$;
2. the **forward orbit** of $x$ under $f$ is the set of forwarad iterates of $x$, that is, $O_f^+(x) = \{f^n(x)\}_{n\geq 0}$;
3. the **$\omega$-limit set** of $x$ is the set of accumulation points of the forward orbit of $x$, that is, $\omega(x) = \cap_{n\geq 1} \overline{O_f^+(f^n(x))}$.

By definition, the $\omega$-limit set is forward invariant, that is, $f(\omega(x)) \subset \omega(x)$. An orbit $O_f^+(x)$ is a finite set if and only if $x$ is a periodic point. When $x$ is periodic, the $\omega$-limit set $\omega(x)$ coincides with the periodic orbit $O_f^+(x)$. Other properties of high dynamical interest aside from periodicity include the following:
4. $x$ is **recurrent** if $x \in \omega(x)$.
5. $x$ is **wandering** if there's an open neighborhood $U$ of $x$ and some $N \in \mathbb{N}$ such that for all $n\geq N$, $f^n(U) \cap U = \emptyset$.

You can think of recurrence as a generalisation of periodicity since recurrent points are those which admits a subsequence of iterates located arbitrarily close to the original point. The set $R$ of recurrent points somewhat encode the complexity of a dynamical system. The set of wandering points is called the **wandering set** $W$; it is open since the definition of wandering points is an open one. The complement $NW:= X\backslash W$ is called the **non-wandering set**, and it is closed. By definition, $\overline{R} \subset NW$.

A continuous map $f: X \to X$ is
1. **minimal** if every point $x \in X$ has a dense orbit, i.e. $\omega(x) = X$;
2. **topologically transitive** if there is a point $x \in X$ with a dense orbit;
3. **topologically mixing** if for every non-empty open subsets $U$ and $V$ of $X$, there is some $N\in \mathbb{N}$ such that whenever $n\geq N$, $f^n(U) \cap V \neq \emptyset$.

Minimality can be equivalently described by the nonexistence of non-empty $f$-invariant proper closed subsets. Clearly, minimality implies topological transitivity. In most nice spaces that we consider, another general criterion for transitivity is the following. (In this setting, clearly mixing also implies transitivity.)

> **_Proposition:_** Let $f:X\to X$ be a continuous map on a locally compact separable metric space $X$. $f$ is topologically transitive if and only if for every non-empty open subsets $U$ and $V$ of $X$, there is some $N\in \mathbb{N}$ such that $f^N(U) \cap V \neq \emptyset$.

The intersection assumption follows immediately from transitivity. Suppose $x$ has a dense orbit. For any non-empty open subsets $U$ and $V$ of $X$, $f^k(x) \in U$ and $f^l(x) \in V$ for some positive integers $k<l$. Therefore, the intersection $f^{l-k}(U) \cap V$ contains $f^l(x)$ and is therefore non-empty. The converse direction requires the additional topological assumption on the space $X$ stated in the proposition. Suppose the intersection assumption holds and let $\\\{U_i\\\}_{i \in \mathbb{N}}$ be a countable base of open subsets of $X$ with compact closure. The point $x$ having a dense orbit can be obtained by the following inductive process. (I am following the book of Katok and Hasselblatt<sup>[2](#fn2)</sup> for this proof.)
* Pick an integer $N_1 > 0$ such that $f^{N_1}(U_1) \cap U_2 \neq \emptyset$, and a non-empty open subset $V_1$ of $U_1 \subset f^{-N_1}(U_2)$.
* Given positive integers $N_1, \ldots N_{k-1}$ and non-empty open subsets $V_i \subset U_i$ for $i=1,\ldots k-1$, pick an integer $N_{k}>0$ such that $f^{N_{k}}(V_{k-1}) \cap U_{k+1} \neq \emptyset$, and a non-empty open subset $V_{k}$ of $V_{k-1} \subset f^{-N_{k}}(U_{k+1})$.
* By induction, we have a nest of compact sets $... \subset \overline{V_3} \subset \overline{V_2} \subset \overline{V_1}$.
By Cantor's intersection theorem, this nest has a non-empty intersection and therefore contains some point $x$. This point has a dense orbit since $f^{N_{k-1}}(x) \in U_k$ for all $k$.

Here are some basic examples:
1. The translation $x+1$ on $\mathbb{R}$ is not transitive. All points are wandering and specifically, for every $x\in \mathbb{R}$, $\omega(x) = \emptyset$.
2. A rational rotation $x+\frac{p}{q}$ of the circle $\mathbb{R}/\mathbb{Z}$, where $p$ and $q$ are co-prime positive integers, is not transitive. In fact, every point is periodic of period $q$.
3. An irrational rotation $x+\rho$ on the circle $\mathbb{R}/\mathbb{Z}$, where $\rho \in (0,1)\backslash \mathbb{Q}$, is minimal, but not mixing.
4. The doubling map $2x$ on the circle $\mathbb{R}/\mathbb{Z}$ is not minimal (there is a fixed point $0$). However, it is mixing because for any open interval $I$ on the circle and any positive integer $N \geq -\log_2 \vert I \vert $ (where $\vert I \vert$ denotes the Euclidean length), $f^N(I) =  \mathbb{R}/\mathbb{Z}$.
5. A complex rational map $f(z)$ restricted to its Julia set $J(f) \subset \mathbb{P}^1$ is not minimal because $J(f)$ always contains periodic points. However, $f$ is mixing: for any open neighborhood $U \subset \mathbb{C}$ of a point $x \in J(f)$, the union $\cup_{n\geq 0} f^n(U)$ of iterates of $U$ must coincide $\mathbb{P}^1$ minus at most two points by Montel's theorem. (See this [post](/posts/2020/06/fatou_and_julia/).)

A continuous map $f: X\to X$ is **topologically conjugate** to another continuous map $g: Y\to Y$ if $h\circ f = g \circ h$ for some homeomorphism $h:X\to Y$. I quite like to think of $h$ as a continuous change of coordinates. Topological conjugacy preserves all of the dynamical properties we mentioned above. Dynamicists would typically reduce a complicated dynamical system by topological conjugacy to a simpler one, analogous to studying a real square matrix $M$ by finding some invertible matrix $P$ such that $P^{-1}M P$ is a block diagonal matrix in linear algebra.

Some examples of conjugacy are the following.
1. Any translation $x+v$ on $\mathbb{R}^n$ by any vector $v \in \mathbb{R}^n\backslash\\\{0\\\}$ is conjugate to the translation $x+e_1$ on $\mathbb{R}^n$ where $e_1=(1,0,\ldots 0)$.
2. Any complex quadratic map $pz^2+qz+r$ is conjugate by an affine map $az+b$ to a monic quadratic map of the form $z^2+c$.

### References

<a name="fn1">1</a>: M. Brin, G. Stuck. Introduction to Dynamical Systems. Cambridge University Press, 2002.  
<a name="fn2">2</a>: A. Katok, B. Hasselblatt. Introduction to the Modern Theory of Dynamical Systems. Encyclopedia of Mathematics and its Applications, volume 54. Cambridge University Press, Cambridge, 1995.  

------
