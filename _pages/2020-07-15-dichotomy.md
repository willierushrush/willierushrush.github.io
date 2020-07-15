---
title: 'Dichotomy of quadratic Julia sets'
date: 2020-07-15
permalink: /test/
tags:
  - Holomorphic dynamics
  - Dynamical systems
---
permalink: /posts/2020/07/dichotomy/?

Consider the family of quadratics $f_c(z) = z^2 + c$ parametrised by $c \in \mathbb{C}$. Recall from [here](/posts/2020/06/fatou_and_julia/) that the filled Julia set $K(f_c)$ of $f_c$ is the complement of the basin of infinity $B_{f_c}(\infty) = \\{ z \in \mathbb{C} | f_c^n(z) \to \infty \\}$, and the Julia set $J(f_c)$ is the boundary of $K(f_c)$. I mentioned on my [post](/posts/2020/07/mandelbrot-1/) on the Mandelbrot set is known that the Julia set $f_c$ is either connected or Cantor.

> **_Dichotomy Theorem:_** For any arbitrary $c \in \mathbb{C}$, either $K(f_c)$ contains $0$ and is connected, or $K(f_c)$ does not contain $0$ and is homeomorphic to the Cantor set.

The map $f_c$ has a few crucial properties:
* $\infty$ is a superattracting fixed point of $f_c$, i.e. it is both an attracting fixed point and a critical point,
* $f_c$ is a holomorphic self double covering of $\mathbb{P}^1$ branched at critical points $0$ and $\infty$.

Suppose first that $0$ lies in $K(f_c)$. Denote $\mathbb{D}_R$ by the finite open disk $\\{ |z| < R\\}$. By topological attractivity of $\infty$, if $U_0 = \mathbb{P}^1 \backslash \overline{\mathbb{D}}_R$, then $U_0$ is compactly contained in $f^{-1}(U_0)$ for some sufficiently large $R>0$. Let $U_n = f^{-n} (U_0)$, then each map $f: U_{n+1} \to U_n$ is a double covering branched at $\infty$. We can use Riemann-Hurwitz formula on $f: U_{n+1} \to U_n$ to obtain the equation
$$
\chi(U_n) = 2 \chi(U_{n+1}) - 1
$$
where $\chi$ denotes Euler characteristic. If $R>0$ is taken sufficiently large, by conformality near $\infty$, $U_0$ must be simply connected and thus $\chi(U_0) = 1$. By the formula, it follows inductively that every $U_n$ is simply connected. However, by topological attractivity of $f$ around $\infty$, the domains $U_n$ form an exhaustion of the basin of infinity $\mathcal{A}(z_0)$. Thus, $\mathcal{A}(z_0)$ must be simply connected and its complement $K(f_c)$ has to be connected.

Suppose instead that $0$ lies in the basin of infinity $\mathcal{A}(\infty)$. The key to this problem is by looking at the basin of infinity through the Böttcher map $B_c : \mathbb{P}^1 \backslash K(f_c) \to \mathbb{P}^1 \backslash \bar{\mathbb{D}}$. This is a unique holomorphic map which satisfies the functional equation $B_c \circ f_c (z) = B_c(z)^2$ for all $z \in \mathbb{P}^1 \backslash K(f_c)$, which essentially states that $f_c$ behaves like a doubling map $z^2$ outside the filled Julia set.

Milnor's book<sup>[3](#fn3)</sup> in $\S 9$ explains clearly that whenever we have a holomorphic map $f$ with a fixed point $z_0$ such that locally $f(z) = z_0 + a_d(z-z_0)^d + O((z-a)^{d+1})$ near $a$, then $f$ admits a Böttcher coordinate $B : \mathcal{A}(z_0) \to \mathbb{D}$ which is a holomorphic map on the basin of attraction $\mathcal{A}(z_0)$ satisfying the following properties:
* $B(a) = 0$ and $B$ is conformal around $a$,
* $B \circ f(z) = B(z)^d$ for all $z \in \mathcal{A}(z_0)$,
* $B$ is unique up to multiplication by $(d-1)$<sup>th</sup> root of unity.
In the context of quadratic maps, we apply this to $f = f_c$, $z_0 = \infty$; the Böttcher coordinate is unique because $d=2$. The Böttcher map $B_c$ for $f_c$ is obtained by post-composing $B$ with inversion $z^{-1}$.

The functional equation $B_c \circ f(z) = B_c(z)^2$ induces the equation $B \circ f^n(z) = B_c(z)^{2^n}$ and $B_c'(f^n(z)) (f^n)'(z) = 2^n B_c'(z) B_c(z)^{2^n-1}$. We can deduce two things from here:
* Whenever $z$ is a critical point of $B_c$, then every forward iterate $f^n(z)$ where $n \geq 1$ is also a critical point of $B_c$, but this will contradict conformality of $B_c$ near $\infty$ since $f^n(z) \to \infty$. As such $B_c$ has no critical points on $\mathcal{A}_f$.
* When $z = f^n(0)$ lies in $\mathcal{A}(\infty)$, ...


### References

<a name="fn1">1</a>: A. Beardon. Iteration of Rational Functions. Grad. Texts Math. 132, Springer-Verlag, NY, 1984.  
<a name="fn2">2</a>: J. Milnor. Dynamics in one complex variable. Princeton University Press, third edition, 2006.  

------
