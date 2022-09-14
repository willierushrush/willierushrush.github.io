---
title: 'Measurable Riemann mapping theorem'
date: 2020-11-07
permalink: /posts/2020/11/mrmt
tags:
  - Complex analysis
---

The measurable Riemann mapping theorem by Ahlfors & Bers remains one of the most fundamental results in the theory of quasiconformal maps. It states that there is a biholomorphic correspondence between quasiconformal maps (modulo post-composition with conformal isomorphisms) and their complex dilatations. I aim to discuss the theorem firstly on the unit disk and then on general Riemann surfaces.

Here, I would assume that you are already familiar with quasiconformal maps and their basic properties. (Else, refer to [here](/posts/2020/08/quasiconformal-maps) and then [here](/posts/2020/09/extremal-length).)

## Measurable Riemann Mapping theorem

> **_Theorem:_** For any function $\mu : U \to \mathbb{C}$ on with bounded essential supremum norm $\lVert \mu \rVert_{\infty} < 1$, there is a quasiconformal map $\phi$ on $U$ satisfying the Beltrami equation $\phi_{\bar{z}}=\mu \phi_{z}$ for almost all $z \in U$. Moreover, $\phi$ is unique up to post-composition with conformal isomorphisms and $\phi$ depends holomorphically on $\mu$.

Uniqueness guarantees a canonical choice of normalisation of the solution. For example, when $U = \mathbb{P}^1$, we can guarantee a unique solution $\phi$ fixing $0$, $1$ and $\infty$. Holomorphic dependence of the solution can be interpreted as follows. Whenever $\mu=\mu_\lambda$ is a holomorphic function in $\lambda$, the normalised solution $\phi = \phi_{\lambda}$ is holomorphic in $\lambda$.

Uniqueness of the solution follows from directly [Weyl's lemma](/posts/2020/09/extremal-length). When $\phi$ and $\psi$ are two solutions, then it is not difficult to show that $(\phi \circ \psi^{-1})_{ \bar{z} } = 0$ almost everywhere on $\psi(U)$, implying that $\phi \circ \psi^{-1}$ is a conformal isomorphism. The classical proof of the existence of solution relies on the analysis of the Cauchy transform

$$
C f(w) = \frac{1}{\pi w} * f(w) = -\frac{1}{\pi} \iint_{\mathbb{C}} \frac{ f(z) }{ z-w } dx dy,
$$

and the Beurling transform

$$
S f = \frac{1}{\pi w^2} * f(w) = \text{p.v.} \frac{1}{\pi} \iint_{\mathbb{C}} \frac{ f(z) }{ (z-w)^2 } dx dy.
$$

where $z=x+iy$. The Cauchy transform $C$ is a convolution operator with the fundamental solution $\frac{1}{\pi z}$ of the $\frac{\partial}{\partial z}$ differential operator. When $f$ is is compactly supported and continuously differentiable, we have the identities $(C f)_{\bar{z}} = f$ and $S f = (C f)_z$.

I'll sketch the proof in the case where $\mu$ is a continuously differentiable and compactly supported map on $U$ such that $\lVert \mu \rVert_{\infty} < 1$. Define the function $g = S\mu + S\mu S\mu + S\mu S\mu S\mu + \ldots$. This function is well-defined and is in $L^p$ for $p>2$ sufficiently close to $2$ once we show that the operator $f \mapsto S(\mu f)$ is a contraction in $L^p$. This map satisfies the equation $g = S(\mu g) + S\mu$.

Define $ \phi(z) = z + C(\mu g + \mu)(z)$. Clearly, $\phi$ is continuously differentiable satisfying the equation $\phi_{\bar{z}}=\mu \phi_{z}$ because the partial derivatives of $\phi$ are

$$
\phi_{\bar{z}} = \mu g + \mu, \qquad \phi_{z} = 1 + S(\mu g) + S\mu = 1 + g.
$$

The Cauchy transform is clearly holomorphic, i.e. if $f$ depends holomorphically on $\lambda$, then so is $Cf$. This gives holomorphic dependence of $\phi$ on $\mu$. It suffices to show that the solution $\phi$ is in fact a homeomorphism. I would personally recommend checking out the book by Ahlfors<sup>[1](#fn1)</sup>, chapter 5, or the book by Astala, Iwaniec, and Martin<sup>[2](#fn2)</sup>, chapter 5, for more details.

## Complex Structures

The same theorem also holds for any arbitrary Riemann surface $X$. Suppose the complex structure of $X$ is governed by a holomorphic atlas $\mathcal{H} = \{h_j : U_j \to \mathbb{D}\}$ for some open cover $\{U_j\}$ of $X$. We can define a **Beltrami form** $\mu$ on $X$ to be one where locally on each chart $\mu$ can be expressed as a measurable $(-1,1)$-form $\mu_i(z) \frac{d\bar{z}}{dz}$ satisfying $\lVert \mu_i \rVert_{\infty} < 1$.

On each chart, we have a solution $\phi_i : U_i \to \mathbb{D}$ of the Beltrami equation for $\mu$ on $U_i$, i.e. $\phi_i \circ h_i^{-1}$ are quasiconformal self maps of $\mathbb{D}$ with dilatation $\mu_i(z) \frac{d\bar{z}}{dz}$. Whenever $U_i \cap U_j$ is non-empty, $\phi_j \circ \phi_{i}^{-1} : \phi_i(U_i\cap U_j) \to \phi_j(U_i \cap U_j)$ is a conformal isomorphism as it must have zero complex dilatation almost everywhere. Therefore, $\{\phi_i\}$ glues together to form a holomorphic atlas $\mathcal{P}$ for $X$, inducing another complex structure for $X$. The identity map on $X$ induces a quasiconformal map $(X,\mathcal{H}) \to (X,\mathcal{P})$ integrating the Beltrami form $\mu$.

> **_Theorem:_** For every Beltrami form $\mu$ on a Riemann surface $X$, there is a Riemann surface $Y$ and a quasiconformal map $\phi : X \to Y$ integrating $\mu$. Moreover, $\phi$ is unique up to post-composition with conformal isomorphisms and it depends holomorphically on $\mu$.

When $X = (X, \mathcal{H})$ is the Riemann sphere $\mathbb{P}^1$, uniformisation theorem guarantees that the sphere $S^2$ admits only one complex structure. Therefore, there is a biholomorphism $\psi : (S^2, \mathcal{P}) \to \mathbb{P}^1$. As $\psi \circ \phi_i^{-1}$ is conformal on each $\phi_i(U_i)$, $\phi$ is a quasiconformal self map of $\mathbb{P}^1$. A common choice of normalisation in this case is one where the solution $\Phi$ fixes $0$, $1$ and $\infty$.

The measurable Riemann mapping theorem has plenty of applications in the field of holomorphic dynamics. It allows us dynamicists to really make use of the flexibility of quasiconformal maps and deform holomorphic functions in a pretty nice way. Branner and Fagella made an entire book<sup>[3](#fn3)</sup> on such applications, and I will cover some of these in future posts.

### References

<a name="fn1">1</a>: L. Ahlfors. Lectures on Quasiconformal Mappings. Van Nostrand, 1966.  
<a name="fn2">2</a>: K. Astala, T. Iwaniec, and G. Martin. Elliptic Partial Differential Equations and Quasiconformal Mappings in the Plane. Princeton University Press, 2008.  
<a name="fn3">3</a>: B. Branner, N. Fagella. Quasiconformal Surgery in Holomorphic Dynamics. Cambridge University Press, 2014.  


------
