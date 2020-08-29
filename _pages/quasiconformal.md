---
title: 'Quasiconformal maps'
date: 2020-08-29
permalink: /quasiconformal-maps
tags:
  - Complex Analysis
---

Conformal mappings are often too rigid for us to use. We know that Riemann mappings, for example, are unique up to conformal automorphisms of the unit disk -- the set of which forms a topological group homeomorphic to $S^1 \times \mathbb{D}$. In complex analysis, we often need maps which are more flexible and in many cases, what we are looking for are quasiconformal maps.

Throughout this post, we are only interested in orientation preserving homeomorphisms $f: U \to V$ between two open subsets $U$ and $V$ of $\mathbb{C}$.

## C^1 $K$-quasiconformal maps

When $f=u+iv$ is $C^1$, its Jacobian $Jf$ must be positive. In terms of partial derivatives,

$$
Jf = u_x v_y - u_y v_x =  \vert f_z \vert^2 -  \vert f_\bar{z} \vert^2 > 0
$$

and so we must have the inequality $ \vert f_z \vert  >  \vert f_\bar{z} \vert $. We define the **complex dilatation** $\mu_f$ on $U$ to be $\mu_f(z) = \frac{f_\bar{z}(z)}{f_z (z)}$. Its values must lie in the unit disk $\mathbb{D}$.

Applying triangle inequality to the one-form $df = f_z dz + f_{\bar{z}} d\bar{z}$,

$$
(1- \vert \mu \vert )  \vert f_z \vert   \vert dz \vert  \leq  \vert df \vert  \leq (1+ \vert \mu \vert )  \vert f_z \vert   \vert dz \vert .
$$

We then see that in general, the image under $f$ of the unit circle on the tangent space $T_z U$ is an ellipse of on the tangent space $T_{f(z)} V$. The eccentricity $D_f(z)$ of the ellipse, i.e. the ratio of the major axis to the minor axis, is given by:

$$
D_f(z) = \frac{1+ \vert \mu \vert }{1- \vert \mu \vert } \geq 1.
$$

We say that a $C^1$ map $f: U \to V$ is **$K$-quasiconformal** if $D_f$ is uniformly bounded above on $U$ by some constant $K\geq 1$. If so, the constant $K$ is called the **dilatation** of $f$. This definition is indeed a generalisation of conformal maps because when $K=1$, then $f_{\bar{z}} \equiv 0$. Another geometric interpretation to quasiconformal maps is the following. While conformal maps preserve angle locally, quasiconformal maps distort angles locally up to some factor depending on $K$.

One easy example is the following. For any real constant $a$, the shear transformation

$$
f(x+iy) = x+ay+iy = \left( \frac{2-ai}{2} \right)z + \frac{ai}{2} \bar{z}.
$$

is an $\mathbb{R}$-linear diffeomorphism from $\mathbb{C}$ onto itself. Its complex dilatation is the constant value $\frac{ai}{2-ai}$ and so $f$ is a $K$-quasiconformal map where $K = \frac{\sqrt{a^2 + 4} + a}{\sqrt{a^2+4}-a}$.

## $K$-quasiconformal maps

Sometimes, $C^1$ is still too rigid. We can relax the regularity of $f$ and say that $f$ is **$K$-quasiconformal** if there is a constant $K\geq 1$ such that
* locally, $f$ is absolutely continuous along almost every horizontal and vertical line,
* $D_f(z) \leq K$ almost everywhere on $U$.

The second criterion is very much similar to the $C^1$ case. The first criterion is often called ACL(absolutely continuous on lines) and it simply states that $x \mapsto f(x+iy)$ (resp. $y \mapsto f(x+iy)$) is differentiable almost everywhere and satisfies the fundamental theorem of calculus for almost all $y$ (resp. $x$). With more careful analysis, we can show that $f$ must be (real) differentiable almost everywhere. (Refer to Ahlfors.)

It is natural to ask whether quasiconformality is preserved under composition and inversion. The answer is yes. In the $C^1$ case, we can show the following.

> **_Proposition:_** The composition of a $C^1$ $K$-quasiconformal map and a $C^1 $L$-quasiconformal map is $KL$-quasiconformal. The inverse of a $C^1$ $K$-quasiconformal map is again $K$-quasiconformal.

The proof of the above very much relies on complex chain rule. In the general case, it is rather difficult to show that the composition or the inverse are ACL to begin with. To avoid the use of heavy analysis, many prefer using a more geometric definition of quasiconformal maps.

A topological quadrilateral $Q = (Q,a_1,a_2,a_3,a_4)$ is a Jordan disk in $\C$ equipped with four vertices $a_i$ for $i=1,2,3,4$ lying on the boundary $\partial Q$ and labelled cyclically in a counterclockwise manner. Every quadrilateral $Q$ admits a unique positive number $m>0$ and biholomorphism $\phi : Q \to \\{ x+iy \: \vert \: 0 < x < m, 0 < y < 1 \\}$ such that $\phi$ maps the vertices $(a_1,a_2,a_3,a_4)$ to the tuple $(0,m,m+i,i)$. The **(conformal) modulus** $\text{mod}(Q)$ of $Q$ is the side length $m$.

I think it is clear from the definition that the modulus of a quadrilateral is invariant under conformal maps, i.e. $\text{mod} f(Q) = \text{mod} Q$ if $f$ is conformal on a neighbourhood of $\overline{Q}$. Quasiconformal maps distort moduli up to some bounded constant; in fact, this can be taken as a geometric definition. (Refer to Ahlfors<sup>[1](#fn1)</sup>. If you do so, notice that I am trying hard to avoid using the term 'extremal length'.)

> **_Theorem:_** An orientation preserving homeomorphism $f: U \to V$ between two open subsets $U$ and $V$ of $\mathbb{C}$ is $K$-quasiconformal if and only if for every quadrilateral $Q$ in $U$,
>
>$$
\frac{\text{mod}Q}{K} \leq \text{mod} f(Q) \leq K \text{mod}Q.
$$

As a consequence, it is clear that the inverse of a $K$-quasiconformal map is $K$-quasiconformal and the composition of a $K_1$-quasiconformal map with an $K_2$-quasiconformal map is $K_1 K_2$-quasiconformal.

### References

<a name="fn1">1</a>: L. Ahlfors. Lectures on Quasiconformal Mappings. Van Nostrand, 1966.  

------
