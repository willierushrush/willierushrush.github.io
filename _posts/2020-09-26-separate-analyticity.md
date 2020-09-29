---
title: 'Hartogs and Forelli's Separate Analyticity'
date: 2020-09-26
permalink: /posts/2020/09/extremal-length
tags:
  - Several Complex Variables
---

In several complex variables, a function $f: D \to \mathbb{C}$ on an open subset $D \subset \mathbb{C}^n$ is holomorphic if it is separately holomorphic on each variable. A theorem by Hartogs says that this is equivalent to $f$ having a local power series representation in $z = (z_1,\ldots z_n)$ at every point in $D$, i.e. the usual definition of analyticity. A similar result by Forelli states that holomorphicity about a point $a \in \mathbb{C}$ is also satisfied if the function is $c^\infty$ near $a$ and is holomorphic on every one-dimensional complex disk centered at $a$. To me, both are equally interesting results on their own!

## Hartogs

The precise formulation of Hartogs's theorem is the following.

> **_Hartogs's Theorem:_** If $f: D \to \mathbb{C}$ is holomorphic on each variable, then $f$ is holomorphic on $D$, i.e. has a unique local power series representation at every point.

Firstly, I'd like to point out that this result does not hold in the real case. The function

$$
\frac{xy}{x^2+y^2}
$$

is continuously differentiable on every real line (thus continuously differentiable with respect to each variable), but it is not even continuous $(0,0)$. In the complex world, continuity and holomorphicity are always guaranteed because of Hartogs's theorem. I will give a rough idea of the proof for $n=2$. We will assume that the domain $D$ is the polydisk $\mathbb{D}^2 = \\{\vert z_1\vert <1, \vert z_2\vert <1 \\}$.

The first step is to show that $f$ is bounded on $\mathbb{D}_r \times \mathbb{D}$ where $\mathbb{D}_r = \\{\vert z_1\vert <r\\}$ for some small radius $0<r<1$. This is known as Osgood's lemma. We can further assume that $D_1$ is centered at $0$ and on $\mathbb{D}_r \times \mathbb{D}$, $\vert f\vert  \leq 1. By Cauchy's estimates on each variable, for any $z=(z_1,z_2),w=(w_1,w_2) \in \mathbb{D}_r \times \mathbb{D}$,

$$
\vert f(z)-f(w)\vert  \leq \vert f(z_1,z_2) - f(w_1,z_2)\vert  + \vert f(w_1,z_2) - f(w_1,w_2)\vert  \leq \frac{\vert z_1-w_1\vert }{(r-\vert z_1\vert )(r-\vert w_1\vert )} + \frac{\vert z_2-w_2\vert }{(1-\vert z_2\vert )(1-\vert w_2\vert )}.
$$

The inequality will show continuity of $f$ on $\mathbb{D}_r \times \mathbb{D}$.

For each $z_2 \in \mathbb{D}$, $f$ admits a unique power series representation with respect to $z_1$, namely $f(z) = \sum_{k=0}^\infty a_k(z_2) z_1^k$. By Taylor's theorem, the coefficients $a_k(z_2)$ are given by

$$
a_k(z_2) = \frac{1}{2\pi i} \oint_{\vert \zeta\vert  = \rho} \frac{f(\zeta,z_2)}{\zeta^{k+1}} d\zeta,
$$

for any $0 < \rho < r$. As $f$ is holomorphic with respect to $z_2$, then so are $a_k(z_2)$. The last step of the proof is to show that the power series $\sum_{k=0}^\infty a_k(z_2) z_1^k$ converges normally on the whole polydisk $\mathbb{D}^2$. This is typically done using basic properties of subharmonic functions. More details can be found in the book of Bers<sup>[1](#fn1)</sup>.

## Forelli

> **_Forelli's Theorem:_** A function $f: \mathbb{B} \to \mathbb{C}$ that is $C^\infty$ near the origin $0$ and holomorphic on $\mathbb{B} \cap \mathcal{l}$ for every complex line $l$ passing through the origin is necessarily holomorphic on $\mathbb{B}$.

The proof of this theorem is somewhat easier. Pick any $z \in \mathbb{B} \backslash \\{ \underline{0} \\}$. Since $f(\lambda z)$ is holomorphic in $\lambda$ for $\vert \lambda\vert  < \norm{z}^{-1}$, we have a Maclaurin series expansion $f(\lambda z) = f(0) + \sum_{k=1}^\infty F_k(z) \lambda^k$ uniformly convergent for $\vert \lambda\vert \leq 1$. If $\lambda = 1$, then we have that $f(z) = f(0) + \sum_{k=1} F_k(z)$, and the right hand side is uniformly convergent. Once we show that each $F_k$ is holomorphic and $f(z)$ is then holomorphic on $\mathbb{B}$.

By Cauchy's integral formula, the coefficients $F_k(z)$ can be expressed as

$$
F_k(z) = \frac{1}{2\pi i} \oint_{\vert \lambda\vert =1} \frac{f(\lambda z)}{\lambda^{k+1}} d\lambda.
$$

Since $f$ is $C^\infty$ on some complex ball $\\{ \norm{z}<r \\}$ for some small r>0$, then $F_k$ is $C^\infty$ (and thus bounded) on $\\{ \norm{z}<r \\}$. By uniqueness of the Maclaurin series, we have that $F_k(\lambda z) = \lambda^k F_k(z)$ whenever $\vert \lambda\vert \leq 1$. The identity implies that if $w$ is close to zero, $\vert F_k(z)\vert  \leq M\vert z\vert ^k$ for some $M>0$. Therefore, the real Maclaurin series expansion of $F_k$ can be written as

$$
F_k(z) = \sum_{p+q=k} P_{p,q}(z) + \vert z\vert ^k Q(z),
$$

where $P_{p,q}$ is a homogeneous polynomial of total degree $p$ in $z=(z_1,\ldots z_n)$ and $q$ in $\bar{z} = (\bar{z_1}, \ldots \bar{z_n})$, and $Q(z) = \mathcal{O}(\vert z\vert )$ as $z \to 0$.

Since $F_k(\lambda z) = \lambda^k F_k(z)$, then

$$
\sum_{p+q = k} P_{p,q}(z) \lambda^p \bar{\lambda}^q + \vert \lambda\vert ^k \vert z\vert ^k Q(\lambda z) = \sum_{p+q=k} P_{p,q}(z) \lambda^k + \lambda^k \vert z\vert ^k Q(z).
$$

When $0< \lambda<1$, we see that $Q(\lambda z) = Q(\lambda)$. However, since $Q(z)\to 0$ as $z \to 0$, this implies that $Q \equiv 0$. By the uniqueness of power expansions, $F_k(z)$ must then coincide with the polynomial $P_{k,0}(z)$, which is holomorphic on $\mathbb{C}^n$. As mentioned earlier, this will imply that $f(z)$ is holomorphic on $\mathbb{B}$.

### References

<a name="fn1">1</a>: L. Bers, Introduction to several complex variables, New York Univ. Press, New York, 1964.  
<a name="fn2">2</a>: B. V. Shabat, Introduction to Complex Analysis: Part II, Functions of Several Variables. Translated from the third (1985) Russian edition by J S Joel. Translations of Mathematical Monographs, 110. American Mathematical Society, Providence, RI, 1992.  
