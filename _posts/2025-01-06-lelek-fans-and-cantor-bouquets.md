---
title: 'Lelek fans and Cantor bouquets'
date: 2025-01-06
permalink: /posts/2025/01/lelek-fans-and-cantor-bouquets
tags:
  - Topology
  - Holomorphic dynamics
---

Recently, I've been a little obsessed with Cantor bouquets. These are rather strange objects with somewhat pathological topological properties, yet they occur rather naturally from dynamical systems, in particular from transcendental dynamics. Cantor bouquets are examples of a Lelek fan, which is essentially a bouquet of uncountably many arcs whose endpoints are dense in the space itself. The center of the bouquet is an explosion point, meaning that even though the set of endpoints is totally disconnected, the union with the center is connected. In the examples coming from dynamics, the endpoints also has rather peculiar measure-theoretic properties.

## What is... a Lelek fan?

Here's a precise definition. A Lelek fan $L$ is a compact connected metric space with the following properties:
1. hereditarily unicoherent: for any two intersecting compact connected subspaces $A$ and $B$ of $L$, $A \cap B$ is connected;   
2. arcwise connected: for any two distinct points $x$ and $y$ in $L$, there is a unique simple arc $[x,y] \subset L$ joining $x$ and $y$;   
3. branch point: there is a unique point $b$ in $L$ that is a common endpoint of at least three disjoint open arcs in $L$;   
4. topologically smooth: given any sequence of points $x_n$ in $L$ converging to $b$, the arcs $[x_n,b]$ converge to $[x,b]$ in the Hausdorff metric;    
5. density of endpoints: the set $E(L)$ of endpoints (i.e. points which are an endpoint of every arc containing it) is dense in $L$.
Properties 1,2, and 3 basically say that $L$ is a bouquet of arcs, the center of the bouquet being $b$ itself. Properties 4 and 5 make $L$ even more interesting.

In the 80's, it was proven independently by Bula-Oversteegen<sup>[2](#fn2)</sup> and Charatonik<sup>[3](#fn3)</sup> that any two Lelek fans are homeomorphic. However, the first example of a Lelek fan was discovered much earlier in the 60's by Lelek<sup>[4](#fn4)</sup>. Lelek also observed that the endpoints $E(L)$ have the following bizarre property.

> **_Theorem:_** Given a Lelek fan $L$, the branch point $b$ is an **explosion** point of the set $\{b\} \cup E(L)$, that is, $\{b\} \cup E(L)$ is connected but $E(L)$ is totally separated (for every two distinct endpoints $x$ and $y$, there is a clopen subset of $E(L)$ containing $x$ but not $y$).

## What is... a Cantor bouquet?

A **straight brush** is a closed subset $B$ of $\mathbb{C}$ that is contained in $\{x+iy \in \mathbb{C} \: : \: x\geq 0, y \not\in \mathbb{Q} \}$ and satisfies the following properties:
1. $B$ is an uncountable union of hairs of the form $\text{hair}_y := \{x+ iy \: : \: x \geq t_y \}$ where $y$ is an irrational number and $t_y \geq 0$;   
2. The image of $B$ under the projection $\pi : x+iy \mapsto y$ is dense in $\mathbb{R}\backslash \mathbb{Q}$;   
3. For any $y \in \pi(B)$, there exist an increasing sequence $(p_n)\_{n}$ in $\pi(B)$ and a decreasing sequence $(q_n)\_{n}$ in $\pi(B)$ such that $\lim_{n\to \infty} p_n = \lim_{n\to \infty} q_n = y$ and $\lim_{n\to \infty} t_{p_n} = \lim_{n\to \infty} t_{q_n} = t_y$.   

A **Cantor bouquet** is the image of a straight brush $B$ under a homeomorphism $\phi: \C \to \C$. Clearly, if $C$ is a Cantor bouquet, then $C \cup \{\infty\}$ is a Lelek fan with vertex $\infty$ embedded in the Riemann sphere $\hat{\mathbb{C}} = \C \cup \{\infty\}$. The key additional property that distinguishes Cantor bouquets from arbitrary Lelek fans is property 3, which states that hairs can be approximated by other hairs from the left and right.

The name Cantor bouquet seems to stem from the fact that the first known example of what should be a Cantor bouquet is the closure of an increasing union of sets homeomorphic to a Cantor set times $\mathbb{R}_{\geq 0}$. Aarts and Oversteegen<sup>[1](#fn1)</sup> then formally came up with the definition of a straight brush. They also proved a stronger uniqueness result: given two Cantor bouquets $C$ and $C'$, there is a homeomorphism $\phi: \mathbb{C} \to \mathbb{C}$ sending $C$ to $C'$.

## Transcendental dynamics

There has been quite a number of studies on how Cantor bouquets arises naturally from dynamics and number theory. However, the classical example comes from iterations of transcendental entire functions, i.e. holomorphic maps $f: \mathbb{C} \to \mathbb{C}$ that are not polynomials. So you should think of an exponential map or a sine map.

The simplest example is $f_\lambda(z) = \lambda e^z$ for $\lambda \in (0, e^{-1})$. It has the following nice features:
- There is a unique point $w=w(\lambda) \in (0,1)$ such that $f_\lambda(w) = w$. (This follows e.g. from Mean Value Theorem.) Moreover, $w$ is an attracting fixed point because $|f_\lambda'(w)| = w <1$.   
- The map $f_\lambda$ sends the left half plane $H = \{ \text{Re}(z)< \log \lambda^{-1} \}$ to the unit disk $\mathbb{D} = \{|z|<1\}$, which is contained in $H$. By Schwarz Lemma, for every point $z$ in $H$, the forward iterates $f^n_{\lambda}(z)$ converge to $w$ as $n \to \infty$.
- The full preimage $f_{\lambda}^{-1}(H)$ of $H$ is a disjoint union of unbounded simply connected domains $D_n$, $n \in \mathbb{Z}$, where $D_n = \{x+iy \: : \: |y - 2 \pi n|< \frac{\pi}{2}, x > \log(\lambda^{-1} \sec(y) \log \lambda^{-1}) \}$. So each $D_n$ is obtained by translating $D_0$ by $2 \pi i n$.
Can you guess what happens to $f_{\lambda}^{-k}(H)$ as $k \to \infty$? See the gif below. The limiting set is what we call the Julia set of $f_{\lambda}$:
$$
J(f_\lambda) = \bigcap_{k \geq 1} f_{\lambda}^{-k}(H).
$$
The Julia set of $f_\lambda$ is essentially the boundary of the attracting basin of the fixed point $w$. It also coincides with the closure of the set of repelling periodic points of $f_\lambda$. (See this [post](/posts/2020/06/fatou_and_julia/).) Roughly speaking, $J(f_\lambda)$ is the set of chaotic points of $f_\lambda$ in the sense that nearby points will always have strikingly different forward orbits.

<p align="center">
  <img src="/images/cantorbouquet.gif" width="560" height="420" />
</p>

The following theorem is also due to Aarts and Oversteegen<sup>[1](#fn1)</sup>.

> **_Theorem:_** For $\lambda \in (0,e^{-1})$, $J(f_\lambda)$ is a Cantor bouquet.

Given any point $z$ in $J(f_\lambda)$, we can keep track the location of the forward orbit of $z$ by looking at the itinerary of $z$, which is an infinite sequence of integers $i(z) = (i_0,i_1,i_2,i_3,\ldots)$ such that $f_\lambda^n(z)$ is contained in $D_{i_n}$ for all $n \geq 0$. Points of the same itinerary are located in the same hair of $J(f_\lambda)$, and conversely points of different itinerary are located in different hairs.

Actually, there's nothing really special about $f_\lambda$. In general, the theorem holds for transcendental entire functions that satisfy the following conditions:
- finite order: $\log \log |f(z)| = O(|\log z|)$ as $|z| \to \infty$ (for example, this holds when $f$ is a finite composition of polynomials and $e^z$);   
- disjoint type: there is a bounded open disk $D$ with $\overline{f(D)} \subset D$ such that the smallest closed set $S$ such that $f: \mathbb{C}\backslash f^{-1}(S) \to \mathbb{C} \backslash S$ is a covering map is contained in $D$.   
See this excellent survey by Sixsmith<sup>[7](#fn7)</sup>.

This particular example of Cantor bouquets is also bizarre in the measure-theoretic viewpoint. Here's a theorem by Karpi\'nska<sup>[5](#fn5),[6](#fn6)</sup>.

> **_Karpi\'nska's Paradox:_** For $\lambda \in (0,e^{-1})$, the endpoints in $J(f_\lambda)$ has Hausdorff dimension two, but $J(f_\lambda)$ minus its endpoints has Hausdorff dimension one.


### References

<a name="fn1">1</a>: J. M. Aarts and L. G. Oversteegen, The geometry of Julia sets. Transactions of the American Mathematical Society, Vol. 338, No. 2, 897–918, 1993.   
<a name="fn2">2</a>: W. D. Bula and L. G. Oversteegen, A characterization of smooth Cantor bouquets. Proceedings of the American Mathematical Society, Vol. 108, No. 2, 529–534, 1990.
<a name="fn3">3</a>: W. J. Charatonik, The Lelek fan is unique. Houston Journal of Mathematics, Vol. 1, 27-34, 1989.   
<a name="fn4">4</a>: A. Lelek, On plane dendroids and their end points in the classical sense. Fundamenta Mathematicae, Vol. 49, 301-319, 1961.   
<a name="fn5">5</a>: B. Karpi\'nska, Area and Hausdorff dimension of the set of accessible points of the Julia sets of $\lambda e^z$ and $\lambda \sin z$. Fundamenta Mathematicae, Vol. 159, no. 3, 269–287, 1999.   
<a name="fn6">6</a>: B. Karpi\'nska, Hausdorff dimension of the hairs without the endpoints for $\lambda \text{exp} z$. Comptes rendus de l'Académie des Sciences Paris, S\'er. I Math., Vol. 328, no. 11, 1039–1044, 1999.   
<a name="fn7">7</a>: D. J. Sixsmith, Dynamics in the Eremenko-Lyubich class. Available on arXiv:1709.09095.   

------
