---
title: 'The Unit Ball is Not Biholomorphic to the Unit Polydisk'
date: 2020-10-17
permalink: /posts/2020/10/the-unit-ball-is-not-biholomorphic
tags:
  - Several Complex Variables
  - Complex Geometry
---

Riemann mapping theorem states that every simply connected domain on the complex plane $\mathbb{C}$ is either $\mathbb{C}$ or biholomorphic to the unit disk $\mathbb{D}$. This theorem is like a miracle and its natural generalisation to domains in higher dimensions miserably fails. In higher dimensions, simply connected domains have a much wider variety of biholomorphic invariants, such as higher cohomology groups, automorphism groups, as well as the property of being a domain of holomorphy. Without using any complicated invariants, I'd like to bring up a classical counterexample by Poincaré, showing that the unit ball $\mathbb{B} \subset \mathbb{C}^n$ and the unit polydisk $\mathbb{D}^n = \\{ \vert z_j \vert <1 \text{ for }j=1,\ldots n \\} \subset \mathbb{C}^n$ for $n \geq 2$ are not biholomorphically equivalent.

> **_Theorem:_** The unit ball $\mathbb{B} \subset \mathbb{C}^n$ is not biholomorphic to the unit polydisk $\mathbb{D}^n \subset \mathbb{C}^n$ for $n \geq 2$.

For any domain $M \subset \mathbb{C}^n$, or any complex manifold in general, denote by $\text{Aut}(M)$ the group of automorphisms (self biholomorphisms) of $M$. When two complex manifolds $M$ and $N$ are biholomorphic, it means that there is a biholomorphism $\phi: M \to N$, i.e. a holomorphic bijection with holomorphic inverse. Any such biholomorphism $\phi$ induces a group isomorphism
$\text{Aut}(M) \to \text{Aut}(N), f \mapsto \phi \circ f \circ \phi^{-1}$. Poincaré showed that the automorphism groups of $\mathbb{B}$ $\mathbb{D}^n$ are not isomorphic to each other. The book by Shabat<sup>[2](#fn2)</sup> explains that $\text{Aut}(\mathbb{B})$ is a Lie group of real dimension $\frac{n^2-n}{2}$ whereas $\text{Aut}(\mathbb{D}^n)$ has dimension $3n$.

## Cartan's theorem

I will not directly follow Poincaré's idea, but rather adopt a more general approach following H. Cartan. We say a domain $M \subset \mathbb{C}^n$ is a *complete Reinhardt* domain if whenever $w = (w_1,\ldots w_n) \in M$, then $M$ contains the polydisk $\\{ \vert z_1 \vert  \leq  \vert w_1 \vert , \ldots  \vert z_n \vert \leq  \vert w_n \vert \\}$. When $M$ is complete Reinhardt, every holomorphic map $f:M \to \mathbb{C}$ can be expressed uniquely as a Taylor series about the origin convergent on the whole domain $M$.

> **_Theorem:_** Every biholomorphism $f = (f_1,\ldots f_n): M \to N$ between two bounded complete Reinhardt domains $M$ and $N$ in $\mathbb{C}^n$ is a linear map if $f(0)=0$.

Indeed, let $f: M to N$ be such a biholomorphism fixing $0$. Define $f_\theta := e^{-i\theta} f(e^{i\theta} z)$. Let $f(z) = Lz + z^{T} Q z + \ldots$ be the series development of $f$ on $M$ about the origin. Here, $L$ is the complex Jacobian matrix of $f$ at $0$. The corresponding series for $f_\theta$ is $f_\theta(z) = Lz + e^{i\theta}z^T Q z + \ldots$; observe that every term aside from the linear one contains a non-zero multiple of $e^{i\theta}$. By taking the arithmetic mean over $\theta$, we obtain:

$$
Lz = \frac{1}{2\pi} \int_0^{2\pi} f_\theta (z) d\theta.
$$

As $N$ is complete Reinhardt, the linear map $L$ maps $M$ into $N$. We can apply the same argument to the inverse $f^{-1}$ and conclude that its Jacobian $L^{-1}$ maps $N$ to $M$. Therefore, $L$ is a biholomorphism from $M$ to $N$.

## Why Riemann mapping theorem fails

We can first apply the theorem above to our favorite complete Reinhardt domains $\mathbb{B}$ and $\mathbb{D}^n$. Assume that a biholomorphism $f: \mathbb{B} \to \mathbb{D}^n$ exists. Let $a = (a_1,\ldots a_n) = f(0)$, then the map $g_a \in \text{Aut}(\mathbb{D}^n)$ given

$$
g_a(w) = \left( \frac{z_1 - a_1}{1-\bar{a_1}z_1}, \ldots , \frac{z_n - a_n}{1-\bar{a_n}z_n} \right)
$$

will map $a$ to $0$. Since the composition $g_a \circ f : \mathbb{B} \to \mathbb{D}^n$ is a biholomorphism fixing the origin, it must be a linear map. We immediately get a contradiction because the boundary of $\mathbb{B}$, i.e. the standard $2n-1$ unit sphere, is not linearly equivalent to the boundary of the polydisk $\mathbb{D}^n$. In fact, the boundary of the polydisk $\mathbb{D}^n$ is not even a smooth manifold! Clearly, this argument can also be generalised to show that the unit polydisk is not biholomorphic to many other complete Reinhardt domains as long as the boundaries are not linearly equivalent.

### References

<a name="fn1">1</a>: D. Huybrechts. Complex Geometry. Springer-Verlag Berlin Heidelberg, 2005.   
<a name="fn1">2</a>: B. V. Shabat. Introduction to Complex Analysis. Part II: Functions of Several Variables, Translated from the third (1985) Russian edition by J S Joel. Translations of Mathematical Monographs, 110. American Mathematical Society, Providence, RI, 1992.
