---
title: 'A geometric proof of Koebe 1/4 theorem'
date: 2021-04-10
permalink: /posts/2021/04/a-geometric-proof-of-koebe-quarter
tags:
  - Complex Analysis
---

The famous Koebe one-quarter theorem gives a sharp bound on the size of the image of univalent functions locally. The standard proof of this theorem which can be found in most complex analysis books (e.g. Rudin<sup>[1](#fn1)</sup> chapter 14) relies on the area theorem and s rather unnatural conformal change of variables. I found another proof of the theorem from the book of Hubbard<sup>[2](#fn2)</sup> which is, in my opinion, more fascinating and geometric, relying on covering spaces and conformal moduli.

Let's denote the open disk centered at $a \in \mathbb{C}$ of radius $r>0$ by $\mathbb{D}(a,r)$. The unit disk will be especially denoted by $\mathbb{D}$. We'd also denote the round annulus $\\\{ r < \vert z \vert < R \\\}$ as $\mathbb{A}(r,R)$.

> **_Koebe 1/4 Theorem:_** Let $f: \mathbb{D} \to \mathbb{C}$ be a univalent map. If $f(0)=0$ and $\vert f'(0)\vert =1$, then the image $f(\mathbb{D})$ contains the disk $\mathbb{D}(0,\frac{1}{4})$.

There are a few comments I would like to make.
* The constant $\frac{1}{4}$ is sharp. This value is achieved by the **Koebe function** $ K(z)=\frac{z}{(z-1)^2}$ which conformally maps $\mathbb{D}$ onto the slit plane $\mathbb{C}\backslash (-\infty,-\frac{1}{4}]$. In fact, this function serves as the extremal function in many other results in geometric function theory.
* By affine change of variables, the result can easily be generalised as follows: the image of any univalent map $f$ on a disk $\mathbb{D}(a,r)$ must contain the disk $\mathbb{D}(f(a), \frac{r}{4}\vert f'(a)\vert)$.

Let's go straight to the proof. Let $f: \mathbb{D} \to \mathbb{C}$ be a univalent map such that $f(0)=0$ and $\vert f'(0)\vert =1$. Define $g(z) := (1+\delta)f(z)$ for some arbitrarily small $\delta>0$, so that $g(0) = 0$ and $\vert g'(0) \vert > 1$. Let's assume for a contradiction that $g(\mathbb{D})$ does not contain some point $w$ in the circle $\\\{ \vert z \vert = \frac{1}{4}\\\}$.

As a rational map, the Koebe function $K(z)$ is a double branched covering map of the Riemann sphere $\mathbb{P}^1$ onto itself with critical points $\pm 1$ and critical values $K(1) = \infty$ and $K(-1)=-\frac{1}{4}$. The unique non-trivial deck transformation of this covering is $\frac{1}{z}$ since $K(\frac{1}{z}) \equiv K(z)$. By composition with some rotation, we can assume that $w=-\frac{1}{4}$, so that the image $g(\mathbb{D})$ of $g$ contains no critical values of $K$. We can then lift $g$ to two distinct meromorphic functions $g_0, g_{\infty} : \mathbb{D} \to \mathbb{P}$ such that $K \circ g_j = g$ and $g_j(0) = j$ for $j=\\\{0,\infty\\\}$. The two lifts are related by the equation $g_\infty = 1/g_0$ and their images are disjoint.

By Taylor series about $0$, we can deduce that for any $\epsilon >0$, for sufficiently small $r>0$, $g_0(\mathbb{D}(0,r))$ contains the disk $\mathbb{D}(0, r(1-\epsilon)\vert g'(0) \vert)$. Since $g_\infty = 1/g_0$, the image $g_\infty(\mathbb{D}(0,r))$ also contains the domain $\\\{ \vert z \vert > \frac{1}{r(1-\epsilon)\vert g'(0) \vert}  \\\}$. In overall, we can conclude that the (disjoint) annuli $A_j(\rho) := g_j(\mathbb{A}(r, 1))$, $j \in \\\{0,\infty\\\}$ are contained in the bigger annulus

$$
A := \mathbb{A} \left( r(1-\epsilon)\vert g'(0) \vert, \frac{1}{r(1-\epsilon)\vert g'(0) \vert}\right).
$$

At this point, we'd like to the family of curves joining the inner and outer boundary components of each of the annuli $A$, $A_0$ and $A_\infty$. (Look back at this [post](/posts/2020/09/extremal-length) for the theory of extremal lengths.) We calculate the moduli of each of these annuli:

$$
\text{mod}(A_0) = \text{mod}(A_\infty) = \frac{1}{2\pi} \log\frac{1}{r}, \quad \text{mod}(A) = \frac{1}{2\pi} \log\frac{1}{r^2}.
$$

By the series law, for the theory of extremal lengths), we have the inequality $\text{mod}(A_0) + \text{mod}(A_\infty) \leq \text{mod}(A)$ which then gives us:

$$
\frac{2}{2\pi} \log\frac{1}{r} \leq \frac{1}{2\pi} \log\frac{1}{r^2(1-\epsilon)^2\vert g'(0) \vert^2}.
$$

Upon simplification, we obtain the inequality $\vert g'(0) \vert \leq \frac{1}{1-\epsilon}$ for all small $\epsilon >0$. This implies $\vert g'(0) \vert \leq 1$, which is then a contradiction.

### References

<a name="fn1">1</a>: W. Rudin. Real and Complex Analysis. McGraw-Hill, Series in Higher Mathematics, 3rd edition, 1987.  
<a name="fn2">2</a>: J. H. Hubbard. Teichmüller Theory and Applications to Geometry, Topology, and Dynamics. Vol. 1. Matrix Editions, Ithaca, NY, 2nd edition, 2006.  

------
