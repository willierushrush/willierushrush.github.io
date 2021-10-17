---
title: 'Neutral local analytic linearisation'
date: 2021-10-17
permalink: /posts/2021/10/neutral-local-analytic-linearisation
tags:
  - Dynamical systems
  - Holomorphic dynamics
---

Given a dynamical system $f: X \to X$ with a fixed point $x \in X$, what can we say about the dynamical behaviour of $f$ near $x$? In my previous [post](/posts/2021/06/local-analytic-linearisation), we discussed that for analytic functions of 1 variable, if the derivative $\lambda =f'(x)$ at $x$ is non-zero and $\vert \lambda \vert \neq 1$, then $f$ is locally conjugate to its linear part $z \mapsto \lambda z$. What happens when $\lambda$ lies on the unit circle? In this case, the fixed point $x$ is called neutral and the problem of linearisability near $x$ becomes much more complicated than the non-neutral case.

For convenience, let's simplify the objects we are dealing with to a map of the form $f(z) = \lambda z + O(z^2)$ where $f$ is well defined and holomorphic on a neighbourhood $U$ of the fixed point $0$ with multiplier $f'(0)= \lambda = e^{2 \pi i \theta}$ for some angle $\theta \in [0,1)$. We say that $f$ is analytically linearisable at $0$ if there is some conformal change of coordinates $h: V \to h(V)$ on a neighbourhood $V \subset U$ of $0$ such that $h(f(z)) = \lambda h(z)$ for all $z \in V$.

The answer to the linearisability problem lies in the nature of the angle $\theta$.

## Parabolic case

Suppose $\theta$ is rational of the form $\frac{p}{q}$ where $\text{hcf}(p,q)=1$. The linear map $z \mapsto \lambda z$ has finite order $q$ and on a neighbourhood of $0$, the $q$-th iterate $f^q$ coincides with the identity map. It is a straightforward exercise on power series to check that $f$ has to be the rotation $f(z) = \lambda z$. In other words, non-linear germs with rational $\theta$ are not linearisable.

There is, however, a different way to describe the local behaviour of $f$ near $0$. The iterate $f^q$ is of the form $f^q(z) = z + a z^{m+1} + \ldots$ where $b \neq 0$ and higher order terms are omitted. The corresponding iterates are of the form $f^{nq}(z) = z + na z^{n+1} + \ldots$.

We say that an open Jordan domain $P$ is an **attracting petal** for $f$ if $f^{q}$ maps $P$ univalently into $P$ itself, $0$ is on the boundary of $P$ and $\partial P \cap \partial f^q(P) = \\\{0 \\\}$. Every point $z$ on a petal has the same dynamics: $f^{qn}(z) \to 0$ as $n\to \infty$. If $P$ is a petal, then $f^q(P)$ is a sub-petal lying inside $P$. Given a petal $P'$, there is a maximal petal $P$ containing $P'$ lying in $U$.

> **_Leau-Fatou Flower Theorem:_** Let $f(z) = e^{2\pi i \theta} z + \ldots$ be a non-linear holomorphic map on a neighborhood $U$ of $0$ such that $f^q(z) = z + a z^{m+1} + \ldots$ for some $n \in \mathbb{N}$ and $b \neq 0$. Then,
1. $n$ is a multiple of $q$, i.e. $n=kq$ for some integer $k$.
2. There are precisely $n$ disjoint maximal attracting petals $\\\{ P_i \\\}\_{i=1,\ldots n}$ in $U$ each making an angle of $\frac{2\pi}{n}$ at $0$ such that $f$ permutes the petals with rotation number $\frac{p}{q}$, that is, if the indices $i$ are cyclically labeled mod n, then $f(P_i) \subset P_{i+kp}$.

As an example, you can check that $f(z)= -z+z^6$ must have $m=10$ attracting petals and $f$ interchanges each pair of opposite petals. Even though $f$ is not linearisable at $0$, the action of $f$ on the petals act like translations under certain coordinates.

> **_Parabolic Linearisation Theorem:_** For any attracting petal $P$, there is a conformal embedding $\alpha : P \to \mathbb{C}$ such that $\alpha(f^q(z)) = \alpha(z) + 1$ for all $z \in P$. Moreover, $\alpha$ is unique up to post-composition with translations.

Note that the attracting behaviour of $0$ does not extend beyond the petals. Outside of the petals, the fixed point $0$ is repelling in $m$ different directions, that is, the local inverse orbit $f^{-qn}(z)$ converges to $0$ if $z$ is close to $0$ but does not lie in any of the attracting petals. These repelling directions are permuted by $f$ with rotation number $\frac{p}{q}$. This can be formulated carefully by defining "repelling petals", i.e. petals for the local inverse $f^{-1}$. Each repelling petal intersects precisely two attracting petals, one on the left and one on the right.

## Irrational case

Now, suppose $\theta$ is irrational. The problem of analytic linearisation becomes an arithmetic problem which is best described using the best rational approximations $\\\{\frac{p_n}{q_n} \\\}_{n \in \mathbb{N}}$ of $\theta$. Have a look at this [post](/posts/2021/01/continued-fractions) for more details.

> **_Theorem:_** Let $f(z) = e^{2\pi i \theta} z + \ldots$ be a non-linear holomorphic map on a neighborhood $U$ of $0$. Then, $f$ is linearisable at $0$ if and only if $\theta$ is a Brjuno number, that is, the best rational approximations $\\\{\frac{p_n}{q_n} \\\}\_{n \in \mathbb{N}}$ of $\theta$ induces a convergent infinite sum: $ \sum_{n=1}^\infty \frac{\log q_{n+1}}{q_n} < \infty$.

Siegel first showed that linearisability holds when $\theta$ is a **Diophantine number**, i.e. there is some $c>0$ and $d>0$ such that for any non-zero integers $p$ and $q$, $\vert p - \theta q \vert > c q^{-d}$. The proof of Siegel's result is accessible in Katok's book<sup>[1](#fn1)</sup> and it relies on the "KAM method" after Kolmogorov, Arnol'd, and Moser. Brjuno later extended Siegel's result for Brjuno numbers, and this condition is proved to be necessary by Yoccoz.

Some examples of Diophantine numbers include irrationals of bounded type, i.e. the continued fraction expansion $[0;a_1, a_2, \ldots]$ satisfies $\sup_i a_i < \infty$. These include the golden ratio and all quadratic irrationals.

The Brjuno condition essentially says that $\theta$ cannot be too closely approximated by any rational number. For any positive integer $n$, we have the approximation $\vert \theta - \frac{p_n}{q_n}\vert < \frac{1}{q_n q_{n+1}}$. When $\log(q_{n+1}) > q_n$ is very large, then we can say that the right hand side of the inequality becomes very small and $\theta$ is extremely close to $\frac{p_n}{q_n}$, causing $f$ to be extremely close to the rational case with multiplier $e^{2\pi i p_n / q_n}$. As such, remnants of attracting and repelling petals near $0$ would cause the failure of $f$ to be conjugate to a rotation about $0$.

If $\theta$ is a Brjuno number, the maximal domain $U$ in which there is conformal linearisation $h: U\to U$ such that $h(f(z))=\lambda h(z)$ on $U$ is called the **Siegel disk** of $f$. Else, the fixed point is called **Cremer**.

### References

<a name="fn1">1</a>: A. Katok, B. Hasselblatt. Introduction to the Modern Theory of Dynamical Systems. Encyclopedia of Mathematics and its Applications, volume 54. Cambridge University Press, Cambridge, 1995.  
<a name="fn2">2</a>: J. Milnor. Dynamics in one complex variable. Princeton University Press, third edition, 2006.    

------
