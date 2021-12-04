---
title: '10 Equivalent Ways of Defining Quasicircles'
date: 2021-12-04
permalink: /posts/2021/12/quasicircles
tags:
  - Complex analysis
---

I have been dealing with a lot of quasicircles lately, and I was thinking it would be practical to write a post about its many equivalent definitions. Quasicircles are Jordan curves which satisfy certain nice analytic and geometric conditions. While conformal maps of the Riemann sphere (aka Möbius transformations) map circles to circles, quasiconformal maps map quasicircles to quasicircles.

We will denote by $\hat{\mathbb{C}}$ the Riemann sphere $\mathbb{C} \cup \\\{ \infty \\\}$. Denote by $\mathbb{D}$ the standard unit disk $\\\{\vert z \vert < 1 \\\}$. We will use the spherical metric throughout, although you can replace it with the Euclidean metric as long as the objects you are dealing with is away from $\infty$. Denote by $\mathbb{D}(z,r)$ the disk centered at $z$ of radius $r>0$ in the spherical metric.

**_Definition & Theorem:_** Let $Z$ be a Jordan curve in $\hat{\mathbb{C}}$, and let $X$ and $Y$ be the components of $\hat{\mathbb{C}} \backslash Z$. Then, Z is a quasicircle if it satisfies any of the following equivalent definitions:
1. There is a quasiconformal homeomorphism $\phi: \hat{\mathbb{C}} \to \hat{\mathbb{C}}$ mapping the unit circle $\mathbb{T}$ onto $Z$;
2. Any Riemann mapping $f: X \to \mathbb{D}$ extends to a quasiconformal map of $\hat{\mathbb{C}}$;
3. There is some $K\geq 1$ such that for every $x_1, x_2 \in X$, there is a $K$-quasiconformal map $f : \hat{\mathbb{C}} \to \hat{\mathbb{C}}$ such that $f(X)=X$ and $f(x_1)=x_2$;
4. There is some $c\geq 1$ such that if for any four cyclically ordered distinct points $z_1, z_2, z_3, z_4 \in Z$, if the rectangle $R_x = X(z_1,z_2,z_3,z_4)$ has modulus $\text{mod}(\Gamma_x) = 1$ then the rectangle $R_y = Y(z_4,z_3,z_2,z_1)$ has modulus $\text{mod}(\Gamma_y) \leq c$;
5. There is some $c\geq 2$ such that if $I$ and $J$ are two disjoint closed intervals on $Z$, the families $\Gamma_{\hat{\mathbb{C}}}$ and $\Gamma_{X}$ of all curves connecting $I$ and $J$ in $\hat{\mathbb{C}}$ and $X$ respectively, the extremal lengths $\lambda(\Gamma_{\hat{\mathbb{C}}})$ and $\lambda(\Gamma_X)$ satisfy $\lambda(\Gamma_{\hat{\mathbb{C}}}) \leq c \cdot \lambda(\Gamma_X)$.
6. $Z$ satisfies the bounded turning condition: there is some $c >0$ such that for any two distinct points $x,y \in Z$, if $\gamma_1$ and $\gamma_2$ are the two components of $Z \backslash \\\{x,y\\\}$, then $\min_{i=1,2} \text{diam}(\gamma_i) \leq c \cdot d(x,y)$;
7. $Z$ is linearly locally connected: there is some $c \geq 1$ such that for every $z \in Z$ and $r>0$, any two points in $Z \cap \mathbb{D}(z,r)$ can be joined by an interval in $Z \cap \mathbb{D}(z,cr)$, and any two points in $Z \backslash \mathbb{D}(z,r)$ can be joined by an interval in $Z \backslash \mathbb{D}(z,r/c)$;
8. If $f : X \to \mathbb{D}$ and $g : Y \to \hat{\mathbb{C}} \backslash \bar{\mathbb{D}}$ are conformal isomorphisms, considering their extensions to the boundary, the composition $h = g \circ f^{-1}$ is a quasisymmetric map on the unit circle $\mathbb{T}$: there is some $c\geq 1$ such that for any $z_1,z_2,z_3 \in \mathbb{T}$,
$$
\frac{d(h(x_1),h(x_2))}{d(h(x_1),h(x_3))} \leq c \frac{d(x_1,x_2)}{d(x_1,x_3)}.
$$
9. For any $x \in X$ and $y \in Y$, the harmonic measure $\omega_X(x, \cdot)$ of $Z$ in $X$ about $x$ is quasisymmetrically equivalent to the harmonic measure $\omega_Y(y, \cdot)$. More precisely, there is some $c\geq 1$ such that every two adjacent intervals $I, J \subset Z$ satisfy
$$
\frac{\omega_X(x,I)}{\omega_X(x,J)} \leq c \frac{\omega_Y(y,I)}{\omega_Y(y,J)};
$$
10. There is some $c>0$ such that for any univalent function $f: X \to \mathbb{C}$, the Schwarzian derivative $S_f = \left( \frac{f''}{f'}\right)' - \frac{1}{2}\left( \frac{f''}{f'}\right)^2$ and the hyperbolic metric $\rho_X(z) dz$ on $X$ satisfy $\vert S_f \vert \leq c \cdot \rho_X^2$ on X.

##

### References

<a name="fn1">1</a>: L. Ahlfors. Lectures on Quasiconformal Mappings. Van Nostrand, 1966.  

------
