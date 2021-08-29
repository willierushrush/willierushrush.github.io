---
title: 'Harmonic Measure and the 2-D Dirichlet Problem'
date: 2021-08-27
permalink: /posts/2021/08/dirichlet-problem/
tags:
  - Complex analysis
---

The Dirichlet problem is one of the classical problems in the field of PDEs and it is the problem of finding a harmonic function on a domain that takes prescribed values on the boundary. The Dirichlet problem is closely related to the notion of harmonic measure of a domain, which is a probability measure on the boundary of the domain. We will first discuss harmonic measure for nice planar domains and its relevance in solving the Dirichlet problem in 2 dimensions.

## Harmonic Measure

Recall that a function $u : U \to \mathbb{R}$ is **harmonic** on a domain $U \subset \mathbb{C}$ if it is twice differentiable and $\Delta u = u_{xx} + u_{yy} = 0$ on $U$. Equivalently, $u$ is harmonic if it is locally integrable and it satisfies the mean value property, i.e. for every closed disk $\overline{\mathbb{D}(a,r)} \subset U$ centered at $a \in U$ of some radius $r>0$,
$$
u(a) = \frac{1}{2\pi} \int_0^{2\pi} u(a+re^{2\pi i t}) dt.
$$

The **harmonic measure** $\omega_U(z,E)$ of a subset $E \subset \partial U$ at a point $z \in U$ on a domain $U$ is defined to be the probability that Brownian motion starting from $z$ would first hit the boundary $\partial U$ at a point on $E$. We are often only interested in $E$ being Borel for obvious reasons.

The simplest example of harmonic measure arises when $U$ is the unit disk $\mathbb{D}$ and the basepoint is picked at $z=0$. By symmetry, the harmonic measure $\omega_{\mathbb{D}}(0,E)$ coincides with the uniform probability measure on the circle, which is
$$
\omega_{\mathbb{D}}(0,E) = \frac{1}{2\pi} \int_E |dz|.
$$
Brownian motion is conformal, so then armonic measure should be invariant under conformal transformations. For any point $z_0 \in \mathbb{D}$, the map $\phi(z) = \frac{z-z_0}{1-\bar{z_0} z}$ is the unique conformal automorphism of $\mathbb{D}$ such that $\phi(z_0) =0$ and $\phi'(0) >0. By conformal invariance, the harmonic measure of $E \subset \partial \mathbb{D}$ at $z_0$ is
$$
\omega_{\mathbb{D}}(z_0,E) = \omega_{\mathbb{D}}(0, \phi(E)) = \frac{1}{2\pi} \int_E |\phi'(z)| |dz| = \int_E P_{z_0}(z) |dz|.
$$
where $P_{z_0}(z) = \frac{1- |z_0|^2}{2\pi|z_0-z|^2}$ is called the **Poisson kernel** at $z_0$ for $\mathbb{D}$. In fact, it is not difficult to check that the Poisson kernel is harmonic in $z_0$.

From the explicit integral formula above, we can list a few important properties of harmonic measure below. The third property can also be viewed in the point of view of probability.
1. $\omega_{\mathbb{D}} (z_0, \cdot)$ is an absolutely continuous measure with respect to the Euclidean measure on the unit circle.
2. For any Borel set $E \subset \partial \mathbb{D}$, $\mathbb{D} \to [0,1], z_0 \mapsto \omega_{\mathbb{D}}(z_0,E)$ is a harmonic function.
3. As $z_0$ converges to a point on the interior of $E$, $\omega_{\mathbb{D}}(z_0,E) \to 1$. As $z_0$ converges to a point on $\partial\mathbb{D} \backslash \bar{E}$, $\omega_{\mathbb{D}}(z_0,E) \to 0$.

On an arbitrary Jordan domain $U$ and a basepoint $z_0 \in U$, pick any Riemann mapping $g : U \to \mathbb{D}$; we know that $g$ always extends continuously to a homeomorphism $\partial \mathbb{D} \to \partial U$ by Carathéodory's extension theorem. (Details can be found [here](/posts/2020/08/continuous-extension-of-riemann-mappings-and-local-connectivity/).) The harmonic measure of a Borel subset $E \subset \partial U$ at $z_0$ on $U$ is
$$
\omega_{U} (z_0, E) = \omega_{\mathbb{D}} (g(z_0), g(E)) = \int_{g(E)} P_{g(z_0)}(z) |dz|.
$$
By conformal invariance, the three properties above also hold for $\omega_{U} (z_0, E)$.

Harmonic measure on an arbitrary domain $U$ can be rather complicated. If the boundary $\partial U$ consists of a finite number of analytic Jordan curves, we can obtain a formula for the harmonic measure of $U$ using Green's function, a generalisation of the Poisson kernel. In general, we can approximate the harmonic measure on an arbitrary domain $U$ by harmonic measures on approximating nice domains $U_n$ whose boundaries are a finite number of piecewise analytic Jordan curves. Of course, this requires us to deal with some notion of convergence of measure and of domains in $\mathbb{C}$. More details can be found in the book of Garnett and Marshall<sup>[1](#fn1)</sup>.

## The Dirichlet Problem

The classical two-dimensional Dirichlet problem is often formulated as follows. Given a continuous function $f: \partial U \to \mathbb{R}$ along the boundary of a domain $U \subset \mathbb{C}$, is there a unique continuous function $u : \bar{U} \to \mathbb{R}$ that is harmonic on $U$ and coincides with $f$ on the boundary $\partial U$?

For $U = \mathbb{D}$, it is well known that the solution is the Poisson integral of $f$, namely
$$
u(z_0) = \int_{\partial\mathbb{D}} P_{z_0}(z) f(z) |dz|.
$$
If $f = \chi_E$ is the characteristic function of a Borel subset $E\subset \partial \mathbb{D}$, the Poisson integral above coincides with the harmonic measure at $z_0$ of $E$, which is harmonic in $z_0$, and extends to $\chi_E$ almost everywhere on the boundary.

Since $f$ can be approximated by simple functions, for any positive integer $n$ there is a simple function $f_n(z) = \sum_{j=1}^m c_j \chi_{I_j} (z)$ on $\partial \mathbb{D}$ for some positive integer $m$, constants $c_j$ and disjoint open arcs $I_j \subset \partial \mathbb{D}$, such that $\| f_n - f \|_\infty < \frac{1}{n}$. Each $f_n$ induces a harmonic function $u_n(z_0) = \sum_{j=1}^m c_j \omega_{\mathbb{D}}(z_0, I_j)$ which coincides with $f_n$ everywhere except at the endpoints of $I_j$'s.

What happens at the endpoints? Let's assume without loss of generality that the union of closure of $I_j$'s is the whole circle. An endpoint $w$ is sandwiched between some pair of arcs $I_j$ and $I_k$. Any limit of $u_n(z_0)$ as $z_0\to w$ should lie in between $c_j$ and $c_k$ by a modified version of the maximum principle (called the Lindelöf principle). Since $\vert f(w) -c_j \vert < \frac{1}{n}$ and $\vert f(w) - c_k \vert < \frac{1}{n}$,
$$
\limsup_{z_0 \to w} \vert u_n(z) - f(w) \vert \leq \frac{1}{n}.
$$

As $n \to \infty$, the functions $u_n$ converge to a unique limit $u$, a harmonic function. By the argument above, $u$ continuously extends to the boundary and $u=f$ on $\partial \mathbb{D}$. The solution $u$ coincides with the Poisson integral on $\mathbb{D}$. Uniqueness of $u$ is rather elementary. If there are two solutions $u_1$ and $u_2$, then $u_1 - u_2$ is harmonic on $U$ and vanishes along the boundary. By the maximum principle, $u_1 - u_2 = 0$.

I'd like to make a few remarks here.
* We can relax the continuity assumption of the boundary function $f$ to simply the $L^1$ class. The solution $u$ given by the Poisson integral of $f$ is still well-defined and harmonic on $\mathbb{D}$, but it only agrees with $f$ at points of continuity of $f$. This may not mean much because it is possible that an $L^1$ function $f$ is discontinuous everywhere. A better notion of limit that comes into play here is the "non-tangential limit" or "radial limit" of $u$, which would agree with $f$ almost everywhere. This is often known as Fatou's theorem.
* The Dirichlet problem can also be solved similarly for Jordan domains since we have an explicit integral formula for the harmonic measure on Jordan domains.
* The Dirichlet problem may not have a solution for some domains. For example, if $U = \mathbb{D} \backslash {0}$, the boundary data $f(z) = 0$ for all $\vert z \vert =0$ and $f(0) = 1$, then any solution $u$ would contradict the mean value property.
* Some of the well-known methods to solve the Dirichlet problem for an arbitrary planar domain $U$ include the Perron method and the Wiener method. The former relies heavily on the theory of subharmonic functions, whereas the latter approach is by approximating $U$ by more regular domains, e.g. those whose boundary consist of finitely many piecewise analytic boundary curves.
* Most of our discussion above extends to higher dimensions. If $\omega_U (x, \cdot)$ is the harmonic measure of a bounded domain $U \subset \mathbb{R}^n$ at $x \in U$, we would expect the solution of the Dirichlet problem to be of the form
$$
u(x) = \int_{\partial U} f(y) d\omega_U(x,y).
$$

### References
<a name="fn1">1</a>: J. Garnett, D. Marshall. Harmonic Measure. Cambridge University Press, 2005.
<a name="fn2">2</a>: W. Rudin. Real and Complex Analysis. McGraw-Hill, Series in Higher Mathematics, 3rd edition, 1987.

------
