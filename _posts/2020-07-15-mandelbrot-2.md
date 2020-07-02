---
title: 'Mandelbrot 2'
date: 2020-07-15
permalink: /posts/2020/07/mandelbrot-2/
tags:
  - Complex analysis
  - Holomorphic dynamics
  - Dynamical systems
---

A central conjecture in holomorphic dynamics is the following.

> **_MLC Conjecture:_** The Mandelbrot set is locally connected.

Local connectivity of $\mathbb{M}$ has highly important implications. An immediate one is that the conformal isomorphism $\Phi^{-1}$ extends to a continuous map from the unit circle $S^1$ to the boundary $\partial\mathbb{M}$. Topologically, this extension will allow us to obtain a precise topological model of $\mathbb{M}$. Dynamically, MLC implies (in fact, is equivalent) to a strong property called combinatorial rigidity which says that any two quadratics $f_c$ and $f_{c'}$ having no non-repelling periodic points have the same combinatorics if and only if $c = c'$.

## Hyperbolic components

We say that $c \in \mathbb{M}$ is a **hyperbolic parameter** if $f_c$ has a finite attracting periodic point. The Julia sets of hyperbolic maps are nice to deal with since they have zero area and are locally connected. (Refer to Milnor<sup>[2](#fn2)</sup> $\S 19$.)

Recall that a $p$-periodic point $z_c$ is attracting if the derivative $(f_c^p)'(z_c)$ lies in the unit disk. Since the map $c \mapsto (f_c^p)'(z_c)$ is non-constant and holomorphic, the set of hyperbolic parameters is open in $\mathbb{M}$. We call a component $C$ of the interior of $\mathbb{M}$ **hyperbolic** if all the parameters in $C$ are hyperbolic, and **queer** if otherwise. Each hyperbolic component $H$ has a period $p$ such that for each parameter $c \in H$, $f_c$ has an attracting periodic point of period $p$.

Ultimately, MLC implies one of the most important open problems in holomorphic dynamics.

> **_Density of Hyperbolicity Conjecture:_** The set of parameters $c \in \mathbb{M}$ such that $f_c$ is hyperbolic is dense in $\mathbb{M}$.

The conjecture is equivalent to the statement that queer components do not exist.

There are a few hyperbolic components which are easy to understand. The main cardioid $H_1$ is the central hyperbolic component of period $p=1$. It consists of parameters $c$ where $f_c$ has an attracting fixed point. (This includes $c=0$.) Elementary calculus should easily show you that $H_1$ is the image of the unit disk $\mathbb{D}$ under the quadratic map $w \mapsto \frac{1}{4}(2w - w^2)$.

An interesting coincidence is that the hyperbolic component $H_2$ of period $p=2$ is a round disk. We know that $c \in H_2$ if and only if $f_c$ has an attracting 2-periodic point $z_c$. By periodicity, this point satisfies the equation

$$
f^2_c(z) - z = z^4 + 2c z^2 + c^2 + c = 0.
$$

We know that the equation is also satisfied by the two fixed points $z_1$ and $z_2 of $f_c$, both of which are solutions of the equation $f_c(z) - z = z^2 - z + c = 0$. We can then factorise the first equation to $z^4 + 2c z^2 + c^2 + c = (z^2 -z + c)(z^2 + z + c+1)$ and thus, $z_c$ and $f_c(z_c)$ are the roots of $z^2 + z + c+1$ and the product is $c+1$. Thus,

$$
|(f_c^2)'(z)| = 4|z f_c(z)| = 4|c+1| < 1.
$$

Therefore, $H_2$ is the round disk of radius $\frac{1}{4}$ centered at $-1$.

### References
<a name="fn1">1</a>: A. Douady, J. Hubbard. Exploring the Mandelbrot set. The Orsay Notes. Available at http://pi.math.cornell.edu/~hubbard/OrsayEnglish.pdf   
<a name="fn2">2</a>: J. Milnor. Dynamics in one complex variable. Princeton University Press, third edition, 2006.   

------
