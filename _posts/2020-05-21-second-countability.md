---
title: 'Riemann surfaces are always second-countable.'
date: 2020-05-21
permalink: /posts/2020/05/second-countability/
tags:
  - Complex analysis
  - Complex geometry
  - Riemann surfaces
  - Topology
---

Manifolds are automatically assumed to be second-countable by definition. Without this assumption, horrible topological objects like the long line, i.e. the concatenation of uncountably many copies of $[0,1)$, would be manifolds and paracompactness as well as the existence of partitions of unity would not come for granted.

A Riemann surface is a connected one dimensional complex manifold, that is, a connected Hausdorff topological space that is locally homeomorphic to the unit disk $\mathbb{D} \subset \mathbb{C}$ and each transition map between two such overlapping charts is holomorphic. Most introductory lectures on Riemann surfaces or complex geometry will make a side remark that Riemann surfaces (without assuming second-countability) are always second-countable. This is quite an extraordinary result typically known as Radó's theorem [insert citation].

> **_Radó's theorem:_** Every connected Riemann surface is second-countable.

Each Riemann surface $Y$ admits a holomorphic universal covering $p: Z \to Y$. Given a basepoint $x_0 \in Y$, the space $Z$ can be defined as the set of all pairs $(x,[\gamma])$ where $x \in Y$ and $[\gamma]$ is a homotopy class of paths on $Y$ from $x_0$ to $x$. The map $p$ is a projection in the obvious way. Endow $Y$ with the Riemann surface structure by pullback via $p$. The uniformisation theorem guarantees that $Z$ is either biholomorphic to $\mathbb{D}$, $\mathbb{C}$ or the Riemann sphere $\mathbb{P}^1$. However, let's pretend we do not know this theorem yet since it is often proven using second-countability.

To prove Radó's theorem, it is sufficient to choose $Y$ to be some appropriate open subset of $X$ and construct non-constant holomorphic map $f : Z \to \mathbb{C}$. Indeed, since $f$ will be continuous and open, any countable basis of $\mathbb{C}$ can be pulled back via $f$ to a countable basis on $Z$, and then pushed forward via $p$ to a countable basis on $Y$. When $Y$ is nice enough, $X$ will also have a countable basis.

Remove two disjoint closed disks $D_1, D_2 \subset X$ and let $Y := X \backslash (D_1 \cup D_2)$. The problem is now reduced to finding a continuous map $h$ on $\bar{Y}$ such that $h$ is harmonic on $Y$, $h \equiv 0$ along $\partial D_1$ and $h \equiv 1$ along $\partial D_2$. When such a map $h$ exists, $\partial h$ ($\frac{\partial h}{\partial z} dz$ in local coordinates) is a holomorphic 1-form and automatically induces a map on the universal cover $Z$:

$$
f : Z \to \mathbb{C}, \quad (z,[\gamma]) \mapsto \int_\gamma \partial h.
$$

Since $h$ is non-constant, $f$ is also non-constant and holomorphic. Therefore, $Y$ is second-countable and so is $X$. It remains to find a solution $h$ to the Dirichlet problem. A common approach would be the Perron method, a variant of which is stated below. [insert citation]

> **_Perron Method:_** Let $Y$ be an open subset of a Riemann surface $X$ with smooth boundary $\partial Y$ compactly contained in $X$. If $\phi: \partial Y \to \mathbb{R}$ is a continuous map and $\mathcal{F}$ is a family of all subharmonic functions $g: Y \to \mathbb{R}$ such that $g \leq \phi$ on $\partial Y$. Then, the supremum $h(x) = \sup_{g \in \mathcal{F}} g(x)$ is a continuous map on $\bar{Y}$ which is harmonic on $Y$ and has boundary value $\phi$.

This concludes the proof of Radó's theorem. As a result, tautological examples like the long plane, i.e. a product of two long lines, do not admit a complex structure. The theorem, however, does not hold for higher complex dimensions.

------
