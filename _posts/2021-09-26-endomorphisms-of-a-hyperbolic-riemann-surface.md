---
title: 'Classifying endomorphisms of a hyperbolic Riemann surface'
date: 2021-09-26
permalink: /posts/2021/09/endomorphisms-of-a-hyperbolic-riemann-surface
tags:
  - Holomorphic dynamics
  - Riemann surfaces
---

We saw in the previous post that the group of automorphisms of a compact Riemann surface $X$ is always finite and can be bounded in terms of its genus. Throwing away the bijective assumption, it turns out that in most situations the group of endomorphisms is still very rigid. We shall classify all holomorphic endomorphisms of hyperbolic Riemann surfaces, which are not necessarily compact, according to their dynamics.

When $X$ is an arbitrary Riemann surface, it is in general quite difficult to know and classify all endomorphism of $X$. In the case when $X$ is the complex plane $\mathbb{C}$, the vector space of entire functions has a basis of monomials $\\\{z^n\\\}_{n\geq 0}$ and, in particular, has infinite dimension. In the case when $X$ is isomorphic to the punctured plane, the situation is not any better either. However, when $X$ is hyperbolic, it turns out that we can classify all endomorphisms by their dynamical behavior.

**_Theorem:_** Let $f: X\to X$ be a non-constant holomorphic map on a hyperbolic Riemann surface $X$. Exactly one of the following holds:
1. Every compact subset $K \subset X$ admits some positive integer $N$ such that $f^n(K) \cap K = \emptyset$ for all $n\geq N$;
2. Every orbit $\\\{ f^n(x) \\\}_{n\geq 0}$ of any point $x$ converges towards a unique attracting fixed point $x_0$;
3. The map $f$ is of finite order, that is $f^n \equiv Id$ for some integer $n$;
4. $X$ is biholomorphic to the unit disk $\mathbb{D}$ or some annuli $\\\{ r < \vert z \vert < R \\\}$, where $0\leq r < R$, and $f$ is an irrational rotation.

What makes a hyperbolic Riemann surface special is that we are blessed with the presence of hyperbolic metric and the Schwarz-Pick theorem (see [here](/posts/2020/07/conformal_metrics/)), which tells us that with respect to the hyperbolic metric, $f$ is either a local isometry and a covering map, or a uniform contraction on compact subsets. In overall, if $d$ corresponds to the hyperbolic distance, then $d(f(x),f(y)) \leq d(x,y)$ for any pair of points $x$ and $y$ in $X$.

The first case corresponds to the possibility that all points diverge away to infinity. Indeed, suppose there is a point $x \in X$ such that it diverges away to infinity. More precisely, $\lim_{n\to \infty} d(f^n(x), C) = \infty$ for any compact set $C \subset X$. For any compact set $K \subset X$, let $\hat{K}$ be an even larger compact set containing $K$ and $x$. Then,

$$
\lim_{n\to \infty} d(f^n(K), C) \geq \lim_{n\to \infty} d(f^n(x), C) - \text{diam}(K) = \infty,
$$

which leads us to 1. As such, we can now assume that there is some non-empty compact set $K$ such that the orbit $f^n(x)$ of some $x$ returns to $K$ infinitely often at times $n_1, n_2, \ldots$. In this case, we say that $f$ is recurrent.

Suppose $f$ is a contraction. Let $\epsilon = d(x,f(x))$ and let $\hat{K}$ be the closed $\epsilon$-neighbourhood of $K$. By compactness, there is some factor $c<1$ such that $d(f(y),f(z)) \leq c d(y,z)$ for all $y,z \in \hat{K}$. Therefore, $d(f^{n_k+1}(x),f^{n_k}x)) \leq c^k d(f(x),x) \to 0$ and the orbit accumulates at some point $x_0$. Since $f$ is a contraction, $x_0$ is the unique fixed point and $f^n(x) \to x_0$ for all $x \in X$. This leads us to case 2.

Suppose $f$ is a covering map. We'll proceed by looking at $X$ as the quotient $\mathbb{D}/ \Gamma$ of the unit disk $\mathbb{D}$ by some subgroup $\Gamma$ of $\text{Aut}(\mathbb{D})$ acting freely and discretely. The group $\Gamma$ can also be identified with the fundamental group of $X$.

- Suppose $\Gamma$ is abelian. This corresponds to the case where $X$ is isomorphic to either the unit disk $\mathbb{D}$ or $\\\{ r < \vert z \vert < R \\\}$, where $0\leq r < R$. It is not difficult to show that every recurrent covering map of $X$ must be a rotation. This leads to cases 3 and 4.
- Suppose $\Gamma$ is not abelian. Then, the semigroup $\text{End}(\Gamma) = \\\{ g \in \Gamma \vert g\Gamma g^{-1} \subset \Gamma \\\}$ must be discrete. (See my previous [post](/posts/2021/09/hurwitzs-automorphism-theorem) for more details.) Every iterate $f^n$ admits a lift $g_n \in \text{End}(\Gamma)$ which, due to recurrence, can all be chosen to lie in a compact subset of $\text{Aut}(\mathbb{D})$. By discreteness of $\text{End}(\Gamma)$, the set of lifts $\\\{g_n \\\}$ is finite, i.e. $g_n = g_m$ for some $m<n$. This implies that $f^{n-m} = Id$. This completes case 3.

All the four cases are realised when $X$ is simply connected. The unit translation $z \mapsto z+1$ on the upper half plane $\mathbb{H}$ belongs to case 1. Maps of the form $z\mapsto \lambda z^d$ on the unit disk $\mathbb{D}$ for any positive integer $d$ and non-zero $\lambda \in \mathbb{D}$ are in case 2.

When $X$ is compact, then every non-constant endomorphism $f : X \to X$ is an automorphism. Indeed, when non-constant, $f$ is a branched covering of some degree $d\geq 1$ and by the Riemann-Hurwitz formula,

$$
\chi(X) = d \chi(X) - \sum(e_p - 1)
$$

where $\chi(X)$ is the Euler characteristic and $X \to \mathbb{N}, p \mapsto e_p$ indicates the multiplicity at each point $p$ ($e_p\geq 2$ iff $p$ is a critical point). Since $\chi(X) < 0$, the only instance in which the formula is consistent is when $e_p=1$ everywhere and $d=1$, that is, $f$ is a conformal automorphism of $X$. By finiteness of $\text{Aut}(X)$, $f$ is always of finite order.

### References
<a name="fn1">1</a>: J. Milnor. Dynamics in one complex variable. Princeton University Press, third edition, 2006.   
<a name="fn2">2</a>: C. McMullen, D. Sullivan. Quasiconformal Homeomorphisms and Dynamics III. The Teichmüller Space of a Holomorphic Dynamical System. Advances in Mathematics, Volume 135, Issue 2, Pages 351-395, 1998.

------
