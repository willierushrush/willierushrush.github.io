---
title: 'Hartogs Extension Theorem'
date: 2022-06-5
permalink: /posts/2022/06/hartogs-extension-theorem
tags:
  - Several complex variables
  - Complex geometry
---

Hartogs extension theorem is one of the few fundamental results in analytic continuation that distinguishes the study of several complex variables and that of one complex variable.

> **_Theorem:_** Let $D$ be a domain (non-empty connected open set) in $\mathbb{C}^n$ for $n\geq 2$ and let $K$ be a compact subset of $D$ such that $D\backslash K$ is connected. Then, every holomorphic function $f: D\backslash K \to \mathbb{C}$ extends uniquely to a holomorphic function on $D$.

Hartogs extension theorem immediately tells us that in several complex variables, holomorphic functions cannot have isolated non-removable singularities! I would like to emphasise that this extension theorem is special for dimensions $2$ or higher. In one dimension, we can construct straightforward counterexamples, such as $\frac{1}{z}$ or general holomorphic functions with isolated singularities. Another immediate consequence is the following.

> **_Corollary:_** For any holomorphic function $f: U \subset \mathbb{C}^n \to \mathbb{C}$, the zero set $Z(f)=\{ z \in U \: : \: f(z)=0\}$ cannot be compactly contained in $U$.

Why is this so? Given such $f$, the function $1/f$ is a well-defined holomorphic function on $U \backslash Z(f)$. If $Z(f)$ were to be compactly contained in $U$, then there is a compact set $K$ containing $Z(f)$ such that $U \backslash K$ is connected. By Hartogs extension theorem, $1/f$ must extend holomorphically to the whole domain $U$, which is impossible!

## A very elementary proof

There are many ways to prove the extension theorem. The standard approach uses the d-bar Poincaré lemma, also known as the Dolbeault-Grothendieck lemma. Before going into that, let's look at a more elementary case where our domain is the 2-dimensional unit polydisk $\mathbb{D}(0,1) = \\\{ (z_1,z_2) \in \mathbb{C}^2 \: : \: \vert z_1\vert < 1, \vert z_2 \vert <1 \\\}$ and $K$ is a smaller closed polydisk $K = \{ (z_1,z_2) \in \mathbb{C}^2 \: : \: \vert z_1\vert \leq \epsilon, \vert z_2 \vert \leq \epsilon \\\}$ for some any $0<\epsilon<1$. (See Huybrechts<sup>[2](#fn2)</sup> Prop 1.1.4)

Any holomorphic function $f$ on $D\backslash K$ has a Laurent series representation

$$
f(z_1,z_2) = \sum_{j=-\infty}^\infty a_j(z_1) z_2^j, \quad a_j(z_1) = \frac{1}{2\pi i} \oint_{\vert w \vert = \delta} \frac{f(z_1,w)}{w^{j+1}} dw,
$$

for any $\delta \in (\epsilon,1)$. For $\epsilon < \vert z_2 \vert$, $f$ is holomorphic and thus $a_j(z_1) = 0$ for $j<0$. By the identity principle, $a_j \equiv 0$ for all $j<0$, so then the series expansion for $f$ becomes a genuine Taylor series $\sum_{j=0}^\infty a_j(z_1) z_2^j$. This implies that $f$ extends holomorphically to the whole polydisk $D$.

## General proof

Once we find a holomorphic extension $F: D \to \mathbb{C}$ of $f$, uniqueness follows immediately from the identity theorem. Thus, the non-trivial step here is showing the existence of $F$.

There exists some small $\epsilon >0$ such that the $2\epsilon$-neighborhood $K_\epsilon$ is compactly contained in $D$ and thus $D \backslash K$ is still connected. Pick a smooth function $c : \mathbb{C}^n \to [0,1]$ such that $c \equiv 0$ on the $\epsilon$-neighborhood $K_\epsilon$ of $K$ and $c \equiv 1$ on $\mathbb{C}^n \backslash K_{2\epsilon}$. Then, define:

$$
g = \begin{cases}
cf & \text{ on } D\backslash K, \\
0 & \text{ on } K.
\end{cases}
$$

This new function $g: D \to \mathcc{C}$ is a smooth extension for $f$ restricted to $D \backslash K_{2\epsilon}$. Then, $\bar{\partial} g$ extends to a global smooth $(0,1)$-form on $\mathbb{C}^n$ that has compact support because it vanishes outside of $K_{2\epsilon}$. Obviously, $\bar{\partial} g$ is also $\bar{\partial}$-closed since $\bar{\partial} \bar{\partial} g \equiv 0$. We can then apply the following lemma.

> **_Dolbeault–Grothendieck lemma:_** Given a smooth $(0,1)$-form $w$ on $\mathbb{C}^n$ that is $\bar{\partial}$-closed and has compact support, then $w$ is $\bar{\partial}$-closed: there exists a smooth solution $u$ to the equation $\bar{\partial} u = w$, unique up to additive constant.

With this lemma, there exists a unique smooth, compactly supported function $u : \mathbb{C}^n \to \mathbb{C}$ satisfying the equation $\bar{\partial} u = \bar{\partial} g$. Then, $F := g-u$ is a holomorphic function on $D$ and outside of $K_{2\epsilon}$, $F$ coincides with $f$. By the identity theorem, $F$ must coincide with $f$ on $D \backslash K$ and $F$ is the unique holomorphic extension of $f$ on $D$ that we are looking for!

### References

<a name="fn1">1</a>: L. Hörmander. An Introduction to Complex Analysis in Several Variables. Van Nostrand Reinhold Company, New York, 1966.      
<a name="fn1">2</a>: D. Huybrechts. Complex Geometry. Springer-Verlag Berlin Heidelberg, 2005.
------
