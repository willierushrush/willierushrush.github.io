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

Indeed, due to conformality of $f$, we have a bijection of weight functions $f^\* : W_V \to W_U, \rho \mapsto f*\rho$ where the pullback is defined by $f^\*\rho(z) = \rho(f(z)) \vert f'(z)\vert$ for all $z \in U$. By change of variables formula, $A_\rho (V) = A_{f^\*\rho} (U)$ and $L_\rho( f(\gamma)) = L_{f^\*\rho} (\gamma)$ for every $\gamma \in \Gamma$.

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

Upon rearrangement, we obtain an upper bound: $\lambda(\Gamma) \leq \frac{a}{b}$. The upper bound is indeed achieved by the Euclidean weight $\rho \equiv 1$ because in this case, $A_rho(R)$ is the usual area $ab$ of the rectangle and $L_\rho (\Gamma)$ is the minimal length $a$ of curves in $\Gamma$. Therefore, the extremal length of $\Gamma$ is $\frac{a}{b}$. This quantity is more commonly known as the **modulus** of the rectangle $R$. (I've discussed this briefly in [here](/posts/2020/08/quasiconformal-maps).) By conformal invariance, we see that modulus is also a conformal invariant.

Let's consider another example. Consider the family $\Gamma$ of rectifiable curves in the regular annulus $\mathbb{A}\_{r_1,r_2} = \\{ r_1 \leq \vert z\vert \leq r_2 \\}$, where $0<r_1<r_2<\infty$, which join the two boundary components of $\mathbb{A}\_{r_1,r_2}$. Pick any arbitrary $\rho \in W_{\mathbb{A}\_{r_1,r_2}}$. Radial curves $\gamma_\theta(r) = re^{i\theta}$, $r_1 \leq r \leq r_2$ for fixed angles $\gamma \in [0,2\pi)$ belong to $\Gamma$. Since $L_{\rho} (\Gamma) \leq L_\rho (\gamma_\theta)$,

$$
2\pi L_\rho(\Gamma) = \int_0^{2\pi} L_\rho(\Gamma) d\theta \leq \int_0^{2\pi} L_\rho(\gamma_\theta) d\theta = \int_0^{2\pi} \int_{r_1}^{r_2} \rho(re^{i\theta}) dr d\theta.
$$

By Cauchy-Schwarz,

$$
4\pi^2 L_\rho (\Gamma)^2 \leq \left( \int_0^{2\pi} \int_{r_1}^{r_2} \frac{1}{r} dr d\theta \right) \left( \int_0^{2\pi} \int_{r_1}^{r_2} \rho( r e^{i\theta}) r dr d\theta \right) = 2\pi \log \left( \frac{r_2}{r_1} \right) A_\rho ( \mathbb{A}_{r_1,r_2} ).
$$

Upon rearrangement, we obtain an upper bound $\lambda(\Gamma) \leq \frac{1}{2\pi} \log\left(\frac{r_2}{r_1}\right)$. This upper bound is again achieved by the weight function $\rho(re^{i\theta}) = \frac{1}{r}$, so then the extremal length of $\Gamma$ is indeed $\frac{1}{2\pi} \log\left(\frac{r_2}{r_1}\right)$.
