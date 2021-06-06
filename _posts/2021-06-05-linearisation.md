---
title: 'Local Analytic Linearisation'
date: 2021-05-15
permalink: /posts/2021/05/irrational-rotation-number
tags:
  - Dynamical systems
  - Holomorphic dynamics
---

Given a dynamical system $f: X \to X$ with a fixed point $x \in X$, what can we say about the dynamical behaviour of $f$ near $x$? For many sufficiently smooth functions $f$, the behaviour of $f$ near $x$ is governed by its linear approximation $Df_x$. More precisely, $f$ is conjugate to $Df_x$ when the derivative $Df_x$ is hyperbolic, i.e. has no eigenvalue with absolute value $1$. Proving local linearisability can be a rather daunting task, requiring a rather involved theory of hyperbolic systems, I would like to discuss the baby problem of local linearisability of analytic functions of 1 variable in this post.

## Real case

> **_Theorem:_** Let $f$ be a real analytic map on $I=[-\delta,\delta]$ such that $f(0)=0$ and $f'(0) = \lambda \not \in \\\{0, \pm 1 \\\}$. There is an real analytic diffeomorphism $h : J \subset I \to K$ for some neighbourhoods $J$ and $K$ of $0$ such that $h\circ f (x) = \lambda h(x)$ for all $x \in J$. Moreover, $h$ is unique up to scalar multiplication by a non-zero real number.

There is a reason why we exclude the values $0$ and $\pm 1$. If the theorem holds for value $0$ or $1$, then $h\circ f \circ h^{-1}$ is either the zero map or the identity map and clearly the only possible $f$ that can satisfy this is either the zero map or the constant map. For $-1$, we consider the second iterate $f^2$ which leads us back to the $1$ case.

It turns out we can find $h$ by brute force. Let $f(x) = \lambda x + \sum_{n\geq 2} a_n x^n$ be the MacLaurin series for $f$. We shall find coefficients $b_n$ such that $h(x) = \sum_{n\geq 1} b_n x^n$ is the desired diffeomorphism. At this point, observe that if $h(x)$ is the solution to the functional equation $h \circ f(x) = \lambda h(x)$, then $\tau h(x)$ is also another solution for any $\tau \neq 0$. As such, we can assume that $b_1 = 1$. The functional equation can be rewritten as:

$$
\left( \lambda x + \sum_{n \geq 2}^\infty a_n x^n \right) + \sum_{m\geq 2} b_m \left( \lambda x + \sum_{n \geq 2}^\infty a_n x^n \right)^m = \lambda x + \sum_{n \geq 2} \lambda b_n x^n.
$$

We can determine the coefficients $b_n$ inductively by comparing the coefficients of $x^n$. The first few $b_n$'s are as follows:

$$
b_2 = \frac{a_2}{\lambda-\lambda^n}, \quad b_3 = \frac{a_3 + b_2(2\lambda a_2)}{\lambda - \lambda^3}, \quad b_4 = \frac{a_4 +b_2 (a_2^2 + 2\lambda a_3) + b_3 (3\lambda^2 a_2)}{\lambda - \lambda^4}.
$$

To show that $h(x)$ converges on some neighbourhood $J$ of $0$, we need to obtain an upper bound $M>0$ for all $\vert b_n \vert$ 's and apply Abel's theorem.

## Complex case

> **_Theorem:_** Let $f$ be a holomorphic map on a neighbourhood $U \subset \mathbb{C}$ of $0$ such that $f(0)=0$ and $f'(0)=\lambda$ where $\vert \lambda \vert \neq 0,1$. There is a conformal isomorphism $h : V \subset U \to W$ for some neighbourhoods $V$ and $W$ of $0$ such that $h \circ f (z) = \lambda h(z)$ for all $z \in V$.



### References

<a name="fn1">1</a>: A. Beardon. Iteration of Rational Functions. Grad. Texts Math. 132, Springer-Verlag, NY, 1984.  
<a name="fn2">2</a>: J. Milnor. Dynamics in one complex variable. Princeton University Press, third edition, 2006.   

------
