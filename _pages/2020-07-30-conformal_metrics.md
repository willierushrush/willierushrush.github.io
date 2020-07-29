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

The pair $(M, g)$ is often called a **Riemannian manifold**. A simple fact in this matter is that every smooth real manifold $M$ admits a Riemannian manifold structure. Indeed, by partition of unity, we can glue together a collection of flat metrics on each local chart to form a global Riemannian metric on $M$. The metric $g$ is what gives $M$ some geometry. At every point $p$, $g$ gives us a norm on the tangent space defined by $\lvert v \rvert_g = \sqrt{g(v,v)}$ for any $v \in T_p M$. We can define the angle between two tangent vectors $v, w \in T_p M$ at a point $p$ to be the value $\theta$ such that the cosine rule holds:

$$
\cos \theta = \frac{g_p(v,w)}{\lvert v\rvert_g \lvert w \rvert_g }.
$$

We can also define the length of a smooth curve $\gamma : [a,b] \to M$ on $M$ to be

$$
L(\gamma) = \int_a^b \lvert \gamma'(t) \rvert_g dt,
$$

where $\gamma'(t)$ is the tangent vector on $T_{\gamma(t)}M$ tangent to the curve $\gamma$. The generalisation for piecewise smooth curves and even rectifiable curves is rather obvious. A standard use of change of variables formula should convince you that the length of a curve is independent of parametrisation. The distance $d(p,q)$ between two points $p,q$ on $M$ is taken to be the infimum of lengths of piecewise smooth curves in $M$ from $p$ to $q$. When $M$ is connected, the metric space topology induced by $d$ coincides with the original topology of $M$.

Every immersion $f: M \to (N,h)$ from a smooth manifold $M$ to a Riemannian manifold $N$ induces the **pullback metric** $f^\*h$ on $M$ defined by $f^\*h_p(v,w) := h_p(df_p(v), df_p(w))$ at every point $p \in M$ for any $v,w \in N$. A smooth map $f: (M, g) \to (N,h)$ between two Riemannian manifolds is a **local isometry** if it is a local diffeomorphism and the metric $g$ coincides with the pullback metric $f^\*h$; $f$ is an **isometry** if additionally it is a diffeomorphism. As the name implies, a local/global isometry preserves lengths locally/globally.

## Conformal metrics

When $M$ is a Riemann surface, we say that a Riemannian metric $g$ on $M$ is **conformal** if on each local chart, $g$ can be written as $\rho(z)^2 \lvert dz \rvert$ (alternatively, $\rho(z)^2 (dx^2 + dy^2)$ or $\rho(z)^2 dz d\bar{z}$) for some smooth positive function $\rho(z)$. The corresponding matrix $g_{ij}$ will be precisely $\rho(z)^2 I_2$ where $I_2$ is the $2 \times 2$ identity matrix. It is common to use the notation $\rho(z) |dz|$ to refer to $g$. We are still able to argue by partition of unity that every Riemann surface admits a conformal metric.

The conformal metric $\rho(z) |z|$ gives rise to a geometry on $M$. As the name suggests, on each local chart, angles with respect to $\rho(z) |dz|$ are the same as angles with respect to the flat metric $|dz|$ because they only differ by a positive factor of $\lambda^2$. The $\rho$-length of a curve $\gamma : [a,b] \to M$ is

$$
L_\rho(\gamma) = \int_\gamma \rho(z) |dz|.
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

Let's look at some examples of conformal metrics on commonly found Riemann surfaces.

## Spherical metrics

Stereographic projection $P : S^2 \to \mathbb{P}^1$ from the unit sphere $S^2 \subset \mathbb{R}^3$ to the Riemann sphere $\mathbb{P}^1 = \mathbb{C} \cup \{\infty\}$ given by

$$
P(\theta,\phi) = \begin{cases}
\cot(\frac{\theta}{2})e^{i\phi}, & \text{ if } \theta \neq 0, \\
\infty, & \text{ if } \theta = 0.
\end{cases}
$$

is a diffeomorphism. The unit sphere $S^2$ has a natural round metric

### References
<a name="fn1">1</a>: L. Ahlfors. Complex Analysis. McGraw-Hill, 1979.   

------
