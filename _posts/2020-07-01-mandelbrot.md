---
title: 'Mandelbrot'
date: 2020-07-01
permalink: /posts/2020/07/mandelbrot/
tags:
  - Complex analysis
  - Holomorphic dynamics
  - Dynamical systems
---

Beautiful images of the Mandelbrot set are ubiquitous. You might have seen them on featured in math textbooks for God knows what reason. They're probably on the posters of some of math professors in your college. You've probably seen some people wearing Mandelbrot set T-shirts or even having Mandelbrot tattoos. Rather than trying to explain its fame, I would like to firstly define this object and state its basic properties.

The Mandelbrot set is, first and foremost, a subset of the complex plane $\mathbb{C}$. Holly Krieger on numberphile gave a clear and pictorial definition.

<iframe src="https://www.youtube.com/watch?v=NGMRB4O922I">
</iframe>

Let's go through a brief summary of the video. Krieger defined the Mandelbrot set $\mathbb{M}$ as the set of complex parameters $c \in \mathbb{C}$ such that the sequence of iterates of the quadratic map $f_c(z) = z^2 +c$ for the initial value $0$ satisfies $|f^n_c(0)| \leq 2$ for all integers $n \geq 0$. Each iterate $f^n_c(0)$ is a polynomial of degree $2^{n-1}$ given by

$$
c, c^2 + c, (c^2 + c)^2 + c, \ldots
$$

If we let $P_n(c) = f^n_c(0)$, then the Mandelbrot set is defined as the countable intersection of preimages of the disk $\mathbb{D}_2$ of radius 2 centered at 0:

$$
\mathbb{M} = \bigcap_{n=1}^\infty P_n^{-1}(\mathbb{D}_2).
$$

Each of these preimages is non-empty and compact. By Cantor's intersection theorem, we can easily deduce that $\mathbb{M}$ is non-empty and compact. The countable intersection expression above also inspires a straightforward algorithm to produce an image of the Mandelbrot set, illustrated below.

<p align="center">
  <img src="/images/simplemandelbrot.gif" />
</p>

In the study of holomorphic dynamics, there are a few other equivalent ways of defining the Mandelbrot set.

> **_Proposition_** $c \in \mathbb{M}$ if and only if it satisfies any of the following equivalent conditions.
> 1. $|f^n_c(0)| \not\to \infty$ as $n \to \infty$;
> 2. The filled Julia set $K(f_c)$ of $f_c$ is connected.



### References

<a name="fn1">1</a>: A. Beardon. Iteration of Rational Functions. Grad. Texts Math. 132, Springer-Verlag, NY, 1984.  
<a name="fn2">2</a>: J. Milnor. Dynamics in one complex variable. Princeton University Press, third edition, 2006.  

------
