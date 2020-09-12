---
title: 'Extremal Lengths'
date: 2020-09-12
permalink: /posts/2020/09/extremal-lengths
tags:
  - Complex Analysis
---

Consider a non-empty open subset $D \subset \mathbb{C}$ of the complex plane and the set $\mathcal{A_D}$ of all measurable functions $\rho : D \to [0,\infty)$ such that $D$ always have finite positive $\rho$-area $A_\rho (D) = \int_D \rho^2 dx dy$. The **extremal length** $\lambda(\Gamma)$ of a collection of rectifiable curves $\Gamma$ in $D$ is defined to be

$$
\lambda(\Gamma) := \sup_{ \rho \in \mathcal{A} } \frac{L_\rho (\Gamma)^2}{A_\rho (D)},
$$

where $L_{\rho} (\Gamma)$ is the infimum of $\rho$-lengths $L_\rho (\gamma) = \int_\gamma \rho |dz|$ of curves $\gamma \in \Gamma$.

To get the idea of what extremal length is and how it can be computed, let's look at some easy examples.

Let's have the regular rectangle $R = \\{ x+iy \: | \: 0\leq x \leq a, 0 \leq y \leq b \\}$ of side lengths $a>0$ and $b > 0$ and the family $\Gamma$ of rectifiable curves in $R$ joining the left vertical side with the right vertical side. For the Euclidean weight $\rho \equiv 1$ on $R$, $A_\rho (R) = ab$ is the usual rectangular area and clearly $L_{\rho} (\Gamma)$ must be $a$, the distance between the vertical sides. Therefore, we have an upper bound: $\lambda(\Gamma) \geq \frac{a^2}{ab} = \frac{a}{b}$.
