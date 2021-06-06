---
title: 'Local Analytic Linearisation'
date: 2021-06-05
permalink: /posts/2021/06/local-analytic-linearisation
tags:
  - Dynamical systems
  - Holomorphic dynamics
---

Given a dynamical system $f: X \to X$ with a fixed point $x \in X$, what can we say about the dynamical behaviour of $f$ near $x$? For many sufficiently smooth functions $f$, the behaviour of $f$ near $x$ is governed by its linear approximation $Df_x$. More precisely, $f$ is conjugate to $Df_x$ when the derivative $Df_x$ is hyperbolic, i.e. has no eigenvalue with absolute value $1$. Proving local linearisability can be a rather daunting task, requiring a rather involved theory of hyperbolic systems, I would like to discuss the baby problem of local linearisability of analytic functions of 1 variable in this post.

> **_Theorem:_** Let $f$ be a real analytic map on an interval neighbourhood $I$ of $0$ such that $f(0)=0$ and $f'(0) = \lambda \not \in \\\{0, \pm 1 \\\}$. There is an real analytic diffeomorphism $h : J \to K$ for some neighbourhoods $J$ and $K$ of $0$ such that $h\circ f (x) = \lambda h(x)$ for all $x \in J$. Moreover, $h$ is unique up to multiplication by a non-zero constant.

There is a reason why we exclude the values $0$ and $\pm 1$. If the theorem holds for value $0$ or $1$, then $h\circ f \circ h^{-1}$ is either the zero map or the identity map and clearly the only possible $f$ that can satisfy this is either the zero map or the constant map. For $-1$, we consider the second iterate $f^2$ which leads us back to the $1$ case.

A stronger version of this theorem is its complex version:

> **_Theorem:_** Let $f$ be a holomorphic map on a neighbourhood $U \subset \mathbb{C}$ of $0$ such that $f(0)=0$ and $f'(0)=\lambda$ where $\vert \lambda \vert \neq 0,1$. There is a conformal isomorphism $h : V \to W$ for some neighbourhoods $V$ and $W$ of $0$ such that $h \circ f (z) = \lambda h(z)$ for all $z \in V$. Moreover, $h$ is unique up to multiplication by a non-zero constant.

In this version, it is clear that the theorem cannot hold for $\lambda = e^{2\pi i p/q}$ for some integers $p$ and $q$ since otherwise the $q^{th}$ iterate $f^q$ would be the identity but the only holomorphic map near $0$ satisfying $f^q(z)=z$ is the rotation map $z \mapsto \lambda z$. When $\lambda = e^{2\pi i \theta}$ for some irrational number $\theta$, linearisability is possible and it depends on the continued fraction expansion of $\theta$. This is a much more complicated story (hint: KAM theory) and we will not delve into it here.

## Existence

If $\vert \lambda \vert >1$, then we can find the map $h$ conjugating the inverse $f^{-1}$ with $z \mapsto \lambda^{-1}z$; the map $h$ will also conjugate $f$ with $z \mapsto \lambda z$. As such, let's assume that $\vert \lambda \vert < 1$. We will show that $h(z) = \lim_{n\to \infty} \lambda^{-n} f^n(z)$ converges uniformly near $0$. This will give us the desired conjugacy since

$$
h \circ f(z) = \lim_{n\to \infty} \lambda^{-n} f^{n+1}(z) = \lambda \lim_{n\to \infty} \lambda^{-n-1} f^{n+1}(z) = \lambda h(z).
$$

Pick a real constant $c \in (0,1)$ such that $\vert \lambda \vert \in (c^2,c)$. There is some small radius $r>0$ such that on the open disk $\mathbb{D}_r$ of radius $r$ centered at $0$ and some constant $C>0$ such that

$$
\vert f(z) \vert \leq c \vert z \vert \quad \text{and} \quad \vert f(z)-\lambda z \vert \leq C \vert z \vert^2.
$$

If $z \in \mathbb{D}_r$, then

$$
\vert f^{n+1}(z) - f^n(z) \vert \leq C \vert f^n(z) \vert^2 \leq C c^{2n} \vert z \vert \leq C c^{2n} r^2.
$$

Dividing by $\vert \lambda \vert^{n+1}$ yields

$$
\vert \lambda^{-n-1} f^{n+1}(z) - \lambda^{-n} f^n(z) \vert \leq C \vert\lambda\vert^{-1} r^2 \vert c^2 \lambda^{-1} \vert^n.
$$

The inequality above gives uniform convergence of the sequence of holomorphic functions $\lambda^{-n} f^n(z)$. Therefore, the limit $h(z)$ is a well defined holomorphic map near $0$. Since $\lambda^{-n} (f^n)'(0) = 1$ for all $n$, $h'(0)= 1$ too, which then implies that $h$ is a conformal isomorphism locally near $0$.

## Uniqueness

Suppose $g$ and $h$ are two such solutions. Since $f(z) = g^{-1}(\lambda g(z)) h^{-1}(\lambda h(z))$, then on a neighbourhood of $0$, $gh^{-1}$ commutes with the linear map $z \mapsto \lambda z$. Therefore, if $A = (gh^{-1})'(0)$, for any $z$ near $0$,

$$
A = \lim_{n \to \infty} \frac{gh^{-1}(\lambda^{n} z)}{\lambda^{n}z} =  \lim_{n \to \infty} \lambda^{n} \frac{gh^{-1}}{\lambda^{n}z} = \frac{gh^{-1}(z)}{z}.
$$

This implies that $g(z) = A h(z)$.

## Finding $h$

Let $f(z) = \lambda z + \sum_{n\geq 2} a_n z^n$ be the MacLaurin series for $f$. We can find the coefficients $b_n$ (by brute force) such that $h(z) = z + \sum_{n\geq 2} b_n z^n$ is a conformal conjugacy for $f$ and $z \mapsto \lambda z$. The functional equation can be rewritten as:

$$
\left( \lambda x + \sum_{n \geq 2} a_n z^n \right) + \sum_{m\geq 2} b_m \left( \lambda x + \sum_{n \geq 2} a_n z^n \right)^m = \lambda z + \sum_{n \geq 2} \lambda b_n z^n.
$$

We can determine the coefficients $b_n$ inductively by comparing the coefficients of $x^n$. The first few $b_n$'s are as follows:

$$
b_2 = \frac{a_2}{\lambda-\lambda^2}, \quad b_3 = \frac{a_3 + b_2(2\lambda a_2)}{\lambda - \lambda^3}, \quad b_4 = \frac{a_4 +b_2 (a_2^2 + 2\lambda a_3) + b_3 (3\lambda^2 a_2)}{\lambda - \lambda^4}.
$$

The general form of $b_n$ is

$$
b_n = \frac{a_n + \sum_{k=2}^{n-1} b_k c_{n,k}}{\lambda - \lambda^n}
$$

where $c_{n,k}$ is a degree $k$ homogeneous polynomial in which each term is of the form $\lambda^{d_1} a_2^{d_2} \ldots a_{k-1}^{d_{k-1}}$ where $\sum_{m=1}^{k-1} m d_m = n$.

As an example, if $f(z) = \frac{z+z^2}{2}$, then the conjugacy $h(z)$ near $0$ has the MacLaurin series development

$$
h(z) = z + 2z^2 + \frac{8}{3}z^3 + \frac{24}{7}z^4 + \ldots.
$$

An alternative proof for the theorem can be made by showing that $\lambda z + \sum_{n \geq 2} \lambda b_n z^n$ converges on some neighbourhood of $0$ by obtaining an upper bound $M>0$ for all $\vert b_n \vert$ 's and applying Abel's theorem. This is done in the book<sup>[1](#fn1)</sup> of Katok and Hasselblatt, Chapter 2.

### References

<a name="fn1">1</a>: A. Katok, B. Hasselblatt. Introduction to the Modern Theory of Dynamical Systems. Encyclopedia of Mathematics and its Applications, volume 54. Cambridge University Press, Cambridge, 1995.  
<a name="fn2">2</a>: J. Milnor. Dynamics in one complex variable. Princeton University Press, third edition, 2006.   

------
