---
title: 'Conformal metrics on Riemann surfaces'
date: 2020-07-30
permalink: /conformal_metrics/
tags:
  - Riemann Surfaces
---

As smooth two dimensional smooth real manifolds, Riemann surfaces admit Riemannian metrics. In the study of Riemann surfaces, it is more interesting to look at those Riemannian metrics which behave nicely under holomorphic maps between Riemann surfaces. This gives rise to conformal metrics.

## Riemannian metrics

Recall that a **Riemannian metric** $g$ on a smooth real $n$-manifold $M$ is a (0,2)-tensor field; at each point $p \in M$, we have a symmetric bilinear and positive definite map $g_p : T_p M \times T_p M \to \mathbb{R}$. On any smooth local charts, $g$ can be expressed as $g = \sum_{1\leq i,j\leq n} g_{ij} dx_i \tensor dx_j$ for some symmetric and positive definite $n \times n$ matrix of smooth functions $g_{ij}$. For example, $\mathbb{R}^n$ admits the flat metric $g = \sum_{i=1}^n dx_i \tensor dx_i$ where the matrix $g_{ij}$ is globally the identity matrix.

The pair $(M, g)$ is often called a **Riemannian manifold**. A simple fact in this matter is that every smooth real manifold $M$ admits a Riemannian manifold structure. Indeed, by partition of unity, we can glue together a collection of flat metrics on each local chart to form a global Riemannian metric on $M$. The metric $g$ is what gives $M$ some geometry. At every point $p$, $g$ gives us a norm on the tangent space defined by $\lvert v \rvert_g = \sqrt{g(v,v)}$ for any $v \in T_p M$. We can define the angle between two tangent vectors $v, w \in T_p M$ at a point $p$ to be the value $\theta$ such that the cosine rule holds:

$$
\cos \theta = \frac{g_p(v,w)}{\lvert v\rvert_g \lvert w \rvert_g }.
$$

We can also define the length of a smooth curve $\gamma : [a,b] \to M$ on $M$ to be

$$
l(\gamma) = \int_a^b \lvert \gamma'(t) \rvert_g dt,
$$

where $\gamma'(t)$ is the tangent vector on $T_{\gamma(t)}M$ tangent to the curve $\gamma$. The generalisation for piecewise smooth curves and even rectifiable curves is rather obvious. A standard use of change of variables formula should convince you that the length of a curve is independent of parametrisation. The distance between two points $p,q$ on $M$ is taken to be the infimum of lengths of piecewise smooth curves in $M$ from $p$ to $q$.

## Conformal metrics

When $M$ is a Riemann surface, we say that a Riemannian metric $g$ on $M$ is **conformal** if on each local chart, $g$ can be written as $\rho(z)^2 \lvert dz \rvert$ (alternatively, $\rho(z)^2 (dx^2 + dy^2)$ or $\rho(z)^2 dz d\bar{z}$) for some smooth positive function $\rho(z)$. The corresponding matrix $g_{ij}$ will be precisely $\rho(z)^2 I_2$ where $I_2$ is the $2 \times 2$ identity matrix. It is common to refer to a conformal metric in terms of its line element $\rho(z) |dz|$ instead.

The conformal metric $\rho(z) |z|$ gives rise to geometry on $M$. As the name suggests, on each local chart, angles with respect to $\rho^2 |dz|^2$ are the same as angles with respect to the flat metric $|dz|^2$ because they only differ by a positive factor of $\lambda^2$. The $\rho$-length of a curve $\gamma : [a,b] \to M$ is

$$
l_\rho(\gamma) = \int_\gamma \rho(z) |dz|.
$$

### References
<a name="fn1">1</a>: L. Ahlfors. Complex Analysis. McGraw-Hill, 1979.   

------
