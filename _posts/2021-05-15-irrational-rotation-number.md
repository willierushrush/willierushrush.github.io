---
title: 'Irrational Rotation number'
date: 2021-05-15
permalink: /posts/2021/05/irrational-rotation-number
tags:
  - Dynamical systems
---

This post is a continuation of the previous [post](/posts/2021/05/rotation-number) in which we discuss about circle homeomorphisms with rational rotation number. To complete the story of Poincaré's classification of circle homeomorphisms, I would like to cover the irrational case, which is split into two: either $f$ is conjugate to the irrational rotation $x+\tau(f)$ and the $\omega$-limit set of every point is $S^1$, or $f$ has an invariant Cantor set $C$ and the $\omega$-limit set of every point is $C$.

## Invariant set of $f$

The following lemma is crucial.

> **_Lemma:_** If $\tau(f) \not\in \mathbb{Q}$, then the forward orbit $\\\{ f^i(I) \\\}_{ i \in \mathbb{N} }$ of any non-degenerate closed interval $I$ of the form $[f^m(x), f^n(x)]$ for some $x \in S^1$ and $m,n \in \mathbb{Z}$ is a covering of $S^1$.

Indeed, suppose $S^1$ is not covered by the forward orbit of $I$ and assume $m>n$. Then, for every $i \in \mathbb{N}$, $f^{i(m-n)}(I)$ and $f^{(i+1)(m-n)}(I)$ share a common endpoint but have disjoint interiors. The sequence of intervals $\\\{ f^{i(m-n)}(I) \\\}\_{ i \in \mathbb{N}}$ must eventually accumulate at $z:= \lim_{i \to \infty} f^{i(m-n)(x)}$. However, this will imply that $z$ must be $m-n$ periodic, which contradicts irrationality of $\tau(f)$.

Pick any two points $x$ and $y$ on $S^1$ having two distinct orbits. Let $z \in \omega(x)$, so there is some sequence $m_i \to \infty$ such that $f^{n_i}(x) \to z$. Applying the lemma to each interval $[ f^{n_i}(x) , f^{n_{i+1}} (x) ]$, we have a sequence $n_i \to \infty$ such that each $f^{n_i}(y)$ lies in this interval. This forces the sequence $f^{n_i}(y)$ to converge to $z$. In particular, $z \in \omega(y)$. Therefore, we always have $\omega(x)=\omega(y)$.

Let's denote the invariant set $\omega(x)$ by $C$. As $S^1$ is compact, so is $C$. By definition, the set $C$ must be also perfect (i.e. all points are accumulation points) because if $x \in C = \omega(x)$, we can always find iterates $f^{m_j}(x) \in \omega(x)$ converging to $x$.

Recall that any compact perfect metrisable space is a Cantor set if it is totally disconnected. Therefore, we need to show that $C$ must be either the whole $S^1$ or totally disconnected. Suppose $C$ is not totally disconnected, so it contains some open interval $I$. Then, $I$ must contain some closed interval $I'$ of the form $[f^m(x), f^n(x)]$ for some $x \in S^1$ and $m,n \mathbb{Z}$. By invariance of $E$, the forward orbit of $I'$ must be contained in $E$, but due to the lemma, $E$ must then be the whole $S^1$.

## Constructing the (semi-)conjugacy

We wish to define a surjective continuous self map $h$ on $S^1$ such that $h\circ f = h + \tau(f)$ on $S^1$. This kind of map is often called semiconjugacy. It is a conjugacy if additionally $h$ is injective.

We start by letting $h(f^n(0))=n\tau(f)$ (mod $1$) for all $n$. We claim that $h$ is monotone on the orbit $\\\{ f^n(0) \\\}_{n \in \mathbb{N}}$ of $0$ and therefore extends continuously to a map from $D$, the closure of the orbit of $0$, onto $S^1$ (since any orbit under irrational rotation is dense). By monotonicity, we can also uniquely continuously extend $h$ to the whole $S^1$ by letting it be constant on each connected component of the complement of $B$. If $E=S^1$, then $h$ is a homeomorphism conjugating $f$ with $x\mapsto x+\tau(f)$. In the Cantor case, $h$ can be thought as a map which blows down / collapses every interval in the set $S^1\backslash C$ into points.

We are left to show the monotonicity of $h$ is true. We can resort to the number one method we always use in this topic, namely lifting $f$ to the homeomorphism $F$ on the real line $\mathbb{R}$ (as seen in [here](/posts/2021/05/rotation-number)). Suppose $f^n(0) < f^m(0)$ for some integers $m$ and $n$, so then $F^n(0) - ⌊F^n(0)⌋ <  F^m(0) - ⌊F^m(0)⌋$.

1. For any $x \in \mathbb{R}$, $F^n(x) - ⌊F^n(x)⌋ <  F^m(x) - ⌊F^m(x)⌋$ too, for if otherwise, by intermediate value theorem, there must be some $x$ satisfying $F^n(x) - ⌊F^n(x)⌋ = F^m(x) - ⌊F^m(x)⌋$ but this would imply that $x$ is a periodic point.

2. We can rearrange the inequality to obtain

$$
F^{n-m}(0) = F^n(0) - F^m(0) < ⌊F^n(0)⌋ - ⌊F^m(0)⌋.
$$

By induction, we can show that $F^{k(n-m)}(0) < k ( ⌊F^n(0)⌋ - ⌊F^m(0)⌋ )$ and therefore,

$$
\tau(f) = \lim_{k\to \infty} \frac{F^{k(n-m)}(0)}{k(n-m)} < \frac{⌊F^n(0)⌋ - ⌊F^m(0)⌋}{n-m}.
$$

which can be reformulated as $n\tau(f) - ⌊F^n(0)⌋ < m\tau(f) - ⌊F^m(0)⌋$, i.e. $n\tau(f)<m\tau(f)$ (mod 1). As such, $h$ must be monotone.


### References

<a name="fn1">1</a>: W. de Melo, S. van Strien. One-Dimensional Dynamics, Springer, 1993.  
<a name="fn2">2</a>: A. Katok, B. Hasselblatt. Introduction to the Modern Theory of Dynamical Systems. Encyclopedia of Mathematics and its Applications, volume 54. Cambridge University Press, Cambridge, 1995.  

------
