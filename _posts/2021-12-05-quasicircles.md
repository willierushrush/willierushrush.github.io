---
title: '10 Equivalent Ways of Defining Quasicircles'
date: 2021-12-05
permalink: /posts/2021/12/quasicircles
tags:
  - Complex analysis
---

I have been dealing with a lot of quasicircles lately, and I was thinking it would be practical to write a post about its many equivalent definitions. Quasicircles are Jordan curves which satisfy certain nice analytic and geometric conditions. While conformal maps of the Riemann sphere (aka Möbius transformations) map circles to circles, quasiconformal maps map quasicircles to quasicircles.

We will denote by $\hat{\mathbb{C}}$ the Riemann sphere $\mathbb{C} \cup \\\{ \infty \\\}$. Denote by $\mathbb{D}$ the standard unit disk $\\\{\vert z \vert < 1 \\\}$. We will use the spherical metric throughout, although you can replace it with the Euclidean metric as long as the objects you are dealing with is away from $\infty$. Denote by $\mathbb{D}(z,r)$ the open disk centered at $z$ of radius $r>0$ in the spherical metric.

**_Definition & Theorem:_** Let $Z$ be a Jordan curve in $\hat{\mathbb{C}}$, and let $X$ and $Y$ be the components of $\hat{\mathbb{C}} \backslash Z$. Then, Z is a quasicircle if it satisfies any of the following equivalent definitions:
1. There is a $K$-quasiconformal homeomorphism $\phi: \hat{\mathbb{C}} \to \hat{\mathbb{C}}$ mapping the unit circle $\mathbb{T}$ onto $Z$;
2. There is some $K\geq 1$ such that any Riemann mapping $f: X \to \mathbb{D}$ extends to a $K$-quasiconformal map of $\hat{\mathbb{C}}$;
3. There is some $K\geq 1$ such that for every $x_1, x_2 \in X$, there is a $K$-quasiconformal map $\psi : \hat{\mathbb{C}} \to \hat{\mathbb{C}}$ such that $\psi(X)=X$ and $\psi(x_1)=x_2$;
4. There is some $K\geq 1$ such that if for any four cyclically ordered distinct points $z_1, z_2, z_3, z_4 \in Z$, if the quadrilateral $R_x = X(z_1,z_2,z_3,z_4)$ has modulus $\text{mod}(R_x) = 1$ then the quadrilateral $R_y = Y(z_4,z_3,z_2,z_1)$ has modulus $\text{mod}(R_y) \leq K$;
5. There is some $c\geq 1$ such that if $I$ and $J$ are two disjoint closed intervals on $Z$ and if $\Gamma_{\hat{\mathbb{C}}}$ and $\Gamma_{X}$ are the families of all paths connecting $I$ and $J$ in $\hat{\mathbb{C}}$ and $X$ respectively, the extremal lengths $\lambda(\Gamma_{\hat{\mathbb{C}}})$ and $\lambda(\Gamma_X)$ satisfy $\lambda(\Gamma_{\hat{\mathbb{C}}}) \leq 2c \cdot \lambda(\Gamma_X)$.
6. If $f : X \to \mathbb{D}$ and $g : Y \to \hat{\mathbb{C}} \backslash \bar{\mathbb{D}}$ are conformal isomorphisms, considering their extensions to the boundary, the composition $h = g \circ f^{-1}$ is a quasisymmetric map on the unit circle $\mathbb{T}$: there is some $c\geq 1$ such that for any $z_1,z_2,z_3 \in \mathbb{T}$,
$$
\frac{d(h(x_1),h(x_2))}{d(h(x_1),h(x_3))} \leq c \frac{d(x_1,x_2)}{d(x_1,x_3)}.
$$
7. For any $x \in X$ and $y \in Y$, the harmonic measure $\omega_X(x, \cdot)$ of $Z$ in $X$ about $x$ is quasisymmetrically equivalent to the harmonic measure $\omega_Y(y, \cdot)$. More precisely, there is some $c\geq 1$ such that every two adjacent intervals $I, J \subset Z$ satisfy
$$
\frac{\omega_X(x,I)}{\omega_X(x,J)} \leq c \frac{\omega_Y(y,I)}{\omega_Y(y,J)};
$$
8. $Z$ satisfies the bounded turning condition: there is some $c \geq 1$ such that for any two distinct points $x,y \in Z$, if $\gamma_1$ and $\gamma_2$ are the two components of $Z \backslash \\\{x,y\\\}$, then $\min_{i=1,2} \text{diam}(\gamma_i) \leq c \cdot d(x,y)$;
9. $Z$ is linearly locally connected: there is some $c \geq 1$ such that for every $z \in Z$ and $r>0$, any two points in $Z \cap \overline{\mathbb{D}(z,r)}$ can be joined by an interval in $Z \cap \overline{\mathbb{D}(z,cr)}$, and any two points in $Z \backslash \mathbb{D}(z,r)$ can be joined by an interval in $Z \backslash \mathbb{D}(z,r/c)$;
10. There is some $a>0$ such that for any univalent function $f: X \to \mathbb{C}$, the Schwarzian derivative $S_f = \left( \frac{f''}{f'}\right)' - \frac{1}{2}\left( \frac{f''}{f'}\right)^2$ and the hyperbolic metric $\rho_X(z) dz$ on $X$ satisfy $\vert S_f \vert \leq a \cdot \rho_X^2$ on X.

The constants $K$ and $c$ above are in general different for each property, but they do depend on each other. It is not difficult to show that the minimal constant $K=1$ and $c=1$ for properties 1-5 and 7-9 are achieved by circles.

## Through quasiconformal maps
The typical definition of quasicircles is 1. Recall that quasiconformal maps locally distort angles up to some finite constant. This means that unlike a circle, $Z$ is allowed to have angles at each point but these angles must be definite. In particular, $Z$ should contain no cusps!

From 1, property 2 is based on the fact that $g = f \circ \phi^{-1}: \mathbb{D}$ is a quasiconformal self map of the unit disk $\mathbb{D}$ and it has a quasiconformal extension to the whole $\hat{\mathbb{C}}$ that is $\mathbb{T}$-symmetric, so then $f$ extends to $\phi \circ g$ on $\hat{\mathbb{C}}$. From 2, property 3 satisfied by $\psi=f^{-1}\cir g\circ f$ where $g$ is a Möbius transformation which sends $f(x_1)$ to $f(x_2)$.

Refer to this [post](/posts/2020/09/extremal-length) for the definition of topological quadrilaterals. Property 2 implies property 4: if $f: X \to \mathbb{D}$ is a Riemann mapping, then by the symmetry of $\partial \mathbb{D}$ and by conformal invariance of the modulus, $\text{mod}(f(R_y)) = \text{mod}(f(R_x)) = \text{mod}(R_x) = 1$, but then by property 2, $\text{mod}(R_y) \leq K \text{mod}(f(R_y))$.

## Through quasisymmeties


## Through basic geometric analysis
The bounded turning condition (property 6) is another popular characterisation because it is the easiest to state. Notice that at this condition fails near a cusp because points get much closer together but the diameter of the shortest interval on $Z$ joining these two points decreases much more slowly.

## Through

## Through univalent functions

### References

<a name="fn1">1</a>: L. Ahlfors. Lectures on Quasiconformal Mappings. Van Nostrand, 1966.  

------
