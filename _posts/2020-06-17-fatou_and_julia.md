---
title: 'Fatou and Julia.'
date: 2020-06-17
permalink: /posts/2020/06/fatou_and_julia/
tags:
  - Complex analysis
  - Holomorphic dynamics
  - Dynamical systems
  - Riemann surfaces
---

Complex dynamics is the study of iterations of a holomorphic map $f: X \to X$ where $X$ is a Riemann surface. Dynamical objects of interest are the Fatou set $F(f)$, i.e. the subset of $X$ on which the iterations are stable, and the Julia set, which is the unstable region. Below, I am to summarise the basic concepts of Fatou and Julia sets in one-dimensional complex dynamics where $X$ is the Riemann sphere $\hat{\mathbb{C}} = \mathbb{C} \mathbb{C}up \{\infty\}$.

A collection $\mathcal{F}$ of continuous functions from topological spaces $A$ to $B$ is called a **normal family** if it is precompact with respect to the compact-open topology. That is, every sequence of functions $f_n$ in $\mathcal{F}$ contains a subsequence which converges uniformly on compact subsets of $A$ to a continuous function $f: A \to B$, not necessarily in the family $\mathcal{F}$.

A simple example would be the following. The family of linear maps $\mathcal{F} = \\{ \hat{\mathbb{C}} to \hat{\mathbb{C}}, z \mapsto 2^{-n} z \\}_{n \in \mathbb{Z}}$ is normal because any infinite sequence of maps in $\mathcal{F}$ subsequentially converges to either a map in $\mathcal{F}$, the zero map $z \mapsto 0$, or the infinity map $z \mapsto \infty$.

When $A \subset \hat{\mathbb{C}}$ and $B = \hat{\mathbb{C}}$, Arzelà–Ascoli theorem implies that normality is equivalent to equicontinuity of $\mathcal{F}$ with respect to the spherical metric $d$ on $\hat{\mathbb{C}}$. When the family $\mathca{F}$ is the set of iterates $\{f^n\}_{n \in \mathbb{N}}$ of a holomorphic function $f: A \to \hat{\mathbb{C}}$, equicontinuity means that for all $\epsilon >0$, whenever two points $z$ and $w$ are sufficiently close, then for any iterate $f^n$, $d(f^n(x),f^n(y)) < \epsilon$. This notion is our notion of stability. We then define the **Fatou set** of a holomorphic map $f: \hat{\mathbb{C}} \to \hat{\mathbb{C}}$ to be:

$$
F(f) = \{ z \in \hat{\mathbb{C}} | \text{there is a neighbourhood of } z \text{ on which } \{f^n\}_{n \in \mathbb{N}} \text{ is a normal family} \}.
$$

The **Julia set** of $f$ is the complement $J(f) = \hat{\mathbb{C}} \backslash F(f)$.

------
