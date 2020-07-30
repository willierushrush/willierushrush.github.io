---
title: 'Conformal metrics on Riemann surfaces'
date: 2020-07-30
permalink: /conformal_metrics/
tags:
  - Riemann Surfaces
---

As smooth two dimensional smooth real manifolds, Riemann surfaces admit Riemannian metrics. In the study of Riemann surfaces, it is more interesting to look at those Riemannian metrics which behave nicely under conformal maps between Riemann surfaces. This gives rise to conformal metrics.

## Riemannian metrics

Recall that a **Riemannian metric** $g$ on a smooth real $n$-manifold $M$ is a (0,2)-tensor field; at each point $p \in M$, we have a symmetric bilinear and positive definite map $g_p : T_p M \times T_p M \to \mathbb{R}$. On any smooth local charts, $g$ can be expressed as $g = \sum_{1\leq i,j\leq n} g_{ij} dx_i \tensor dx_j$ for some symmetric and positive definite $n \times n$ matrix of smooth functions $g_{ij}$. For example, $\mathbb{R}^n$ admits the flat metric $g = \sum_{i=1}^n dx_i \tensor dx_i$ where the matrix $g_{ij}$ is globally the identity matrix.

The pair $(M, g)$ is often called a **Riemannian manifold**. A simple fact in this matter is that every smooth real manifold $M$ admits a Riemannian manifold structure. Indeed, by partition of unity, we can glue together a collection of flat metrics on each local chart to form a global Riemannian metric on $M$.

The metric $g$ is what gives $M$ some geometry. At every point $p$, $g$ gives us a norm on the tangent space defined by $\lvert v \rvert_g = \sqrt{g(v,v)}$ for any $v \in T_p M$. We can define the angle between two tangent vectors $v, w \in T_p M$ at a point $p$ to be the value $\theta$ such that the cosine rule holds:

$$
\cos \theta = \frac{g_p(v,w)}{\lvert v\rvert_g \lvert w \rvert_g }.
$$

We can also define the length of a smooth curve $\gamma : [a,b] \to M$ on $M$ to be

$$
L(\gamma) = \int_a^b \lvert \gamma'(t) \rvert_g dt,
$$

where $\gamma'(t)$ is the tangent vector on $T_{\gamma(t)}M$ tangent to the curve $\gamma$. The generalisation for piecewise smooth curves and even rectifiable curves is rather obvious. A standard use of change of variables formula should convince you that the length of a curve is independent of parametrisation. The distance $d(p,q)$ between two points $p,q$ on $M$ is taken to be the infimum of lengths of piecewise smooth curves in $M$ from $p$ to $q$. When $M$ is connected, the metric space topology induced by $d$ coincides with the original topology of $M$. A curve $\gamma : [a,b] \to M$, where $-\infty \leq a < b \leq \infty$, is a geodesic if it locally minimises distance. In other words, for sufficiently small closed interval $[c,d]$ in $[a,b]$, the length of $\gamma\rvert_{[c,d]}$ is equal to the distance $d(\gamma(c), \gamma(d))$.

Every immersion $f: M \to (N,h)$ from a smooth manifold $M$ to a Riemannian manifold $N$ induces the **pullback metric** $f^\*h$ on $M$ defined by $f^\*h_p(v,w) := h_p(df_p(v), df_p(w))$ at every point $p \in M$ for any $v,w \in N$. A smooth map $f: (M, g) \to (N,h)$ between two Riemannian manifolds is a **local isometry** if it is a local diffeomorphism and the metric $g$ coincides with the pullback metric $f^\*h$; $f$ is an **isometry** if additionally it is a diffeomorphism. As the name implies, a local/global isometry preserves lengths locally/globally.

## Conformal metrics

When $M$ is a Riemann surface, we say that a Riemannian metric $g$ on $M$ is **conformal** if on each local chart, $g$ can be written as $\rho(z)^2 \lvert dz \rvert$ (alternatively, $\rho(z)^2 (dx^2 + dy^2)$ or $\rho(z)^2 dz d\bar{z}$) for some smooth positive function $\rho(z)$. The corresponding matrix $g_{ij}$ will be precisely $\rho(z)^2 I_2$ where $I_2$ is the $2 \times 2$ identity matrix. It is common to use the notation $\rho(z) \lvert dz \rvert$ to refer to $g$. We are still able to argue by partition of unity that every Riemann surface admits a conformal metric.

The conformal metric $\rho(z) \lvert dz \rvert$ gives rise to a geometry on $M$. As the name suggests, on each local chart, angles with respect to $\rho(z) \lvert dz \rvert$ are the same as angles with respect to the flat metric $\lvert dz \rvert$ because they only differ by a positive factor of $\lambda^2$. The $\rho$-length of a curve $\gamma : [a,b] \to M$ is

$$
L_\rho(\gamma) = \int_\gamma \rho(z) \lvert dz \rvert.
$$

The $\rho$-distance between two points are defined similarly as before. The $\rho$-area of a measurable subset $E$ of $M$ is

$$
A_\rho(E) = \int_E \rho(x+iy)^2 dx \wedge dy.
$$

The curvature $K$ of $(M,\rho)$ at a point $p \in M$ is defined locally to be

$$
K(p) := \frac{\Delta \log \rho(p)}{\rho(p)^2},
$$

where $\Delta = 4\frac{\partial}{\partial z} \frac{\partial}{\partial \bar{z}}$ is the usual Laplacian operator. (I am trying to avoid introducing the Levi-Civita connection or Riemannian curvature tensor, but if you do know these objects, you may wish to confirm that $K$ coincides with the Gaussian curvature.)

Let's look at some examples of conformal metrics on commonly found Riemann surfaces. We shall do this based on the classification. (See my previous [post](/posts/2020/06/classificaiton/).)

## Spherical metric

Stereographic projection $P : S^2 \to \mathbb{P}^1$ is a diffeomorphism from the unit sphere $S^2 \subset \mathbb{R}^3$ to the Riemann sphere $\mathbb{P}^1 = \mathbb{C} \cup \\{\infty\\}$ given in spherical coordinates by $P(\theta,\phi) = \cot(\frac{\theta}{2})e^{i\phi}$ when $\theta \neq 0$ and $\infty$ when $\theta = 0$. The natural round metric $d\theta^2 + \sin^2\theta d\phi^2$ on the unit sphere $S^2$ can be pushed forward by $P$ to obtain the metric

$$
\frac{4 dz d\bar{z}}{1+ \lvert z \rvert^2}
$$

on $\mathbb{P}^1$ in local coordinates away from $\infty$. This is in fact a conformal metric $\rho(z) \lvert dz\rvert$ where $\rho(z) = \frac{2}{1+\lvert z \rvert^2}$. Unsurprisingly, this is often called the round / spherical / Fubini-Study metric on $\mathbb{P}^1$. Similar to $S^2$ equipped with the round metric, $(\mathbb{P}^1,\rho)$ has total area $4 \pi$ and constant curvature $K \equiv 1$. Geodesics of $\mathbb{P}^1.

## Flat metric

The complex plane $\mathbb{C}$ is trivially equipped with the flat metric $\lvert dz \rvert$ with uniform density $\rho(z) \equiv 1$ and constant curvature zero. The only isometries of $\C$ are translations $z+a$ and all geodesics of $\mathbb{C}$ are straight lines. This $\mathbb{C}$ case is not very exciting, so we'll go straight to other parabolic Riemann surfaces.

Let $X$ be the punctured plane $\mathbb{C}^\*$ or a complex torus and let $p : \mathbb{C} \to X$ be its universal cover. We can push forward the flat metric $g = \lvert dz \rvert$ to a metric $p_\*g$ defined by

$$
p_\*g(z) = \frac{\rho(w)}{\lvert p'(w)\rvert}
$$

where $p(w) = z$. This pushforward metric is well-defined, i.e. independent of the choice of the preimage $z$ of $w$ because deck transformations of $p$ consist of translations, which are isometries. It is clear that $(X, p_\* 1)$ must have zero curvature too.

When $X = \mathbb{C}^\*$, the pushforward flat metric is $\lvert\frac{dz}{z}\rvert$. All closed geodesics are concentric circles centered at $0$ are closed geodesics of length $2\pi$ and all open geodesics are infinite spirals or straight rays from $0$ to $\infty$. $X$ has infinite area.

When $X$ = \mathbb{c} / \Lambda$ for some lattice $\Lambda = w_1\mathbb{Z} + w_2 \mathbb{Z}$, then the pushforward flat metric is often still denoted by $\lvert dz \rvert$. $X$ has finite area $\lvert \text{Im} (w_1 \bar{w_2}) \rvert $. Any straight line in $\mathbb{C}$ induces a closed geodesic on $X$ if and only if it is parallel to a vector $a w_1 + b w_2$ for some integers $a$ and $b$. Moreover, every open geodesic in $X$ extends to a dense subset of $X$.

## Hyperbolic metric

The most fascinating conformal metrics are those on hyperbolic Riemann surfaces. We'll start with the simply connected case. Recall that every biholomorphism of the unit disk $\mathbb{D}$ is a Möbius transformation of the form $e^{i\theta} \frac{z-a}{1-\bar{a}z}$ for some $\theta \in \mathbb{R}$ and $a \in \mathbb{D}$. The unit disk admits a special conformal metric called the **Poincaré metric** $\rho_{\mathbb{D}}(z) \lvert dz \rvert$ on $\mathbb{D}$ given by

$$
\rho_{\mathbb{D}}(z) = \frac{2}{1-\lvert z \rvert^2}.
$$

$\rho_{\mathbb{D}}(z) |dz|$ is the unique (up to multiplication by a positive constant) conformal metric on $\mathbb{D}$ such that all biholomorphisms of $\mathbb{D}$ are isometries of $(\mathbb{D}, \rho_{\mathbb{D}})$. We can pull this metric back by the conformal map $\mathbb{H} \to \mathbb{D}, z \mapsto \frac{i-z}{i+z}$ to obtain the **Poincaré metric** $\rho_{\mathbb{H}}(z) \lvert dz \rvert$ on the upper half plane $\mathbb{H}$ where

$$
\rho_{\mathbb{H}}(z) = \frac{1}{\text{Im}z}.
$$

### References
<a name="fn1">1</a>: L. Ahlfors. Complex Analysis. McGraw-Hill, 1979.   

------
