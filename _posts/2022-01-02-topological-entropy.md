---
title: 'Topological Entropy'
date: 2022-01-02
permalink: /posts/2022/01/topological-entropy/
tags:
  - Dynamical systems
---

The word entropy refers to a measure of chaos or uncertainty of a system. In the field of dynamical systems, topological entropy is perhaps the most important topological invariant which measures the exponential growth of 'distinct' orbits (the 'complexity') of a dynamical system. In this post, we will discuss some of the basic properties and examples of topological entropy.

Let $f: X \to X$ be a continuous self map on a compact metric space $(X,d)$. For every positive integer $n$, we keep track of the first $n$ iterates and define a new metric $d_{f,n}: X \times X \to [0, \infty)$ by $d_{f,n}(x,y) := \max_{0\leq j \leq n-1} d(f^j(x),f^j(y))$.

For any $\epsilon>0$, we say that a subset $E \subset X$ is $(n,\epsilon)$-spanning if every point in $X$ is within $\epsilon$ distance from a point in $E$ in the $d_{f,n}$ metric. Denote by $S_d(f,n,\epsilon)$ the smallest cardinality of a $(n,\epsilon)$-spanning set of $(X,d)$; this quantity represents the smallest number of initial points in $X$ whose finite orbits up to time $n$ $\epsilon$-approximate all possible orbits up to time $n$. The **topological entropy** $h_{top}(f)$ of $f$ is defined to be the asymptotic exponential growth rate of $S_d(f,n,\epsilon)$:

$$
h_{top}(f) = \lim_{\epsilon \to 0} \limsup_{n\to \infty} \frac{1}{n}\log S_d(f,n,\epsilon).
$$

This is just one common way of defining $h_{top}(f)$. Another similar way is to look at the asymptotic growth rate of the minimum cardinality of a $(n,\epsilon)$-separating set, which is a subset in which any two distinct points $x$ and $y$ must satisfy $d_{f,n}(x,y)>\epsilon$; this gives the same quantity $h_{top}(f)$. There is also another approach that utilises coverings similar to the definition of a measure-theoretic entropy; one advantage is that it directly shows independence of the metric $d$, but unfortunately the covering method is difficult to compute. I personally recommend looking at the book<sup>[2](#fn2)</sup> of Katok and Hasselblatt for more details.

## Some properties

The definition of $h_{top}(f)$ above a priori depends on the metric $d$. In fact, it is independent of the choice of the metric!

> **_Proposition:_** The topological entropy of $f: X\to X$ is independent of the metric $d$.

Indeed, by the compactness of $X$, for every other metric $d'$ on $X$ and every $\epsilon >0$, there is some constant $\delta=\delta(\epsilon)>0$ such that $\lim_{\epsilon \to 0}\delta(\epsilon) = 0$ and every $d'$-ball of radius $\delta$ is contained in a $d$-ball of radius $\epsilon$. This observation immediately implies the inequality $S_d(f,n,\epsilon) \leq S_{d'}(f,n,\delta(\epsilon))$. By taking $n\to\infty$ and $\epsilon \to 0$, the entropy with respect to $d'$ is less than or equal to that of $d$. The same argument applies by swapping $d$ and $d'$ so that in the end the two entropies are in fact equal.

As the name suggests, topological entropy is a topological invariant.

> **_Proposition:_** The topological entropy of $f: X\to X$ is invariant under topological conjugacy, namely $h_{top}(p^{-1} \circ f \circ p) = h_{top}(f)$ for any homeomorphism $p: Y \to X$.

This follows rather directly from the independence of $d$ as follows. Let $p: Y \to X$ be a homeomorphism. Endow $Y$ with the pullback metric $p^{*}d$ so that $p: (Y, p^{\*}d) \to (X, d)$ becomes an isometry. Then, the entropy of $g := p^{-1} \circ f \circ p$ coincides with that of $f$ on $(X,d)$.

## Some examples and estimates

Let's start with some easy examples.

1. Any isometry $f$ of a compact metric space $(X,d)$ has zero entropy. This is because the induced metric $d_{f,n}$ coincide with $d$ for all $n$ and thus the quantity $S_d(f,n,\epsilon)$ is independent of $n$.

2. The degree $m$ covering map $E_m(x)=mx$ (mod $1$) on the unit circle $S^1 = \mathbb{R}/\mathbb{Z}$ has topological entropy $h_{top}(E_m) = \log m$. Indeed, you can confirm by a rather straightforward calculation that $\\\{ jm^{-n-k} \vert j =0, 1, \ldots m^{n+k}-1 \\\} \subset S^1$ is a minimal $(n,m^{-k})$-spanning subset of $(S^1,d)$, equipped with the Euclidean metric $d$ induced by $\mathbb{R}$, for $E_m$. This implies that $S_d(E_m,n,m^{-k}) = m^{n+k}$.

The definition(s) of topological entropy can be quite difficult to handle for rather chaotic dynamical systems. Often, we can only obtain crude estimates upon assuming further regularity of the map $f$ and the space $X$.

Recall that the Lipschitz constant $L_f$ of a Lipschitz continuous self map $f$ on a compact metric space $(X,d)$ is defined to be

$$
L(f) := \sup_{x\neq y} \frac{d(f(x),f(y))}{d(x,y)}.
$$

In particular, when $f$ is continuously differentiable, the Lipschitz constant is equal to $L(f) = \sup_{x \in X} \| D f_x \|$ where $\| D f_x \|$ is the operator norm of the linear map $Df_x : T_x X \to T_{f(x)} X$ for each point $x \in X$. The topological entropy of a Lipschitz continuous self map $f$ of a compact $m$-dimensional manifold $X$ satisfies:

$$
h_{top}(f) \leq \max\{ 0, m L_f \}.
$$

This upper bound can actually be generalised to arbitrary compact metric spaces where $m$ is the upper box/Minkowski dimension of $X$, defined by $m := \limsup_{\epsilon \to 0} \frac{\log N(\epsilon)}{\log(1/\epsilon)}$, where $N(\epsilon)$ is the minimal number of balls of radius $\epsilon>0$ needed to cover $(X,d)$. This estimate follows from the inequality $S_d(f,n,\epsilon) \leq N(\max\\\{1,L(f)\\\}^{-n}\epsilon)$, which comes from the observation that every $d$-ball of radius $\max\\\{1,L(f)\\\}^{-n}\epsilon$ is contained in the $d_{f,n}$-ball of the same center and of radius $\epsilon$.

Suppose $f$ is a smooth self map on a compact $m$-dimensional manifold $X$. Manifolds of arbitrarily high dimension can support very complicated dynamics. One of main ways for dynamicists to tackle them is to firstly look at the induced maps $f_{*,i}$ on the homology groups $H_i(X,\mathbb{R})$ for $i=0,1 \ldots m$. The induced maps $f_{\*,i}$ are much easier to study because they are topologically invariant linear maps on vector spaces. Denote by $\rho(f_\*)$ the spectral radius (the absolute value of the largest eigenvalue). The spectral radius $\rho(f_\*)$ is a topological invariant which encodes the homological growth rate induced by $f$. A result by Yomdin<sup>[3](#fn3)</sup> states that we can obtain a lower bound of the topological entropy depending on the spectral radius as follows.

> **_Theorem:_** For any smooth map $f:X \to X$ on a compact manifold $X$, $h_{top}(f) \geq \log \rho(f_*)$.

Here's a more easily digestible implication of Yomdin's inequality. When $X$ is orientable, the top homology group $H_m(X,\mathbb{R})$ is one-dimensional) and if $\omega$ is a generator of $H_m(X,\mathbb{R})$, then $f_*(\omega) = \text{deg}(f) \omega$ where $\text{deg}(f) \in \mathbb{Z}$ is the topological degree of $f$. Then, Yomdin's inequality implies that $h_{top}(f) \geq \log \vert \text{deg}(f) \vert$.

There are instances in which the bound in Yomdin's inequality is attained. Gromov<sup>[1](#fn1)</sup> proved that $\log \rho(f_*)$ is an upper bound for topological entropy when $f$ is a holomorphic map on a compact Kähler manifold $X$.

> **_Gromov-Yomdin Theorem:_** For any holomorphic map $f:X \to X$ on a compact Kähler manifold $X$, $h_{top}(f) = \log \rho(f_*)$.

In particular, when $f$ is a holomorphic map on the complex projective space $X = \mathbb{P}^n$, $f$ is given by $n+1$ homogeneous polynomials in $\mathbb{C}^{n+1}$ of the same (algebraic) degree $k$ and $h_{top}(f) = \log \text{deg}(f) = n \log k$. One of the crucial ingredients in Gromov's proof is the fact that complex submanifolds of any compact Kähler manifold is minimal (in the sense that it has zero curvature with respect to the induced Kähler metric).

### References

<a name="fn1">1</a>: M. Gromov. On the Entropy of Holomorphic Maps. Enseign. Enseign. Math. (2) 49 no. 3-4, Pages 217–235. 2003.    
<a name="fn2">2</a>: A. Katok, B. Hasselblatt. Introduction to the Modern Theory of Dynamical Systems. Encyclopedia of Mathematics and its Applications, volume 54. Cambridge University Press, Cambridge, 1995.     
<a name="fn3">3</a>: Y. Yomdin. Volume Growth and Entropy. 1987. Israel J. Math, Vol 57, 1987.
------
