---
title: 'Dichotomy of quadratic Julia sets'
date: 2020-08-12
permalink: /posts/2020/08/dichotomy/
tags:
  - Holomorphic dynamics
  - Dynamical systems
---
permalink: /posts/2020/07/dichotomy/?

Consider the family of quadratics $f_c(z) = z^2 + c$ parametrised by $c \in \mathbb{C}$. Recall from [here](/posts/2020/06/fatou_and_julia/) that the filled Julia set $K(f_c)$ of $f_c$ is the complement of the basin of infinity
$$
A(\infty) = \\{ z \in \mathbb{C} \vert f_c^n(z) \to \infty \\},
$$
and the Julia set $J(f_c)$ is the boundary of $K(f_c)$. I mentioned on my [post](/posts/2020/07/mandelbrot-1/) on the Mandelbrot set is known that the Julia set $f_c$ is either connected or Cantor.

> **_Dichotomy Theorem:_** For any arbitrary $c \in \mathbb{C}$, either $K(f_c)$ contains $0$ and is connected, or $K(f_c)$ does not contain $0$ and is homeomorphic to the Cantor set.

The map $f_c$ has a few crucial properties:
* $\infty$ is a superattracting fixed point of $f_c$, i.e. it is both an attracting fixed point and a critical point,
* $f_c$ is a holomorphic self double covering of $\mathbb{P}^1$ branched at critical points $0$ and $\infty$.

Denote $U_0$ by the open neighbourhood $\\{ \lvert z \rvert \geq R \\} \cup \\{ \infty\\}$ for some large $R>1$ and let $U_n = f^{-n} (U_0)$. By topological attractivity, we can assume by taking $R>0$ to be sufficiently large that $U_0$ is compactly contained in $U_1$ and $U_0$ is be simply connected. It the follows that each $U_n$ is compactly contained in $U_{n+1}$ and that the domains $U_n$ form an exhaustion of the basin of infinity $\mathcal{A}(z_0)$.

Suppose first that $0$ lies in $K(f_c)$. Since each $U_n$ does not contain $0$, each map $f: U_{n+1} \to U_n$ is a double covering branched only at $\infty$. We can use Riemann-Hurwitz formula on $f: U_{n+1} \to U_n$ to obtain the equation
$$
\chi(U_{n+1}) = 2 \chi(U_n) - 1
$$
where $\chi$ denotes Euler characteristic. Thus, $\chi(U_0) = 1$. It follows inductively from the formula that every $U_n$ is simply connected. Therefore, $\mathcal{A}(z_0)$ must be simply connected and its complement $K(f_c)$ has to be connected.

Suppose instead that $0$ lies in the basin of infinity $\mathcal{A}(\infty)$. We can take the smallest number $N$ such that the critical value $c$ lies in the closure $\overline{U_{N-1}}$. By perturbing $R$, we can assume that $c$ lies on the boundary of $U_{N-1}$, and consequently $0$ lies on the boundary of $U_{N}$. The boundary $\partial U_0$ is a Jordan curve. Since $U_n$ is connected and $f_c$ restricts to a double cover of $\partial U_{n}$ onto $\partial U_{n-1}$ for all $n\leq N-1$, we see inductively that each $\partial U_{n}$ is a Jordan curve for $n \leq N-1$. However, the boundary of $U_N$ will now be a bouquet of two circles since $f$ restricts to a double cover of $\partial U_{N}$ onto the Jordan curve $\partial U_{N-1}$ branched at the unique critical point at $0$.

Let $V$ be the domain $\mathbb{P}^1 \backslash \overline{U_{N-1}}$ and let $V_1$, $V_2$ be the two connected components of $\mathbb{P}^1 \backslash \overline{U_{N}}$. The map $f_c$ restricts to a double covering of $V_1 \cup V_2$ onto $V$, so then the inverse branches $g_1 : V_1 \to V$ and $g_2 : V_2 \to V$ of $f_c$ are conformal isomorphisms. Since each $U_n$ is compactly contained in $U_{n+1}$, both $V_1$ and $V_2$ are compactly contained in $V$. The rest follows from Schwarz Lemma.


### References

<a name="fn1">1</a>: A. Beardon. Iteration of Rational Functions. Grad. Texts Math. 132, Springer-Verlag, NY, 1984.  
<a name="fn2">2</a>: J. Milnor. Dynamics in one complex variable. Princeton University Press, third edition, 2006.  

------