---
title: '6 Equivalent Ways of Defining Ergodicity'
date: 2022-02-06
permalink: /posts/2022/02/ergodicity/
tags:
  - Dynamical systems
---

In statistical mechanics, Boltzmann brought up the 'ergodic hypothesis' which states that over time, a system of $N$ particles will eventually find all its way to admit all accessible (constant energy) states (position and momentum). The hypothesis is known to be false. The property the system needs to satisfy in order to get the result that Boltzmann originally wanted (time averages = space averages) is now called ergodicity. Ergodic theory has been one of the key measure theoretic studies in the field of dynamical systems. In this post, I aim to introduce the modern formulation of ergodicity in discrete dynamical systems, outline a variety of ways of defining it, and provide simple examples.

Suppose we are given a measure space $(X, \mathcal{M},\mu)$. We say that a measurable self map $f: X \to X$ is invariant with respect to $\mu$, or that $\mu$ is $f$-invariant, if $\mu(f^{-1}(A)) = \mu(A)$ for every measurable set $A \in \mathcal{M}$.

**_Definition & Theorem:_** An invariant self map $f$ on a probability space $(X, \mathcal{M},\mu)$ is said to be ergodic if it satisfies any of the following equivalent definitions:
1. for any $A \in \mathcal{M}$, if $f^{-1}(A)=A$ , then $A$ has either zero or full measure: $\mu(A) \in \{0,1\}$;
2. for any $A \in \mathcal{M}$, if $\mu( f^{-1}(A) \triangle  A ) = 0$, then $A$ has either zero or full measure;
3. for any $A \in \mathcal{M}$ of positive measure, the backward orbit of $A$ has full measure: $\mu( \cup_{n=1}^\infty f^{-n}(A) ) = 1$;
4. for any $A,B \in \mathcal{M}$ of positive measure, $f^{-n} \cap B$ has positive measure for some $n\in \mathbb{N}$;
5. for any measurable function $g: X \to \mathbb{R}$, if $g \circ f = g$, then $g$ is constant almost everywhere;
6. for any $g \in L^p(X,\mu)$, if $g \circ f = g$ almost everywhere on $X$, then $g$ is constant almost everywhere.

The formal definition of ergodicity is usually taken to be 1, which states that there are no $f$-invariant proper subsets ($f^{-1}(A)=A$) up to measure zero. Whenever $X$ can be written as a disjoint union of two invariant measurable subsets $A_1$ and $A_2$, then either $A_1$ or $A_2$ has measure zero. I quite like the formulation of 3 as well, which essentially says that given any positive measure set $A$, almost every point $x$ on $X$ must admit some time $n$ at which $f^n(x)$ lands in $A$.

## Why are they equivalent?

We will show $1 \to 2 \to 3 \to 1$ and $2\to 5 \to 6 \to 1$ using very basic techniques in measure theory.

* 1 implies 2: Suppose $f^{-1}(A) \triangle  A$ has zero measure for some $A \in \mathcal{M}$. Since $f^{-n} \triangle  A$ is a subset of $\cup_{k=0}^{n-1} f^{-k}(f^{-1}(A) \triangle  A)$, the $f$-invariance of $\mu$ implies that $\mu(f^{-k}(A) \triangle  A) \leq n \mu(f^{-1}(A) \triangle  A) = 0$. For any $n \in \mathbb{N}$, $A \triangle  \cup_{k\geq n} f^{-k}(A)$ must also have zero measure as well. Therefore, the set $A_\infty = \cap_{n\geq 0} \cup_{k\geq n} f^{-k}(A)$ of points contained in infinitely many $f^{-n}(A)$'s satisfies $\mu(A_\infty \triangle  A) = 0$ and consequently $\mu(A) = \mu(A \cap A_\infty) = \mu(A_\infty)$. We also know that $A_\infty$ is $f$-invariant, so by property 1, $\mu(A) = \mu(A_\infty) \in \{0,1\}$.

* 2 implies 3: Suppose $A$ is a measurable set of positive measure. The backward orbit $C = \cup_{n=1}^\infty f^{-n}(A)$ contains $f^{-1}(C)$ by definition. By $f$-invariance of $\mu$, we have $\mu(f^{-1}(C)) = \mu(C)$ which implies $\mu(f^{-1}(C) \triangle  C) = \mu(C \backslash f^{-1}(C)) = 0$. By property 2, $C$ has to be of zero or full measure, but since $f^{-1}(A) \subset C$ has positive measure, $C$ must have full measure.

* 3 implies 4: Suppose $A$ and $B$ are measurable sets of positive measure. Since property 3 tells us that the backward orbit $C = \cup_{n=1}^\infty f^{-n}(A)$ has full measure, $0< \mu(B) = \mu(B \cap C) \leq \sum_{n=1}^\infty \mu(B \cap f^{-n}(A))$. Then, $B \cap f^{-n}(A)$ has positive measure for some positive integer $n$.

* 4 implies 1: Suppose $f$ is a measurable set with $0 < \mu(A) < 1$. Since the sets $A$ and $X \backslash A$ both have positive measure, property 4 implies that there is some integer $n\geq 1$ where $f^{-n}(A) \backslash A$ has positive measure. In particular, $f^{-1}(A) \neq A$.

* 2 implies 5: Suppose $g: X \to \mathbb{R}$ is a measurable function satisfying $g \circ f = g$ almost everywhere. Let's pick a scale $n \in \mathbb{N}$ and partition $X$ into $\cup_{k \in \mathbb{Z}} X_n(k)$ where $X_{n,k} = g^{-1}( [ 2^{-n}k, 2^{-n}(k+1)])$. Each symmetric difference $f^{-1}(X_{n,k}) \triangle  X_{n,k}$ has zero measure because every point $x$ lying on the symmetric difference $f^{-1}(X_{n,k}) \triangle  X_{n,k}$ must satisfy $g\circ f (x) \neq g(x)$. By property 2, $\mu(X_{n,k}) \in \{0,1\}$ for any $k \in \mathbb{Z}$. Then, for each $n$, there must be a unique integer $k_n \in \mathbb{Z}$ such that $X_{n,k_n}$ has full measure. Therefore, the set $\cap_{n\geq 1} X_{n,k}$ must have full measure, but on this set, the value of $g$ must be constant due to how we defined these $X_{n,k}$'s.

* 5 implies 6: This is trivial...

* 6 implies 1: Suppose $A$ is an invariant measurable set. Since $\chi_A \circ f = \chi_A$ everywhere, then $\chi_A$ is constant almost everywhere and $A$ must have either zero or full measure.

## Some examples

Any irrational rotation $R_\theta (x) = x + \theta$ of angle $\theta \not\in\mathbb{Q}$ on the unit circle $S^1 = \mathbb{R}/ \mathbb{Z}$ is ergodic with respect to the Lebesgue measure $\mu$. (In fact, $R_\theta$ is uniquely ergodic: the only $R_\theta$-invariant measure that is ergodic is the Lebesgue measure!) This is all thanks to the fact that the forward orbit of every point under $R_\theta$ is dense on $S^1$.

Ok, let's try to be more precise. Suppose $A$ is a $R_\theta$-invariant measurable subset of $S^1$. Pick any small $\epsilon >0$ and any continuous map $h : S^1 \to \mathbb{R}$ that $\epsilon$-approximates the indicator function $\chi_A$ of $A$, that is, $ \vert h - \chi_A \vert_{1} = \int_{S^1} \vert h - \chi_A \vert dx < \epsilon $.

Because $A$ is invariant under $R_\theta$, we also have that for any $n \in \mathbb{N}$, $\vert h(x+n\theta) - \chi_A(x) \vert_1 < \epsilon$ and thus $\| h(x+n\theta) - h(x) \|_1 < 2\epsilon $. By the density of $\{n\theta\}_{n\in \mathbb{N}}$ on $S^1$, we have the $\| h(x+y) - h(x)\|_1 < 2 \epsilon$ for any point $y \in S^1$. It then follows that $\| f - \int\_{S^1} f(t) dt \|_1 \leq 2\epsilon$ and

$$
\| \chi_A - \mu(A) \|_1 \leq \| \chi_A - f \|_1 + \| f - \int_{S^1} f(t) dt \|_1 + \| \int_{S^1} f(t) dt - \mu(B) \|_1 \leq 4 \epsilon.
$$

Taking $\epsilon \to 0$, it is clear that the indicator function $\chi_A(x)$ must be equal to the constant $\mu(B)$ almost everywhere. Therefore, $\mu(A)$ must be either $0$ or $1$.

In general, the toral translation $f(x_1, \ldots x_n) = (x_1 + \theta_1, \ldots x_n +\theta_n)$ on $\mathbb{R}^n / \mathbb{Z}^n$ is ergodic whenever the angles $\theta_1, \theta_n$ are rationally independent, that is, the only integer values $k_1 \ldots k_n$ such that $\sum_{i=1}^n k_i \theta_i$ is an integer is $k_1=\ldots =k_n = 0$.

In general, any $C^2$ diffeomorphism $f$ of $S^1$ with irrational rotation number $\tau(f) \not\in \mathbb{Q}$ has to be topologically conjugate to the irrational rotation $R_{\tau(f)}$ and therefore $f$ must ergodic with respect to the Lebesgue measure as well. (When $f$ is only $C^1$, further assumptions are needed to make things work. See this [post](/posts/2021/05/irrational-rotation-number) or the book<sup>[1](#fn1)</sup> by de Melo and van Strien for more details.)

Another example of an ergodic system is the standard degree $d \geq 2$ covering map $T_d(x) = dx$ mod $1$ on $S^1$ equipped with the Lebesgue measure $\mu$. The $T_d$-invariance of $\mu$ follows from the fact that the preimage of any interval $I \subset S^1$ of length $0\leq l \leq 1$ is a disjoint union of $d$ intervals of length $l/d$. There are multiple ways to show ergodicity. One can perform a similar analysis to that of the rotation example, but we will take a slightly different approach using Fourier analysis, which is another method commonly used in the subject. Suppose $g: S^1 \to \mathbb{R}$ is a bounded measurable function such that $g \circ T_d = g$. Take the Fourier expansion of $g$ and write it as $\sum_{k \in \mathbb{Z}} g_k e^{2 \pi i k x}$. Since $g$ must be an $L^1$ function, $\vert g_k \vert \to 0$ as $\vert k \vert \to \infty$. Moreover, the assumption that $g \circ T_d = g$ almost everywhere implies that $g_k = g_{dk}$ for all $k$. From here, it is clear that $g_k \equiv 0$ for all $k\neq 0$ and $g$ must be equal to the constant $g_0$ almost everywhere.

### References

<a name="fn1">1</a>: W. de Melo, S. van Strien. One-Dimensional Dynamics, Springer, 1993.  
<a name="fn2">2</a>: A. Katok, B. Hasselblatt. Introduction to the Modern Theory of Dynamical Systems. Encyclopedia of Mathematics and its Applications, volume 54. Cambridge University Press, Cambridge, 1995.  
<a name="fn3">3</a>: P. Walters. An Introduction To Ergodic Theory, Springer, NY, 1982.  
------
