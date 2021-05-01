---
title: 'Rotation number'
date: 2021-05-01
permalink: /posts/2021/05/rotation-number
tags:
  - Dynamical systems
---

Circle rotations provide easy and simple examples of low-dimensional dynamical systems. A natural generalisation to rotations is circle homeomorphisms. In this post, we will delve into an important invariant of circle homeomorphisms, namely the rotation number, and Poincaré's classification of circle homeomorphisms.

A circle homeomorphism is a homeomorphism $f$ of the circle $S^1$ onto itself. Two models of the circle can be used, namely $\\\{ z \in \mathbb{C} : \vert z \vert = 1 \\\}$ and $\mathbb{R}\backslash \mathbb{Z}$. We will use the latter since it naturally provides us with the quotient map $\pi: \mathbb{R} \to S^1, x \mapsto x + \mathbb{Z}$. We will assume that every circle homeomorphism we are dealing with here preserves the orientation; if otherwise, the second iterate will always be orientation preserving anyway.

## Rotation number

Consider a lift $F: \mathbb{R} \to \mathbb{R}$ of $f$ via the projection $\pi$, namely $F$ is a self homeomorphism of $\mathbb{R}$ such that $\pi \circ F = f \circ \pi$. Let $x$ be your favorite real number. The **rotation number** of an orientation preserving circle homeomorphism $f$ is the quantity

$$
\tau(f) = \lim_{n \to \infty} \frac{F^n(x)-x}{n}.
$$

The limit exists because for any $n \in \mathbb{N}$, $\vert F^n(x)-x \vert \leq n$. Since any other lift is of the form $F+k$ for some fixed integer $k$, you may see how the value $k$ does not matter in the limit and thus $\tau(f)$ is independent of the choice of the lift $F$. Moreover, you can show by a rather straightforward computation of limits that $\tau(f)$ is independent of the choice of $x$.

The rotation number is invariant under topological [conjugacy](/posts/2021/03/the-fundamentals-of-topological-dynamics).

> **_Proposition:_** If two circle homeomorphism $f$ and $g$ are topologically conjugate, then $\tau(f) = \tau(g)$.

Indeed, let $g=h\circ f \circ h^{-1}$ for some circle homeomorphism $h$. Let $F$, $G$, and $H$ be the unique lifts of $f$, $g$, and $h$ via $\pi$ such that $G = H \circ F \circ H^{-1}$ and $F(0)$ and $H(0)$ lie in $[0,1)$. We can make use of the periodicity of $H$, i.e. $H(x+1)=H(x)$, to show that $\vert H(x)-x \vert <2$ and $\vert H^{-1}(x)-x \vert 2$ for all $x \in \mathbb{R}$, and $\vert F^n(x) - F^n(y) \vert < 3$ if $\vert x - y \vert < 3$. Therefore,

$$
\begin{align}
\tau(f) - \tau(g) & = \lim_{n \to \infty} \frac{G^n(x) - F^n(x)}{n} = \lim_{n \to \infty} \frac{H^{-1}F^n H(x) - F^n(x)}{n} \\
& = \lim_{n \to \infty} \frac{[H^{-1}F^n H(x) - F^nH(x)] + [F^nH(x) - F^n(x)]}{n} < \lim_{n \to \infty}  \frac{2+3}{n} = 0. 
$$

### References

<a name="fn1">1</a>: W. de Melo, S. van Strien. One-Dimensional Dynamics, Springer, 1993.  
<a name="fn2">2</a>: A. Katok, B. Hasselblatt. Introduction to the Modern Theory of Dynamical Systems. Encyclopedia of Mathematics and its Applications, volume 54. Cambridge University Press, Cambridge, 1995.  

------
