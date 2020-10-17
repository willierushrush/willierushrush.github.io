---
title: 'Riemann Mapping Theorem Fails in Higher Dimensions'
date: 2020-09-26
permalink: /posts/2020/10/riemann-mapping-theorem-fails
tags:
  - Several Complex Variables
  - Complex Geometry
---

Riemann mapping theorem states that every simply connected domain on the complex plane $\mathbb{C}$ is either $\mathbb{C}$ or biholomorphic to the unit disk $\mathbb{D}$. This theorem is like a miracle and its natural generalisation to domains in higher dimensions miserably fails. I'd like to bring up a classical counterexample by Poincaré, showing that the unit ball $\mathbb{B} \subset \mathbb{C}^n$ is not biholomorphic to the unit polydisk $\mathbb{D}^n$ \subset \mathbb{C}^n$ for $n \geq 2$.

> **_Theorem:_** Th The unit polydisk $\mathbb{D}^n$ \subset \mathbb{C}^n$ is not biholomorphic to the unit ball $\mathbb{B} \subset \mathbb{C}^n$ for $n \geq 2$.

For any domain $M \subset \mathbb{C}^n$, or any complex manifold in general, denote by $\text{Aut}(M)$ the group of automorphisms (self biholomorphisms) of $M$. When two complex manifolds $M$ and $N$ are biholomorphic, it means that there is a biholomorphism $\phi: M \to N$, i.e. a holomorphic bijection with holomorphic inverse. Any such biholomorphism $\phi$ induces a group isomorphism
$\text{Aut}(M) \to \text{Aut}(N), f \mapsto \phi \circ f \circ \phi^{-1}$. Poincaré showed that the automorphism groups of $\mathbb{B}$ $\mathbb{D}^n$ are not isomorphic to each other.

## Cartan's theorem

I will not directly follow Poincaré's idea, but rather adopt a more general approach following H. Cartan. We say a domain $M \subset \mathbb{C}^n$ is a *complete Reinhardt* domain if whenever $w = (w_1,\ldots w_n) \in M$, then $M$ contains the polydisk $\\{ \vert z_1 \vert  \leq  \vert w_1 \vert , \ldots  \vert z_n \vert \leq  \vert w_n \vert \\}$. When $M$ is complete Reinhardt, every holomorphic map $f:M \to \mathbb{C}$ can be expressed uniquely as a Taylor series about the origin convergent on the whole domain $M$.

> **_Theorem:_** Every biholomorphism $f = (f_1,\ldots f_n): M \to N$ between two bounded complete Reinhardt domains $M$ and $N$ in $\mathbb{C}^n$ is a linear map if $f(0)=0$.

Indeed, let $f: M to N$ be such a biholomorphism fixing $0$ and let $L =  define $f_\theta := e^{-i\theta} f(e^{i\theta} z)$. Let $f(z) = Lz + z^{T} Q z + \ldots$ be the series development of $f$ on $M$ about the origin. Here, $L$ is the complex Jacobian matrix of $f$ at $0$. The corresponding series for $f_\theta$ is $f_\theta(z) = Lz + e^{i\theta}z^T Q z + \ldots$; observe that every term aside from the linear one contains a non-zero multiple of $e^{i\theta}$. By taking the arithmetic mean over $\theta$, we obtain:

$$
Lz = \frac{1}{2\pi} \int_0^{2\pi} f_\theta (z) d\theta.
$$

As $N$ is complete Reinhardt, the linear map $L$ maps $M$ into $N$. We can apply the same argument to the inverse $f^{-1}$ and conclude that its Jacobian $L^{-1}$ maps $N$ to $M$. Therefore, $L$ is a biholomorphism from $M$ to $N$.

## Why Riemann mapping theorem fails

We can first apply the theorem above to our favorite complete Reinhardt domains $\mathbb{B}$ and $\mathbb{D}^n$. Assume that a biholomorphism $f: \mathbb{B} \to \mathbb{D}^n$ exists. Let $a = (a_1,\ldots a_n) = f(0)$, then the map $g_a \in \Aut(\mathbb{D}^n)$ given

$$
g_a(w) = \left( \frac{z_1 - a_1}{1-\bar{a_1}z_1}, \ldots , \frac{z_n - a_n}{1-\bar{a_n}z_n} \right)
$$

will map $a$ to $0$. Since the composition $g_a \circ f : \mathbb{B} \to \mathbb{D}^n$ is a biholomorphism fixing the origin, it must be a linear map. We immediately get a contradiction because the boundary of $\mathbb{B}$, i.e. the standard $2n-1$ unit sphere, is not linearly equivalent to the boundary of the polydisk $\mathbb{D}^n$. In fact, the boundary of the polydisk $\mathbb{D}^n$ is not even a smooth manifold!

Clearly, this argument can be generalised to show that the unit polydisk is not biholomorphic to many other complete Reinhardt domains as long as the boundaries are not linearly equivalent. There is another way of seeing how the Riemann mapping theorem fails in higher dimensions. There are in fact domains $D \subset \mathbb{D}^n$ which are biholomorphic to $\mathbb{C}^n$ even though not the whole $\mathbb{C}^n$. These are called Fatou-Bieberbach domains and are typically constructed from the attracting basin of a fixed point of a special type of polynomial automorphisms (Hénon maps). I will probably discuss this in detail in another post...

### References

<a name="fn1">1</a>: L. Bers, Introduction to several complex variables, New York Univ. Press, New York, 1964.  
Huybrects  
Korevaar Wiegernick?  
