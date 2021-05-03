---
title: 'Rotation number'
date: 2021-05-01
permalink: /posts/2021/05/rotation-number
tags:
  - Dynamical systems
---

Circle rotations provide easy and simple examples of low-dimensional dynamical systems. A natural generalisation to rotations is circle homeomorphisms. In this post, we will delve into an important invariant of circle homeomorphisms, namely the rotation number, and discuss the dynamics of circle homeomorphisms of rational rotation number.

A circle homeomorphism is a homeomorphism $f$ of the circle $S^1$ onto itself. Two models of the circle can be used, namely $\\\{ z \in \mathbb{C} : \vert z \vert = 1 \\\}$ and $\mathbb{R}\backslash \mathbb{Z}$. We will use the latter since it naturally provides us with the quotient map $\pi: \mathbb{R} \to S^1, x \mapsto x + \mathbb{Z}$. We will assume that every circle homeomorphism we are dealing with here preserves the orientation; if otherwise, the second iterate will always be orientation preserving anyway.

## Rotation number

Consider a lift $F: \mathbb{R} \to \mathbb{R}$ of $f$ via the projection $\pi$, namely $F$ is a self homeomorphism of $\mathbb{R}$ such that $\pi \circ F = f \circ \pi$. Let $x$ be your favorite real number. The **rotation number** of an orientation preserving circle homeomorphism $f$ is the quantity

$$
\tau(f) = \lim_{n \to \infty} \frac{F^n(x)-x}{n}.
$$

The limit exists because for any $n \in \mathbb{N}$, $\vert F^n(x)-x \vert \leq n$. Since any other lift is of the form $F+k$ for some fixed integer $k$, you may see how the value $k$ does not matter in the limit and thus $\tau(f)$ is independent of the choice of the lift $F$. Moreover, you can show by a rather straightforward computation of limits that $\tau(f)$ is independent of the choice of $x$.

The rotation number is invariant under topological [conjugacy](/posts/2021/03/the-fundamentals-of-topological-dynamics).

> **_Proposition:_** If two circle homeomorphism $f$ and $g$ are topologically conjugate, then $\tau(f) = \tau(g)$.

Indeed, let $g=h\circ f \circ h^{-1}$ for some circle homeomorphism $h$. Let $F$, $G$, and $H$ be the unique lifts of $f$, $g$, and $h$ via $\pi$ such that $G = H \circ F \circ H^{-1}$ and $F(0)$ and $H(0)$ lie in $[0,1)$. We can make use of the periodicity of $H$, i.e. $H(x+1)=H(x)+1$, to show that $\vert H(x)-x \vert <2$ and $\vert H^{-1}(x)-x \vert <2$ for all $x \in \mathbb{R}$. Similarly, by periodicity of $F$, $\vert F^n(x) - F^n(y) \vert < 3$ whenever $\vert x - y \vert < 2$. Therefore,

$$
\begin{align}
\tau(f) - \tau(g) & = \lim_{n \to \infty} \frac{G^n(x) - F^n(x)}{n} \\
& = \lim_{n \to \infty} \frac{H^{-1}F^n H(x) - F^n(x)}{n} \\
& = \lim_{n \to \infty} \frac{[H^{-1}F^n H(x) - F^nH(x)] + [F^nH(x) - F^n(x)]}{n} \\
& \leq \lim_{n \to \infty}  \frac{2+3}{n} = 0.
\end{align}
$$

Rotation number gives a complete picture of the dynamics of circle homeomorphisms.

> **_Poincaré's classification_** Let $f$ be a circle homeomorphism. Exactly one of the following holds.
1. $\tau(f) \in \mathbb{Q}$, $f$ has a periodic point, and the $\omega$-limit set of every point is a periodic orbit;
2. $\tau(f) \not\in \mathbb{Q}$ and $f$ is either conjugate to the irrational rotation $x+\tau(f)$ or has an invariant Cantor set.

Proving the whole statement requires rigorous and technical combinatorics. In this post, I will only focus on the rational case.

## Rational rotation number

Suppose $f$ has a periodic point $x$ of period $q$, then for any lift $F$ of $f$, $F^q(x)-x$ must be some non-negative integer $p$, which must be less than $q$ since $\vert F(z)-z \vert < 1$ for any $z$. As such, $\tau(f)=\frac{p}{q}$.

The converse is not as straightforward. Suppose $\tau(f) = \frac{p}{q}$ for some co-prime non-negative integers $p$ and $q$. By the definition of rotation number, we can show that $\tau(f^q) \equiv q\tau(f) \equiv 0 (\text{mod } 1)$ so we may as well assume that $\tau(f)=0$. If, for a contradiction, $f$ does not have any fixed points, then by compactness of $S^1$ and periodicity of $F$, $\delta := \min{ F(x)-x : x \in \mathbb{R}}$ is strictly positive. Therefore, we have a contradiction:

$$
\tau(f) = \lim_{n \to \infty} \frac{F^n(x) - x}{n} \geq \lim_{n \to \infty} \frac{n\tau}{n} = \delta > 0.
$$

In fact, we can show more: any other periodic point must have the same period $q$. Indeed, suppose $y$ is a periodic point of period $s$. Let $r = F^s(y)-y$ so then $r = kp$ and $s = kq$ for some positive integer $k$. For a contradiction, if $F^q(y)-p>y$ for some lift $F$, then by periodicity and monotonicity of $F$,

$$
F^{2q}(y)-2p = F^q (F^q(y)-p) -p > F^q(y)-y > y
$$

which inductively implies $F^{kq}(y)-kp > y$, a contradiction. Similarly, we can show that $F^q(y)-p>y$ is impossible. Hence, $y$ must have period $q$.

Let's have a look at the behaviour of a typical orbit of a point under $f$ when $\tau(f) = \frac{p}{q}$ is rational. The set $P$ of periodic points of $f$ is closed in $S^1$. Pick any non-periodic point $x \in S^1\backslash P$ and let $I=(a,b)$ be the connected component of $S^1\backslash P$ containing $x$. Since the endpoints $a$ and $b$ of $I$ are periodic points of the same period $q$, the interval $I$ is also invariant under $f^q$, i.e. $f^q(I) = I$. We then have the following two possibilities:
* If $f^q(x)>x$, then $\\\{f^{nq}(x)\\\}_{n \in \mathbb{N}}$ must be a strictly increasing sequence and it converges to the periodic point $b$;
* Else, $f^q(x)<x$ and as a consequence, $\\\{f^{nq}(x)\\\}_{n \in \mathbb{N}}$ must be a strictly decreasing sequence converging to the periodic point $a$.

In both situations, the orbit of $x$ must be asymptotic to a periodic orbit.

### References

<a name="fn1">1</a>: W. de Melo, S. van Strien. One-Dimensional Dynamics, Springer, 1993.  
<a name="fn2">2</a>: A. Katok, B. Hasselblatt. Introduction to the Modern Theory of Dynamical Systems. Encyclopedia of Mathematics and its Applications, volume 54. Cambridge University Press, Cambridge, 1995.  

------
