---
title: 'Caratheodory topology and the space of Riemann mappings.'
date: 2020-06-03
permalink: /posts/2020/06/caratheodory_topology/
tags:
  - Complex analysis
  - Riemann surfaces
  - Set Theory
  - Topology
---

Let $X$ be a set. For any infinite sequence $A_n$ of subsets, define

$$
\liminf_{n\to \infty} A_n := \bigcup_{m \geq 1} \bigcap_{n \geq m} A_n, \qquad \limsup_{n\to \infty} A_n := \bigcap_{m \geq 1} \bigcup_{n \geq m} A_n.
$$

The inner limit $\liminf A_n$ is the set of points in $X$ which are in all but finitely many $A_n$'s, whereas the outer limit $\limsup A_n$ is the set of points in $X$ which are contained in infinitely many $A_n$'s. As the names suggest, the former is a subset of the latter.

In set and measure theories, it is common to say that $A_n$ has a limit $A$ when both limits coincide and are equal to $A$. When $X$ is a topological space, this notion of convergence may not respect the topological properties of these subsets. In $\mathbb{R}$, open intervals can converge to non-open subsets: $(-\frac{1}{n}, \frac{1}{n}) \to \\{0\\}$.

## Hausdorff Metric Topology

Now, assume that $(X,d)$ is a compact metric space and let's have a look at the set $C(X)$ of all non-empty closed subsets of $X$. We can in fact fix the earlier problem by endowing $C(X)$ with the topology where closed subsets $A_n$ converge to $A$ if and only if the closure of the two limits coincide with $A$:

$$
A = \overline{ \liminf_{n\to \infty} A_n } = \overline{ \limsup_{n\to \infty} A_n }.
$$

In fact, $C(X)$ is metrisable. Define $D: C(X) \times C(X) \to [0,\infty)$ by

$$
D(A,B) = \inf \\{ \epsilon \geq 0 \: | \: A \subset B_{\epsilon}, B \subset A_{\epsilon} \\},
$$

where $A_{\epsilon} := \\{ x \in X \: | \: d(x,A) \leq \epsilon \\}$ denotes the closed $\epsilon$-neighbourhood of the closed subset $A$. (I'll leave it to you to check that $D$ really is a metric on $C(X)$.) The metric $D$ is often called the \emph{Hausdorff metric} and it measures the maximum distance a point in $A$ has to travel to go to some point in $B$, and vice versa. For example, if $X = [0,1]$ is the Euclidean unit interval, $D(\{0,1\}, [0,0.4]) = 0.6$.

The set $O(X)$ of all proper open subsets of $X$ can also be topologised by saying that $U_n \to U$ if and only if

$$
U = \text{int} \left( \liminf_{n\to \infty} U_n \right) = \text{int} \left( \limsup_{n\to \infty} U_n \right).
$$

It can also be endowed with a similar metric which we shall again call the \emph{Hausdorff metric} denoted by $D$:
$$
D(U,V) = \inf \\{ \epsilon \geq 0 \: | \: U^{\epsilon} \subset V, V^{\epsilon} \subset U \\},
$$

where $U^{\epsilon} := \\{ x \in U \: | \: d(x, X \backslash U) > \epsilon \\}$ denotes the set of points in $U$ which is at least $\epsilon$ distance away from its complement. This definition coincides with our previous one by the relation $D(U,V) = D(X\backslash U, X \backslash V)$.

## Riemann mappings

Let's look at the one-point compactification $\mathbb{P}^1 = \mathbb{C} \cup \\{ \infty \\}$ of the complex plane $\mathbb{C}$. As a Riemann surface, the Riemann sphere $\mathbb{P}^1$ can be endowed with the spherical metric $d$.

Let's call $U$ a \emph{topological disk} if it is a simply connected domain (connected open subset) in $\mathbb{P}^1$ whose complement consists of at least two distinct points. The set $\mathcal{D}$ of all topological disks can be viewed as a subspace of the Hausdorff metric space $( O(\mathbb{P}^1), D)$.

The uniformisation theorem asserts that every topological disk $U$ admits a conformal isomorphism $f: \mathbb{D} \to U$. By studying the conformal automorphisms of $\mathbb{D}$, we can also say that for every basepoint $u \in U$ there is a unique $f$ such that $f(0)=u$ and $f'(0) \in \mathbb{R}_+$. We shall call such function the \emph{Riemann mapping} of the pointed topological disk $(U,u)$. Riemann mappings provide a bijective correspondence $\Phi: (U,u) \mapsto f$ between the set $\mathcal{E}$ of all pointed topological disks and the set $\mathcal{F}$ of all conformal injections from $\mathbb{D}$ to $\mathbb{P}^1$ with positive derivative at $0$.

We can view $\mathcal{E}$ as both a subspace of the product $\mathcal{D} \times \mathbb{P}^1$ and a fiber bundle of $\mathcal{D}$ over $\mathbb{D}$. In particular, $\mathcal{E}$ can be endowed with the metric $d_\mathcal{E}$ where $d_\mathcal{E}( (U,u), (V,v)) = \max \\{ D(U,V), d(u,v) \\}$. This topology is often called the \emph{Carathéodory topology}. Meanwhile, the set $\mathcal{F}$ can be endowed with the compact-open topology, that is, $f_n \to f$ if and only if $f_n$ converges to $f$ uniformly on every compact subset of $\mathbb{D}$.

> **_Theorem:_** The map $\Phi: \mathcal{E} \to \mathcal{F}$ is a homeomorphism.

To prove the theorem, it is sufficient to prove that the map $\Psi : \mathcal{D}_0 \to \mathcal{G}$ where $\mathcal{D}_0 \subset \mathcal{D}$ is the space of all topological disks containing $0$, $\mathcal{G} \subset \mathcal{F}$ is the space of all conformal injections fixing $0$ and $\Psi(U) = \Phi((U,0))$. Indeed, suppose $(U_n, u_n)$, $n \geq 1$, and $(U,u)$ are pointed disks with Riemann mappings $f_n$ and $f$. If $u \neq \infty$, then we may assume all $u_n$'s are finite too. Then, we can post-compose $f_n$ with the translation $z \mapsto z - u_n$ and $f$ with $z \mapsto z-u$. By applying triangle inequality and the fact that $\Psi$ is a homeomorphism, we can show the following:
$$
(U_n ,u_n) \to (U, u) \Longleftrightarrow (U_n -u_n, 0) \to (U - u, 0) \Longleftrightarrow f_n - u_n \to f - u \Longleftrightarrow f_n \to f.
$$
When $u = \infty$, then we may assume that all $u_n$'s are non-zero and additionally post-compose $f_n$'s and $f$ with the inversion map $z \mapsto \frac{1}{z}$ in order to make the basepoints finite.

### References
<a name="fn1">1</a>: E. Calabi and M. Rosenlicht. Complex Analytic Manifolds Without Countable Base. Proceedings of the American Mathematical Society, 4(3): 335-340, 1953.  
<a name="fn2">2</a>: O. Forster. Lectures on Riemann surfaces. Graduate Texts in Mathematics, Vol 81. Springer-Verlag, NY-Berlin, 1981.  
<a name="fn3">3</a>: J. H. Hubbard. Teichmüller Theory and Applications to Geometry, Topology, and Dynamics. Vol. 1. Matrix Editions, Ithaca, NY, 2006.  
<a name="fn4">4</a>: T. Radó. Über den Begriff der Riemannschen Fläche. Acta Szeged, 2(2): 101–121, 1925.  

------
