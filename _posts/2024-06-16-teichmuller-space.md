---
title: '5 equivalent ways of defining Teichmüller Spaces'
date: 2024-06-16
permalink: /posts/2024/06/teichmuller-spaces
tags:
  - Riemann surfaces
  - Complex analysis
---

(It's summer 2024 and I haven't been writing anything meaningful in this blog in the last two years. I would like to think that graduate school and research in general has been keeping me busy for a while... but now that my graduate school era is over, there is no more excuse!) I have been thinking about Teichmüller spaces. What exactly are they? How are they relevant? Why should I care about it? Well, there are many questions you can ask, but let me just try to answer the first one here.

Let me provide a little background. Every surface $S$ (let's say smooth oriented $2$-dimensional manifold) admits a complex structure. One can say that this follows from Newlander-Nirenberg theorem and the vanishing of the Nijenhuis tensor. Alternatively, you can pick a Riemannian metric $g$ on $S$ and show that $S$ admits isothermal coordinates, i.e. choice of local coordinates $(x,y)$ such that $g$ locally looks like $\phi(x,y) (dx^2+dy^2)$ for some smooth function $\phi$. In isothermal coordinates, transition functions are conformal (locally angle-preserving), hence it induces a conformal structure, which is the same as a complex structure on $S$. It is natural to ask what the space of complex structures on $S$ looks like. This gives rise to the notion of moduli space of a Riemann surfaces. Often, studying the moduli space amounts to studying its universal cover, which is isomorphic to the Teichmüller space $\text{Teich}(S)$ of $S$. The existence of a natural complex structure and the richness of metric structures and compactifications of $\text{Teich}(S)$ are at the heart of Teichmüller theory.

In this post, we will discuss five different yet equivalent ways of defining the Teichmüller space $\text{Teich}(S)$ of a surface $S$. We will assume that $S$ is a genus $g \geq 2$ compact surface. (By the uniformization theorem, the moduli space of a non-hyperbolic Riemann surface is easy to describe. The notion of $\text{Teich}(S)$ when $S$ is non-compact, e.g. has punctures and boundary, can be generalized fairly easily, although there are a few technical subtleties...) Any homeomorphisms between surfaces are assumed to preserve orientation.

## Via complex structures

Complex structures on $S$ can be formulated as follows. Denote by $\text{Cplx}(S)$ the set of pairs $(Y,f)$ such that $Y$ is a Riemann surface and $f:S \to Y$ is a diffeomorphism.  Each element of $\text{Cplx}(S)$ is often called a marking. We then consider the equivalence relation $\sim$ on $\text{Cplx}(S)$ where $(Y,f) \sim (Z,g)$ if and only if $g \circ f^{-1}$ is homotopic to a biholomorphism $X \to Y$. (Here, homotopy can be replaced with isotopy. This is something very special in two dimensions!)

> **_Definition 1:_** The Teichmüller space of $S$ is the set of homotopy classes of marked complex structures on $S$:
$$
\text{Teich}(S) = \text{Cplx}(S)/\sim.
$$

## Via hyperbolic structures

The uniformization theorem states that given any genus $g$ compact Riemann surface $X$ is biholomorphic to the quotient space $\mathbb{H}/\Gamma$ where $\mathbb{H}$ is the upper half plane in $\mathbb{C}$ and $\Gamma$ is a **Fuchsian group**, i.e. a discrete group of automorphisms of $\mathbb{H}$ (hence a subgroup of $\text{PSL}(2,\mathbb{R})$). Since automorphisms of $\mathbb{H}$ preserve the hyperbolic metric of $\mathbb{H}$, they are simply isometries! Therefore, isomorphism classes of Riemann surfaces homeomorphic to $S$ correspond to isomorphism classes of hyperbolic surfaces homeomorphic to $S$. The first definition can then be rewritten as follows.

Let $\text{Hyp}(S)$ denote the set of pairs $(f,Y)$ such that $Y$ is a compact surface equipped with a hyperbolic metric of constant curvature $-1$ and $f:S \to Y$ is a diffeomorphism. We write $(f,Y) \sim (g,Z)$ if $g \circ f^{-1}:Y \to Z$ is homotopic to an isometry $Y \to Z$.

> **_Definition 2:_** The Teichmüller space of $S$ is the set of homotopy classes of marked hyperbolic structures on $S$:
$$
\text{Teich}(S) = \text{Hyp}(S)/\sim.
$$

## Via representation theory

Let $\pi_1$ denote the fundamental group of $S$. One can consider the representation variety $\mathcal{R}(S) = \text{Hom}(\pi_1, \text{PSL}(2,\mathbb{R}))$ consisting of group homomorphisms $\rho : \pi_1 \to \text{PSL}(2,\mathbb{R})$. In practice, we only consider the subspace $\mathcal{R}^{df}(S)$ consisting of representations $\rho$ which are injective (faithful) and have a discrete image, so that $\rho(\pi_1)$ is a Fuchsian group. Then, each $\rho$ in $\mathcal{R}^{df}(S)$ gives rise to a compact Riemann surface $\mathbb{H}/\rho(\pi_1)$.

The group $\text{PSL}(2,\mathbb{R})$ acts on $\mathcal{R}^{df}(S)$ by conjugation: $(h * \rho)(\gamma) = h \rho(\gamma) h^{-1}$. Of course, given any $\rho \in \mathcal{R}^{df}(S)$ and any $h \in \text{PSL}(2,\mathbb{R})$, the Riemann surfaces induced by $\rho$ and $h*\rho$ are isomorphic.

> **_Definition 3:_** The Teichmüller space of $S$ is the conjugacy classes of $\mathcal{R}^{df}(S)$:
$$
\text{Teich}(S) = \mathcal{R}^{df}(S)/\text{PSL}(2,\mathbb{R}).
$$

With this definition, one can easily work out the dimension of $\text{Teich}(S)$ (assuming that we already know it is a real manifold). As $\mathcal{R}^{df}(S)$ is an open subspace of $\mathcal{R}(S)$, let us first consider the dimension of $\mathcal{R}(S)$. The fundamental group $\pi_1$ naturally has $2g$ generators $\gamma_1$, $\gamma_2$, $\ldots$, $\gamma_{2g}$ and one relation:

$$
[\gamma_1, \gamma_2] [\gamma_3, \gamma_4] \ldots [\gamma_{2g-1}, \gamma_{2g}] = 1.
$$

Each $\rho \in \mathcal{R}(S)$ is determined by the elements $\rho(\gamma_i)$ for $1\leq i \leq 2g$, although based on the relation, $\rho(\gamma_{2g})$ can be written in terms of $\rho(\gamma_i)$'s for $1\leq i \leq 2g-1$. For each $i \in \{1,\ldots,2g-1\}$, $\rho(\gamma_i)$ is an element of $\text{PSL}(2,\mathbb{R})$, which is a Lie group with real dimension $3$. Since we are counting conjugacy classes under the action of $\text{PSL}(2,\mathbb{R})$, this further cuts down the dimension by $3$. In total, $\text{Teich}(S)$ has real dimension

$$
\text{dim}(\text{Teich}(S)) = 3 (2g-1) - 3 = 6g - 6.
$$

## Via quasiconformal deformations

From the discussion above, it is clear that a diffeomorphism between two surfaces $S$ and $S'$ induces a bijection between the corresponding Teichmüller spaces. In particular, we can select a representative Riemann surface $X = \mathbb{H}/\Gamma$ and so there is a bijection between $\text{Teich}(X)$ and $\text{Teich}(S)$.

To make sense of deformations of Riemann surfaces, we often deal with maps which are close to being conformal up to some bounded constant. We say that a homeomorphism $f: Y \to Z$ between Riemann surfaces is $K$-quasiconformal if for almost every point $y$ in $Y$, $Df_y$ sends the unit circle in the tangent space $T_{y} Y$ into an ellipse of eccentricity uniformly bounded by the constant $K\geq 1$. (See this [post](/post/2020/08/quasiconformal) for alternative and more precise definitions.) If $f$ is $1$-quasiconformal, it sends infinitesimal circles to circles, and a lemma by [Weyl](/posts/2020/09/extremal-length) states that it is therefore a conformal isomorphism. If the bound $K$ is not specified, we simply call $f$ quasiconformal.

Let's define the deformation space $\text{Def}(X)$ of $X$ to be the equivalence classes of pairs $(f,Y)$ where $f: X \to Y$ is a quasiconformal map between Riemann surfaces and any two pairs $(f,Y)$ and $(g,Z)$ are equivalent when $g\circ f^{-1} : Y \to Z$ is a conformal isomorphism. Then, consider $\text{QC}_0(X)$, the space of self quasiconformal maps $h: X \to X$ of $X$ which are isotopic to the identity map; it is in fact a group and it acts on $\text{Def}(X)$ by: $h * (f,Y) = (f \circ h^{-1}, Y)$.

> **_Definition 4:_** The Teichmüller space of $X$ is quotient space
$$
\text{Teich}(X) = \text{Def}(X)/\text{QC}_0(X).
$$

Quasiconformal maps are very flexible; for example, piecewise linear maps are quasiconformal. The isotopy class of homeomorphisms between two Riemann surfaces always contains quasiconformal maps. For this reason, homeomorphisms in Definition 1 can be assumed to be quasiconformal and we arrive at Definition 4.

## Via Beltrami differentials

A Beltrami form $\mu$ on $X$ is a measurable $(-1,1)$ form on $X$ with $L^\infty$ norm less than $1$. In local coordinates, $\mu$ can be written as $\mu(z) \frac{d\bar{z}}{dz}$ where $\mu(z)$ is a measurable function with absolute value less than $1$ almost everywhere. Let's denote by $\mathcal{B}_1(X)$ the space of Beltrami forms on $X$.

Beltrami forms encode how the complex structure of $X$ can be deformed. Given a quasiconformal map $f: X \to Y$, there is a unique Beltrami differential $\mu_f$ in $\mathcal{B}_1(X)$ such that $\bar{\partial} f = \mu_f \partial f$. (See this [post](/posts/2020/11/mrmt) for details!) The measurable Riemann mapping theorem by Ahlfors & Bers states that for every Beltrami form $\mu \in \mathcal{B}_1(X)$, there exists a Riemann surface $X^\mu$ and a quasiconformal map $f^{\mu}: X \to X^\mu$ such that $\mu = \mu_f$, and $f^\mu$ is unique up to post-composition with a conformal automorphism of $X^\mu$.

Now, every $\mu \in \mathcal{B}_1(X)$ can be lifted to a Beltrami form $\hat{\mu}$ on the upper half plane $\mathbb{H}$ by the universal covering, and we can extend $\hat{\mu}$ to the lower half plane $-\mathbb{H}$ such that it satisfies the equation $\mu(\bar{z}) = \overline{\mu(z)}$. As the measurable Riemann mapping theorem is applied, we obtain a quasiconformal map $F^{\mu}: \mathbb{C} \to \mathbb{C}$ which can be normalized to fix $0$ and $1$. By symmetry, $F^{\mu}$ preserves the upper and lower half planes respectively. Since $\hat{\mu}$ is constructed by lifting, it is equivariant with respect to the Fuchsian group $\Gamma$ and so $\Gamma^{\mu} := \{ F^\mu \circ \gamma \circ (F^\mu)^{-1} \: : \: \gamma \in \Gamma\}$ is again a Fuchsian group. The quotient $\mathbb{H}/\Gamma^{\mu}$ is precisely the Riemann surface $X^{\mu}$!

Let's say that two Beltrami forms $\mu_1$ and $\mu_2$ in $\mathcal{B}_1(X)$ are equivalent ($\mu_1 \sim \mu_2$) if the corresponding quasiconformal maps $F^{\mu_1}$ and $F^{\mu_2}$ agree on the real line: $F^{\mu_1}\|\_{\mathbb{R}} \equiv F^{\mu_2}\|\_{\mathbb{R}}$.

> **_Definition 5:_** The Teichmüller space of $X$ is the quotient space
$$
\text{Teich}(X) = \mathcal{B}_1(X)/\sim.
$$

To see the significance of this equivalence between two Beltrami forms $\mu_1$ and $\mu_2$, let's suppose that the resulting deformed Riemann surface $Y$ is the same, i.e. $Y = X^{\mu_1} = X^{\mu_2}$, and that there is an isotopy $h_t: X\to Y$, $0\leq t \leq 1$, between the quasiconformal maps $f^{\mu_1}: X \to Y$ and $f^{\mu_2}: X \to Y$. This lifts to an isotopy $H_t : \mathbb{C} \to \mathbb{C}$ between $F^{\mu_1}$ and $F^{\mu_2}$, and $H_t$ conjugates $\Gamma$ to a covering group $\Gamma'$ of $Y=\mathbb{H}/\Gamma'$, that is, $H_t \circ \Gamma \circ H_t^{-1} = \Gamma'$ for all $t$. Actually, since $\Gamma'$ is discrete, for every $\gamma \in \Gamma$, there is a unique Möbius transformation $\gamma' \in \Gamma$ such that $H_t \circ \gamma \circ H_t^{-1} = \gamma'$. From here, we see that $F^{\mu_2} \circ (F^{\mu_1})^{-1}$ commutes with every element of $\Gamma$ and in particular fixes every fixed point of elements of $\Gamma$. As a Fuchsian group, the set of fixed points of elements of $\Gamma$ accumulates on the real line (in other words, the limit set of $\Gamma$ is $\mathbb{R} \cup \{\infty\}$), so then $F^{\mu_2} \circ (F^{\mu_1})^{-1}(x) = x$ for all $x \in \mathbb{R}$. This implies that $\mu_1$ is equivalent to $\mu_2$.

### References
<a name="fn1">1</a>: L. Ahlfors. Lectures on Quasiconformal Mappings. Van Nostrand, 1966.   
<a name="fn2">2</a>: B. Farb, D. Margalit. A Primer on Mapping Class Groups. Princeton University Press, 2012.   
<a name="fn2">3</a>: F. Gardiner and N. Lakic. Quasiconformal Teichmüller Theory, vol. 76 of Mathematical Surveys and Monographs. AMS, 2000.   
<a name="fn2">4</a>: J. H. Hubbard. Teichmüller Theory and Applications to Geometry, Topology, and Dynamics. Vol. 1. Matrix Editions, Ithaca, NY, 2nd edition, 2006.  
<a name="fn3">5</a>: C. McMullen, D. Sullivan. Quasiconformal homeomorphisms and dynamics III. The Teichmüller space of a holomorphic dynamical system. Adv. Math., 135(2):351–395, 1998.   

------
