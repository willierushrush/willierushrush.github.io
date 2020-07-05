---
title: 'Riemann surfaces are always second-countable'
date: 2020-05-21
permalink: /posts/2020/05/second-countability/
categories:
  - '2020'
tags:
  - Riemann surfaces
  - Topology
---

Manifolds are automatically assumed to be second-countable by definition. Without this assumption, horrible topological objects like the long line, i.e. the concatenation of uncountably many copies of $[0,1)$, would be manifolds and paracompactness as well as the existence of partitions of unity would not come for granted. However, even without this assumption, Riemann surfaces are still second-countable.

A Riemann surface is a connected one dimensional complex manifold, that is, a connected Hausdorff topological space that is locally homeomorphic to the unit disk $\mathbb{D}$ on the complex plane $\mathbb{C}$ and each transition map between two such overlapping charts is holomorphic. Most introductory lectures on Riemann surfaces or complex geometry will make a side remark that Riemann surfaces (without assuming second-countability) are always second-countable. This is quite an extraordinary result typically known as Radó's theorem<sup>[4](#fn4)</sup>.

> **_Radó's theorem:_** Every connected Riemann surface is second-countable.

Each Riemann surface $Y$ admits a holomorphic universal covering $p: Z \to Y$. Given a basepoint $x_0$ in $Y$, the space $Z$ can be defined as the set of all pairs $(x,[\gamma])$ where $x$ is a point in $Y$ and $[\gamma]$ is a homotopy class of paths on $Y$ from $x_0$ to $x$. The map $p$ is a projection in the obvious way. Endow $Y$ with the Riemann surface structure by pullback via $p$. Koebe's uniformisation theorem guarantees that $Z$ is either biholomorphic to $\mathbb{D}$, $\mathbb{C}$ or the Riemann sphere $\mathbb{P}^1$. However, let's pretend we do not know this theorem yet. (Uniformisation is often proven using second-countability.)

To prove Radó's theorem, it is sufficient to choose $Y$ to be some appropriate open subset of $X$ and construct non-constant holomorphic map $f : Z \to \mathbb{C}$. This essentially relies on the covering properties and opennes of $f$. Indeed, every point $z \in Z$ admits a small neighbourhood $V_z$ on which $f$ is a finite covering onto its image, possibly branched but only at $z$. Let $\mathcal{B}'$ be a countable basis for $\mathbb{C}$ and define $\mathcal{B}$ to be the set of all connected components $V$ of $f^{-1}(U)$ for each $U \in \mathcal{B}'$ such that on $V$, $f$ is a cover onto its image, possibly branched at at most one point. For each $z \in Z$, since there is some $U \in \mathcal{B}'$ contained in '$f(V_z)$, so then the connected component $V \in \mathcal{B}$ of $f^{-1}(U)$ which contains $z$ is a subset of $V_z$. Therefore, $\mathcal{B}$ is a basis for $Z$.

Each $V \in \mathcal{B}$ is surely second-countable since it is a finite cover of an open subset of a second-countable space $\mathbb{C}$. As such, each $V$ must only intersect countably many elements of $\mathcal{B}$. We can pick an element $V$ in $\mathcal{B}$ and define $B_1 = \\{ V \\}$ and inductively $B_n$ to be the collection of elements of $\mathcal{B}$ which intersect some element of $B_{n-1}$. By connectivity, $\mathcal{B} = \bigcup_{n=1}^\infty B_n$, but since this is a countable union of countable sets, $\mathcal{B}$ is indeed a countable basis for $Z$.

We can the image of elements of $\mathcal{B}$ under $p$ to obtain a countable basis on $Y$. We will see below that when $Y$ is nice enough, $X$ will also have a countable basis. (From this argument, it is clear that uniformisation implies second-countability, but we do not know uniformisation yet!)

Remove two disjoint closed disks $D_1, D_2 \subset X$ and let $Y := X \backslash (D_1 \cup D_2)$. The problem is now reduced to the Dirichlet problem of finding a continuous map $h$ on the closure $\bar{Y}$ such that $h$ is harmonic on $Y$, $h \equiv 0$ along $\partial D_1$ and $h \equiv 1$ along $\partial D_2$. When such a map $h$ exists, the 1-form $\partial h$ ($\frac{\partial h}{\partial z} dz$ in local coordinates) is holomorphic and since the pullback $p^* \partial h$ via the universal cover $p: Z \to Y$ must be exact, it has a primitive

$$
f : Z \to \mathbb{C}, \quad (z,[\gamma]) \mapsto \int_\gamma \partial h,
$$

which is holomorphic and non-constant. Therefore, $X$ is second-countable if find a solution $h$ to the Dirichlet problem. A common approach would be the Perron method, a variant of which is stated below. (See Forster<sup>[2](#fn2)</sup> $\S 22$.)

> **_Perron Method:_** Let $Y$ be an open subset of a Riemann surface $X$ with smooth boundary $\partial Y$ compactly contained in $X$. Let $\phi: \partial Y \to \mathbb{R}$ be a bounded continuous map and $\mathcal{F}$ be a family of all subharmonic functions $g: Y \to \mathbb{R}$ bounded above by $\sup_{x \in \partial Y} \phi(x)$ such that $g \leq \phi$ on $\partial Y$. Then, the supremum $h(x) = \sup_{g \in \mathcal{F}} g(x)$ is a continuous map on $\bar{Y}$ which is harmonic on $Y$ and has boundary value $\phi$.

This concludes the proof of Radó's theorem. A straightforward consequence is that tautological examples like the long plane, i.e. a product of two long lines, do not admit a complex structure. The theorem, however, does not hold for higher complex dimensions. One of the first examples was explicitly constructed Calabi and Rosenlicht<sup>[1](#fn1)</sup> via algebraic geometry.

### References
<a name="fn1">1</a>: E. Calabi and M. Rosenlicht. Complex Analytic Manifolds Without Countable Base. Proceedings of the American Mathematical Society, 4(3): 335-340, 1953.  
<a name="fn2">2</a>: O. Forster. Lectures on Riemann surfaces. Graduate Texts in Mathematics, Vol 81. Springer-Verlag, NY-Berlin, 1981.  
<a name="fn3">3</a>: J. H. Hubbard. Teichmüller Theory and Applications to Geometry, Topology, and Dynamics. Vol. 1. Matrix Editions, Ithaca, NY, 2006.  
<a name="fn4">4</a>: T. Radó. Über den Begriff der Riemannschen Fläche. Acta Szeged, 2(2): 101–121, 1925.  

------
