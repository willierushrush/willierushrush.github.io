---
layout: single
title:  "Draft Post"
header:
  teaser: "unsplash-gallery-image-2-th.jpg"
categories:
  - Jekyll
tags:
  - edge case
---

## Extremal Length

We wish to introduce a conformal invariant on families of curves and define quasiconformal maps as those which distort this invariant up to some bounded constant. Consider the set $\mathcal{A}$ of all measurable functions $\rho: \mathbb{C} \to [0,\infty)$ such that the $\rho$-area $A(\rho) = \int_{\mathbb{C}} \rho^2 dx dy$ is a finite positive number. Consider a family of rectifiable curves $\Gamma$ and define the $\rho$-length of $\Gamma$ as

$$
L_{\Gamma} (\rho) = \inf_{\gamma \in \Gamma} L_{\gamma}(\rho),
$$

where $L_{\gamma}(\rho) = \int_\gamma \rho \vert dz \vert$ is the $\rho$-length of the curve $\gamma$. Then, the extremal length $\lambda(\Gamma)$ of $\Gamma$ is defined as

$$
\lambda(\Gamma) = \sup_{\rho \in \mathcal{A}} \frac{ L_{\Gamma}(\rho)^2 }{A(\rho)}.
$$

A simple example is the following. Let $\Gamma$ be the set of rectifiable curves on the rectangle $U = \\{ x+iy \: \vert \: 0\leq x \leq a, 0 \leq y \leq b \\}$ with an endpoint lying on a vertical side of $U$ and another endpoint on the other vertical side of $U$. The extremal length of $\Gamma$ is $\lambda(\Gamma) = \frac{a}{b}$.
