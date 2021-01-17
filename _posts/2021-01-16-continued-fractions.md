---
title: 'Continued Fractions'
date: 2021-01-16
permalink: /posts/2021/01/continued-fractions
tags:
  - Number Theory
---

Irrational numbers are typically defined upon constructing the set $\mathbb{R}$ of real numbers from the set $\mathbb{Q}$ of rational numbers via either Cauchy sequences or Dedekind cuts. Decimal expansion has been used as the standard way of representing and approximating irrational numbers. However, it turns out that the best way to approximate irrational numbers is through continued fractions.

## Continued Fractions

A **continued fraction** expansion of a real number $\theta$ is of the form:

$$
[a_0;a_1,a_2,\ldots] = a_0 + \frac{1}{a_1 + \frac{1}{a_2 + \frac{1}{a_3 + \ldots}}}.
$$

for some positive integers $a_0, a_1, \ldots$. We can obtain the continued fraction expression for any $\theta \in \mathbb{R}$ through the following algorithm.
* Set $a_0 = \lfloor \theta \rfloor$, the highest integer less or equal to $\theta$, and $b_0 = \{\theta\} := \theta - a_0$, the fractional part of $\theta$;
* Inductively, for all $n \in \mathbb{N}$, $a_n = \bigl\lfloor \frac{1}{b_{n-1} \bigr\rfloor$ and $b_n = {\frac{1}{b_{n-1}}$.

If we ever obtain $b_k = 0$ for some $k \in \mathbb{N}$, then $\theta$ has a finite continued fraction expansion $[a_0; a_1, \ldots a_k]$. By the Euclidean algorithm, this happens precisely when $\theta$ is rational. In the rational case, the expansion is not unique because of the following identity:

$$
[a_0; a_1 \ldots a_k+1] = [a_0; a_1 \ldots a_k,1].
$$

Irrational numbers have infinite continued fractions uniquely determined by the algorithm. A natural question would be whether or not such an infinite expression converges. If so, at what rate? We begin by an obvious way of approximating $\theta =[a_0;a_1,a_2,\ldots]$ by the rational numbers $\frac{p_n}{q_n} = [a_0; a_1, \ldots a_n]$. By straightforward induction, $p_n$ and $q_n$ is determined by the following recurrence relation:

$$
p_n = a_n p_{n-1} + p_{n-2}, \qquad q_n = a_n q_{n-1} + q_{n-2},
$$

with initial values $q_{-1} = 0, p_{-1} = q_{0} = 1, p_0 = a_0$.

> **_Proposition:_** The rational numbers $\frac{p_n}{q_n}$ satisfy the following properties:
> 1. $\frac{p_{n+1}}{q_{n+1}} = \frac{p_n}{q_n} + \frac{(-1)^n}{q_n q_{n+1}}$;
> 2. $ \theta = a_0 + \sum_{n=0}^\infty \frac{(-1)^n}{q_n q_{n+1}}$.

Property 1 again follows from induction. (and it immediately implies that $p_n$ and $q_n$ are always coprime!) Property 2 follows directly from the first. Observe that $\frac{p_n}{q_n}$ for odd $n$ must be a decreasing sequence of rational numbers greater than $\theta$, whereas $\frac{p_n}{q_n}$ for even $n$ must be an increasing sequence of rational numbers smaller than $\theta$:

$$
\frac{p_0}{q_0} < \frac{p_2}{q_2} < \frac{p_4}{q_4} < \ldots < \theta < \ldots < \frac{p_5}{q_5} < \frac{p_3}{q_3} < \frac{p_1}{q_1}.
$$

It turns out that the rational numbers $\frac{p_n}{q_n}$ are best rational approximations (often also called best Diophantine approximations) of $\theta$ in the sense that for any rational number $\frac{p}{q}$, if $q_n \geq q$, then $\vert \theta - \frac{p_n}{q_n} \vert \leq \vert \theta - \frac{p}{q} \vert$. In fact, they satisfy an even stronger inequality.

> **_Theorem:_** For any rational number $\frac{p}{q}$, if $q_n \geq q$, then $\vert q_n\theta - p_n \vert \leq \vert q\theta - p \vert$.

By triangle inequality, property 2 also yields the following estimate

$$
\frac{1}{q_n(q_n+q_{n+1})} < \Big\vert \theta - \frac{p_n}{q_n} \Big\vert < \frac{1}{q_n q_{n+1}},
$$

which immediately implies the inequality $\vert q_n \theta - p_n \vert < \vert q_{n-1} \theta - p_{n-1} \vert$. By induction, it is sufficient to show the theorem under the additional assumption that $q_{n-1} < q \leq q_n$, $\text{hcf}(p,q)=1$, and $\frac{p}{q} \neq \frac{p_n}{q_n}$.

If $q = q_n$, then since $\vert q_n\theta - \frac{p_n} \vert < \frac{1}{q_{n+1}} < \frac{1}{2} $,

$$ \vert q\theta - p \vert \geq \vert p - p_n \vert - \vert q_n\theta - p_n \vert \geq 1 - \frac{1}{2} = \frac{1}{2} > \vert q_n\theta - p_n \vert.
$$

Suppose $q_{n-1} < q < q_n$. By property 1, the simultaneous equations

$$
a p_n + b p_{n-1} = p, \qquad a q_n + b q_{n-1} = q
$$

have a unique non-zero integral solution $a = (-1)^{n-1} (pq_{n-1} - q p_{n-1})$ and $b = (-1)^n ( p q_n - q p_n)$. Since $ q_{n-1} < a q_n + b q_{n-1} <q_n$, $a$ and $b$ must have opposite signs, so $a(q_n \theta - p_n)$ and $b(q_{n-1} \theta - p_{n-1})$ have the same sign. Therefore, we have our desired inequality:

$$
\vert q\theta - p \vert = \vert a(q_n \theta - p_n) + b(q_{n-1} \theta - p_{n-1}) \vert \geq \vert q_{n-1} \theta - p_{n-1} \vert > \vert q_{n} \theta - p_{n}.
$$

## Preperiodic Continued Fractions

An infinite continued fraction $\theta = [a_0; a_1, a_2, \ldots]$ is **preperiodic** if there are some $N,s \in \mathbb{N}$ such that $a_{n} = a_{n+s}$ whenever $n \geq N$. The minimum of such $s$ is called the **period** and the minimum of such $N$ is called the **preperiod**. Real numbers with preperiodic decimal expansion are precisely rational numbers, but the decimal expansion of irrationals follows no clear pattern. Analogously, we have the following theorem by Lagrange.

> **_Theorem:_** The continued fraction expansion of an irrational number $\theta$ is preperiodic if and only if $\theta$ is a quadratic irrational, i.e. can be written in the form of $\frac{a + b\sqrt{c}}{d}$ for some $a,b,c,d \in \mathbb{Z}$ where $c$ is square-free.

The proof is slightly more involved and can be found in the book of Hardy and Wright<sup>[1](#fn1)</sup>. Here is the continued fraction expansion of some of your favorite quadratic irrationals:
* $\frac{1+\sqrt{5}}{2} = [1;1,1,1,\ldots]$ (the golden ratio)
* $\sqrt{2} = [1;2,2,2,\ldots]$
* $\frac{\sqrt{3}}{2} = [0;1,6,2,6,2,6,2 \ldots]$

In comparison, the continued fraction expansion of the following irrationals are not preperiodic:
* $e = [2;1,2,1,1,4,1,1,6,1,1,8,1,1,10,\ldots]$
* $\pi = [3;7,15,1,292,1,1,2, \ldots]$

Let's assume for now that $a_0 = 0$. By induction, we can show from the basic properties of the $n$-th convergents $\frac{p_n}{q_n}$ of $\theta$ that the matrix

$$
A_n =
  \begin{pmatrix}
  a_n & -1\\
  -1 & 0
  \end{pmatrix} \ldots \begin{pmatrix}
  a_1 & -1\\
  -1 & 0
  \end{pmatrix} =
  \begin{pmatrix}
  q_n & -p_n\\
  -q_{n-1} & p_{n-1}
  \end{pmatrix}
$$

satisfies the following equation:

$$
A_n \begin{pmatrix}
\theta\\
1
\end{pmatrix} =
(-1)^n \theta_1 \ldots \theta_n \begin{pmatrix}
\theta_{n+1}\\
1
\end{pmatrix}.
$$

Suppose the continued fraction expansion of $\theta$ is preperiodic with period $s$ and preperiod $N$. When $n \geq N$,

$$
A_{n+s} \begin{pmatrix}
\theta\\
1
\end{pmatrix} =
(-1)^s \theta_1 \ldots \theta_s A_{n} \begin{pmatrix}
\theta\\
1
\end{pmatrix}.
$$

By looking at the first coordinate of the equation above, we see that the fractional parts $\vert q_n \theta - p_n \vert$ converge to zero at a fixed rate.

> **_Proposition:_** Let $\theta = [a_0;a_1,a_2,\ldots]$ be preperiodic of period $s$ and preperiod $N$. Let $\theta_n = \frac{p_n}{q_n}$ be the $n$-th convergent of $\theta$ and let $r = \prod_{k=1}^s \theta_k$. For all $n \geq N$, $\vert q_{n+s} \theta - p_{n+s} \vert = r \vert q_n \theta - p_n \vert$.

In particular, when the period is $s=1$, the fractional parts $\vert q_n \theta - p_n \vert $ eventually form a geometric sequence.

### References

<a name="fn1">1</a>: G. H. Hardy and E. M. Wright. An Introduction to the Theory of Numbers. Oxford University Press, 1979.  

---
