---
title: 'Extremal Lengths'
date: 2020-09-12
permalink: /posts/2020/09/extremal-lengths
tags:
  - Complex Analysis
---

Consider a non-empty open subset $D \subset \mathbb{C}$ of the complex plane and the set $W_D$ of all measurable functions $\rho : D \to [0,\infty)$ such that $D$ always has finite positive $\rho$-area $A_\rho (D) = \int_D \rho^2 dx dy$. The **extremal length** $\lambda(\Gamma)$ of a collection of rectifiable curves $\Gamma$ in $D$ is defined to be

$$
\lambda(\Gamma) := \sup_{ \rho \in W_D } \frac{L_\rho (\Gamma)^2}{A_\rho (D)},
$$

where $L_{\rho} (\Gamma)$ is the infimum of $\rho$-lengths $L_\rho (\gamma) = \int_\gamma \rho \vert dz\vert$ of curves $\gamma \in \Gamma$.

## Some Properties

Extremal length gives us a measurement of curve families that is invariant under conformal maps. For this reason, its study has a variety of uses in complex analysis.

> **_Proposition:_** Let $f: U \to V$ be a biholomorphism of two domains $U, V$ in $\mathbb{C}$. For any family of rectifiable curves $\Gamma$ on $U$, if $f(\Gamma) = \\{ f\circ \gamma \\}_{\gamma \in \Gamma }$, then $\lambda( f(\Gamma) ) = \lambda( \Gamma)$.

Indeed, due to conformality of $f$, we have a bijection of weight functions $f^\* : W_V \to W_U, \rho \mapsto f\*\rho$ where the pullback is defined by $f^\*\rho(z) = \rho(f(z)) \vert f'(z)\vert$ for all $z \in U$. By change of variables formula, $A_\rho (V) = A_{f^\*\rho} (U)$ and $L_\rho( f(\gamma)) = L_{f^\*\rho} (\gamma)$ for every $\gamma \in \Gamma$.



## Some examples

To get the idea of what extremal length is and how it can be computed, let's look at some easy examples.

Let's have the regular rectangle $R = \\{ x+iy \: \vert \: 0\leq x \leq a, 0 \leq y \leq b \\}$ of side lengths $a>0$ and $b > 0$ and the family $\Gamma$ of rectifiable curves in $R$ joining the left vertical side with the right vertical side. Pick any arbitrary $\rho \in W_R$. Horizontal curves $\gamma_y(x) = x+iy$, $0 \leq x\leq a$ for fixed values of $y \in [0,b]$ belong to $\Gamma$. Since $L_{\rho} (\Gamma) \leq L_\rho (\gamma_y)$,

$$
b L_\rho (\Gamma) = \int_0^b L_\rho (\Gamma) dy \leq \int_0^b L_\rho (\gamma_y) dy = \int \int_R \rho(x+iy) dx dy.
$$

By Cauchy-Schwarz,

$$
b^2 L_\rho (\Gamma)^2 \leq \left( \int\int_R dx dy \right) \left( \int\int_R \rho(x+iy)^2 dx dy\right) = ab A_\rho (R).
$$

Upon rearrangement, we obtain an upper bound: $\lambda(\Gamma) \leq \frac{a}{b}$. The upper bound is indeed achieved by the Euclidean weight $\rho \equiv 1$ because in this case, $A_\rho(R)$ is the usual area $ab$ of the rectangle and $L_\rho (\Gamma)$ is the minimal length $a$ of curves in $\Gamma$. Therefore, the extremal length of $\Gamma$ is $\frac{a}{b}$. This quantity is more commonly known as the **modulus** $\text{mod}(R)$ of the rectangle $R$.

Let's consider another example. Consider the family $\Gamma$ of rectifiable curves in the concentric annulus $\mathbb{A}\_{r_1,r_2} = \\{ r_1 \leq \vert z\vert \leq r_2 \\}$, where $0<r_1<r_2<\infty$, which join the two boundary components of $\mathbb{A}\_{r_1,r_2}$. Pick any arbitrary $\rho \in W_{\mathbb{A}\_{r_1,r_2}}$. Radial curves $\gamma_\theta(r) = re^{i\theta}$, $r_1 \leq r \leq r_2$ for fixed angles $\gamma \in [0,2\pi)$ belong to $\Gamma$. Since $L_{\rho} (\Gamma) \leq L_\rho (\gamma_\theta)$,

$$
2\pi L_\rho(\Gamma) = \int_0^{2\pi} L_\rho(\Gamma) d\theta \leq \int_0^{2\pi} L_\rho(\gamma_\theta) d\theta = \int_0^{2\pi} \int_{r_1}^{r_2} \rho(re^{i\theta}) dr d\theta.
$$

By Cauchy-Schwarz,

$$
4\pi^2 L_\rho (\Gamma)^2 \leq \left( \int_0^{2\pi} \int_{r_1}^{r_2} \frac{1}{r} dr d\theta \right) \left( \int_0^{2\pi} \int_{r_1}^{r_2} \rho( r e^{i\theta}) r dr d\theta \right) = 2\pi \log \left( \frac{r_2}{r_1} \right) A_\rho ( \mathbb{A}_{r_1,r_2} ).
$$

Upon rearrangement, we obtain an upper bound $\lambda(\Gamma) \leq \frac{1}{2\pi} \log\left(\frac{r_2}{r_1}\right)$. This upper bound is again achieved by the weight function $\rho(re^{i\theta}) = \frac{1}{r}$, so the extremal length of $\Gamma$ is indeed $\frac{1}{2\pi} \log\left(\frac{r_2}{r_1}\right)$. This quantity is again called the **modulus** $\text{mod}(\mathbb{A}\_{r_1,r_2})$ of the regular annulus $\mathbb{A}_{r_1,r_2}$. In the case where $r_1 = 0$ and/or $r_2 = \infty$, we set the modulus to be $\infty$. Observe that we can also obtain the modulus from the conformal map $R \to \mathbb{A}\_{r_1,r_2}, z \mapsto r_1 e^{2\pi a/b}$ where the sides $a$ and $b$ of the rectangle $R$ are picked such that $\frac{r_2}{r_1} = e^{2\pi a/b}$. This conformal map should give you a hint on the equivalence between $\text{mod}(R)$ and $\text{mod}(\mathbb{A}\_{r_1,r_2})$.

By conformal invariance, we see that the modulus of a regular rectangle or concentric is a conformal invariant. We can define the modulus of a topological annulus $\Omega$ either as the extremal length of the family of rectifiable curves in $\Omega$ joining the two boundary components, or as the modulus of a concentric annulus $\Omega'$ biholomorphic to $\Omega$. We can also define similarly the modulus of an arbitrary topological quadrilateral $Q = (Q,a_1,a_2,a_3,a_4)$, which is a Jordan disk in $\mathbb{C}$ equipped with four vertices $a_i$ for $i=1,2,3,4$ lying on the boundary $\partial Q$ and labelled cyclically in a counterclockwise manner. We additionally require that the biholomorphism sends vertices to vertices accordingly.

## Weyl's Lemma

We say that an orientation preserving homeomorphism $f: U \to V$ between domains $U,V$ in $\mathbb{C}$ is **$K$-quasiconformal** if there is some $K \geq 1$ such that for any family of rectifiable curves $\Gamma$ in $U$,

$$
\frac{\lambda(\Gamma)}{K} \leq \lambda(f(\Gamma)) \leq K \lambda(\Gamma).
$$

In other words, these maps distort extremal lengths up to some bounded factor. It may not be obvious but this definition is in fact equivalent with the other definitions I have introduced in my previous [post](/posts/2020/08/quasiconformal-maps). Quasiconformal maps naturally generalise conformal maps because of the following result.

> **_Weyl's Lemma_** For an orientation preserving homeomorphism $f: U \to V$, the following are equivalent:
> (1) $f$ is conformal,
> (2) $f$ preserves extremal lengths,
> (3) $f$ is 1-quasiconformal.

The only non-obvious implication is (3) $\Rightarrow$ (1). This is automatically true if $f$ is $C^1$, but in general we have to be more careful. We will follow directly from Ahlfors' approach. Suppose $f$ is $1$-quasiconformal and pick any arbitrary regular quadrilateral $Q \subset U$ of some modulus $m>0$. Draw some arbitrary disjoint vertical line segments to partition $Q$ into $Q_1, Q_2, \ldots Q_k$ for some $k\in \mathbb{N}$. Let $m_i$ be the modulus of each $Q_i$, then clearly $m = \sum_i m_i$. Denote by $Q'$ and $Q'_i$ the images of $Q$ and $Q_i$ for $i = 1, 2,\ldots k$ under $f$. By the assumption, $Q'$ and $Q'_i$'s have moduli $m$ and $m_i$.

By drawing some $l-1$ disjoint curves in $Q'$ joining the vertical sides, partition each $Q'_i$ into $Q'\_{i1}, Q'\_{i2}, \ldots Q'\_{il}$ in such a way that $m_i^{-1} = \sum_j m\_{ij}^{-1}$, where $m\_{ij}$ denotes the modulus of $Q'\_{ij}$. We claim that the corresponding dividing horizontal curves in $Q$ must be straight line segments. There is a unique conformal map $g : Q' \to Q$ preserving the vertices. Since the moduli matches, $g$ sends each $Q'_i$ to $Q_i$ and $Q'\_{ij}$ to $Q\_{ij}$. As the subdivision is arbitrary, $g$ must be the inverse of $f$. Therefore, $f$ is conformal.

What remains is to show that the claim holds. This subproblem can be simplified as follows. Let $l$ be a vertical curve dividing the rectangle $R = \\{ x+iy \: \vert \: 0\leq x \leq m, 0\leq y \leq 1 \\}$ of modulus $m$ into two open quadrilaterals $R_1$ and $R_2$ of moduli $m'$ and $m"$. We need to show that if $m' + m" = m$, then $l$ is the vertical line segment $\\{x=m'\\}$. Indeed, we can find two conformal maps

$$
f_1 : R_1 \to \{ x+iy \: \vert \: 0<x< m', 0 <y<1 \}, \quad f_2 : R_2 \to \{ x+iy \: \vert \: m'< x < m, 0 <y < 1 \}.
$$

and let $\rho(z) = \vert f_i'(z)\vert$ if $z \in R_i$ for $i=1,2$, $0$ otherwise. Then,

$$
\int\int_R \rho^2 -1 dx dy = (m'+m'')-m = 0
$$

and by Cauchy-Schwarz

$$
\int\int_R \rho - 1 dx dy \geq \frac{ \left( \int\int_R \rho^2 -1 dx dy \right)^2 }{ \int\int_R \rho + 1 dx dy } = 0.
$$

Therefore, $\int\int_R (\rho-1)^2 dx dy = \int\int (\rho^2 - 1) - 2(\rho -1) dx dy \leq 0$, which immediately implies that $\rho$ must be $1$ almost everywhere in $R$. As such, $f_i$'s must be identity maps and $l$ must be the vertical line $\\{x=m'\\}$. All in all, the claim holds and (3) does imply (1).

Next time, I aim to post more about what makes quasiconformal maps interesting and what we can do with them.
