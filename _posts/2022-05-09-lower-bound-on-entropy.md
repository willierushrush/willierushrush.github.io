---
title: 'Lower Bound on Entropy'
date: 2022-05-09
permalink: /posts/2022/05/lower-bound-on-entropy/
tags:
  - Dynamical Systems
---

In dynamical systems, the entropy $h_{top}(f)$ of a continuous map $f : X \to X$ on a compact space $X$ is a way to measure the complexity of $f$. Computing the exact value of entropy often requires $f$ to be highly regular (e.g. holomorphic). In the case where $X$ is a smooth orientable manifold and $f$ is continuously differentiable ($C^1$), a theorem by Misiurewicz and Przytycki gives a lower bound for $h_{top}(f)$.

[Firstly, I would like to thank Roland Roeder for letting me know of this beautiful proof. It was recently communicated in a talk by Misiurewicz, and I simply cannot resist writing about it because of how clean it is!]

## What is entropy again?

Let $f: X \to X$ be a continuous self map on a compact metric space $(X,d)$. We say that a subset $E \subset X$ is a **$(n,\delta)$-separated set** if for every pair of distinct points $x,y \in E$, we have $d(f^k(x),f^k(y)) \geq \delta$ for all $k=0,1,\ldots n-1$. Then, the topological entropy of $f$ is defined to be

$$
h_{top}(f) := \lim_{\delta \to 0} \limsup_{n\to \infty} \frac{1}{n}\log N_d(f,n,\delta).
$$

where $N_d(f,n,\delta)$ is the maximum cardinality of an $(n,\delta)$-separated set. Refer to this [post](/posts/2022/01/topological-entropy/) for more details.

Misiurewicz and Przytycki published an important 2-page paper on a lower bound of $h_{top}(f)$.

> **_Theorem:_** Every $C^1$ map $f: X \to X$ on a smooth compact orientable manifold satisfies $h_{top}(f) \geq \text{log}\vert \text{deg}(f) \vert$.

## The proof

Recall that a point $x \in X$ is a critical value if it is the image of some critical point $y \in X$, that is, $Df_y$ does not have full rank. If $x$ is not a critical value, it is called a regular value and by basic degree theory (e.g. from Lee's book<sup>[2](#fn2)</sup>), $x$ has at least $d$ preimages where $d:=\vert \text{deg}(f)\vert$ is the absolute value of the degree of $f$. The main ingredient we shall use is Sard's theorem, which tells us that the set of regular values of $f$ has full Lebesgue measure.

Let's pick a Riemannian metric on $X$ and denote by $\omega$ and $d: X \times X \to [0,\infty)$ the induced volume form and the induced metric on $X$. (Recall that $h_{top}(f)$ will be independent on the choice of this metric!) Let's pick any $\alpha \in (0,1)$. We will show in the end that $h_{top}(f) \geq \alpha \text{log}d$.

Let pick some $\epsilon >0$ and $n \in \mathbb{N}$. Denote by $B$ the set of points $b \in X$ such that $\vert Df_b \vert \geq \epsilon$. Denote by $A$ the set of points $a \in X$ such that the cardinality of $B \cap \\\{f^i(a)\\\}_{i=0, \ldots n-1}$ is at most $\alpha n$. Suppose $L:= \sup\_{y \in X} \vert Df_y \vert$, then by how $A$ is defined, every $a \in A$ satisfies

$$
\vert Df^n_a\vert = \prod_{j=0}^{n-1} \vert Df_{f^j(a)} \vert < \epsilon^{(1-\alpha)n} L^{\alpha n}.
$$

Let's set $\epsilon = L^{-\alpha/(\alpha -1)}$ so then now we have $\vert Df^n_a \vert < 1$ for every $a \in A$. In particular, $\text{Vol}(f^n(A)) < \text{Vol}(X)$ and the iterate $f^n$ admits a regular value $x$ outside of $f^n(A)$.

Let's define the finite set $Q_n \subset X$ through the following inductive process.
1. Set $Q_0:= \\\{x \\\}$.
2. Given $Q_i$ for $i < n$, we set $Q_{i+1}$ to be the union $\cup_{y \in Q_n} P_y$ where:
  (a) If $y$ admits a preimage $z \in f^{-1}\\\{y\\\}$ outside of $B$, then set $P_y = \\\{z\\\}$;
  (b) Otherwise, $P_y = f^{-1}\\\{y\\\}$.
There is some maximal $\delta=\delta(\epsilon)>0$ such that for every $x \in B$, $f$ is injective on the ball $B(x,\delta)$. Then, $Q_n$ is actually an $(n,\delta)$-separated set!

The condition that $x \not\in f^n(A)$ implies that $Q_n$ is disjoint from $A$. In the inductive process, case (b) must happens at least $\alpha n$ times, so then the cardinality of $Q_n$ is at least $d^{\alpha n}$. Therefore, $h_{top}(f) \geq \alpha \text{log}d$ for every $0 < \alpha < 1$ and we are done!

### References
<a name="fn1">1</a>: A. Katok, B. Hasselblatt. Introduction to the Modern Theory of Dynamical Systems. Encyclopedia of Mathematics and its Applications, volume 54. Cambridge University Press, Cambridge, 1995.     
<a name="fn2">2</a>: J. M. Lee. Introduction to Smooth Manifolds. Springer, 2003.   
<a name="fn3">3</a>: M. Misiurewicz, F. Przytycki. Topological Entropy and Degree of Smooth Mappings. Bull. Acad. Pol. Sci., Ser. sci. math., astr. et phys, 25, pg. 573-574, 1977.   
------
