---
title: 'Orbifolds'
date: 2021-02-26
permalink: /posts/2021/02/orbifolds
tags:
  - Riemannian geometry
  - Topology
---

Earlier today, I gave a [talk](https://www.youtube.com/watch?v=AuHZgJ_k9os&t=4s) about orbifolds in SBU's graduate student math seminar and I was thinking it'd be a good time for me to write about them too. Orbifolds are a rather natural generalisation of manifolds especially if you are dealing with a lot of quotient spaces. Let's have a look at what they really are and what we can do with them.

Roughly speaking, an **orbifold** $O$ is a Hausdorff second countable topological space that is locally homeomorphic to $\mathbb{R}^n/\Gamma$ for some finite group $\Gamma$. In other words, $O$ admits an open covering $\\\{U_i\\\}$ and a collection of homeomorphisms $\phi_i : U_i \to V_i / \Gamma_i$ for some open set $V_i \subset \mathbb{R}^n$ and finite group $\Gamma_i$ acting on $V_i$. These local homeomorphisms must also satisfy certain gluing conditions. (Such conditions are rather lengthy and I will gladly recommend you to refer to Thurston's notes chapter 13<sup>[1](#fn1)</sup> on this.) We say that $O$ is a smooth orbifold if the local finite groups (and the local gluing maps) are acting smoothly, and a Riemannian orbifold if there are Riemannian metrics on the local charts invariant under the finite group action and if the finite groups (and the local gluing maps) are acting isometrically.

One of the main reasons for studying orbifolds is the following.

> **_Proposition:_** If $M$ is a smooth manifold and a group G acts smoothly and properly discontinuously on $M$, then $M/G$ is a smooth orbifold.

The idea of the proof of the proposition above goes along the following lines. Pick any $x \in M$ and denote the stabiliser subgroup of $G$ with respect to $x$ by $\Gamma_x$. Pick any neighbourhood $N_x$ that is invariant under the action of $\Gamma_x$ and disjoint from any $g(N_x)$ whenever $g \in G \backslash \Gamma_x$. The quotient map will project $N_x$ onto $N_x/\Gamma_x$, a neighbourhood of the corresponding orbit $\tilde{x} = G\cdot x \in M/G$ of $x$. By construction, the quotient space $M/G$ is therefore locally homeomorphic to $N_x/\Gamma_x$, a quotient of some Euclidean space by a finite group action, at $\tilde{x}$ in $M/G$.

We call the corresponding finite group $\Gamma_x$ at $x$ such that $O$ is locally homeomorphic to $\mathbb{R}^n/\Gamma_x$ the **isotropy group** of $O$ at $x$. In the context of the proposition above, the isotropy groups coincide with the stabilisers.  If the isotropy group $\Gamma_x$ is trivial, clearly $O$ is locally Euclidean at $x$; otherwise, we call $x$ a singularity. Let's look at some examples.
* If $G$ acts smoothly, freely and properly discontinuously on a smooth manifold $M$, then $M/G$ is a smooth manifold.
* The quotient $\mathbb{R}^2/C_n$ of the Euclidean plane by the group of rotations $C_n$ of order $n$ is a smooth orbifold. Topologically, this orbifold is an infinite cone with exactly one singularity, which we will call a cone point of order $n$.
* The quotient $\mathbb{R}^n/D_{2n}$ of the Euclidean plane by the dihedral group $D_{2n}$ is also a smooth orbifold. This orbifold is homeomorphic to a closed infinite sector and the singularities are the two boundary edges, which we will call mirror boundary lines (they are coming from the axes of reflections), and the unique point at which the two mirror lines meet, which we will call a corner reflector of order $n$.
* The quotient $\mathbb{T}^2/\text{Sym}_2$ of the 2-torus $\mathbb{T}^2 = S^1 \times S^1$ by the symmetric group $\text{Sym}_2 = \\\{ Id, (x,y) \mapsto (y,x)\\\}$ is a smooth orbifold. Topologically, it is a Mobius strip with mirror boundary.  
* The quotient $\mathbb{H}^2/Mod$ of the upper half plane $\mathbb{H}^2$ by the modular group
$$
Mod = \left\{ \frac{az+b}{cz+d} \: : \: \left( \begin{array}{cc}
      a & b \\
      c & d
    \end{array} \right) \in SL(2,\mathbb{Z}) \right\}
$$
is a smooth orbifold. This is the space of all complex structures on a 2-torus; it is homeomorphic to an open disk (or the sphere punctured at $\infty$) and the only singularities are two cone points of order $2$ and $3$ (arising from the point $i$ fixed by the hyperbolic rotation $-\frac{1}{z}$ of order $2$ and the point $e^{\pi i/3}$ fixed by the hyperbolic rotation $-\frac{1}{z+1}$ of order $3$).

Given an orbifold $O$ of dimension $n$, the isotropy group at any point $x \in O$ is an arbitrary finite group acting on a open subset of $\mathbb{R}^n$. We can in fact assume without loss of generality that each isotropy group is a subgroup of the orthogonal group $O(n)$ acting on $\mathbb{R}^n$.

> **_Proposition:_** Every orbifold $O$ is locally homeomorphic to $\mathbb{R}^n / \Gamma$ where $\Gamma$ is some finite subgroup of $O(n)$.

Indeed, suppose $O$ is locally homeomorphic to $V/G$ at $x \in O$, where $V$ is some open subset of $\mathbb{R}^n$ and $G$ is a finite group acting on $V$. Pick any Riemannian metric $\tilde{g}$ on $V$ (e.g. the usual Euclidean metric). The average $\hat{g} = \frac{1}{\vert G \vert} \sum_{\gamma \in G} \gamma^* \tilde{g}$ is a Riemannian metric on $V$ that is invariant under $G$. If we replace $V$ with some $\epsilon$-neighborhood of $\tilde{x} \in V$ (the point which projects to $x \in O$) with respect to the metric $\hat{g}$, then the exponential map would induce an isometry $\phi: V \to \mathbb{B}(0,\epsilon)$ with respect to the metrics $\hat{g}$ on $V$ and the Euclidean metric on the open ball $\mathbb{B}\_\epsilon$ of radius $\epsilon$ in $\mathbb{R}^n$. Since $G$ acts isometrically on $(V,\hat{g})$, the corresponding group $\Gamma = \phi G \phi^{-1}$ acts isometrically on $\mathbb{B}_\epsilon$, so $\Gamma$ is a finite subgroup of $O(n)$.

The proposition above gives us a clear idea to classify all the possible singularities allowed in an orbifold, which starts by listing out all finite subgroups of $O(n)$.

When $n=1$, the only non-trivial finite subgroup has order $2$ generated by reflection about the origin of $\mathbb{R}$. The quotient $\mathbb{R}/\\\{\pm Id\\\}$ is the closed infinite ray $[0,\infty)$ where the boundary point $0$ acts as a mirror point of the action. Thus, the only possible singularity in dimension $1$ is a mirror point. Clearly, every 1-orbifold must then be homeomorphic to a 1-manifold, possibly with boundary. Thus, every 1-orbifold is homeomorphic to one of the following: $\mathbb{R}, S^1, [0,\infty), [0,1]$. Any topological boundary points arise as mirror points of the orbifold.

When $n=2$, the only non-trivial finite subgroups are the cyclic group $C_n$ of order $n\geq 2$ and the dihedral group $D_{2n}$. From previous examples, we see that the only possible singularities in dimension $2$ are cone points (induced by $C_n$), corner reflectors and mirror boundaries (both induced by $D_{2n}$). In this case, every 2-orbifold is still homeomorphic to a 2-manifold, possibly with boundary. Every boundary component, if exists, is a CW complex of corner reflectors and mirror boundaries. In my next post, I will resume with an attempt to classify all possible 2-D orbifolds.

### References

<a name="fn1">1</a>: W. Thurston, Three-dimensional geometry and topology. Vol. 1. Edited by Silvio Levy. Princeton Mathematical Series, 35. Princeton University Press, Princeton, NJ, 1997.   

---
