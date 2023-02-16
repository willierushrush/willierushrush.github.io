---
title: 'Thoughts on my first paper'
date: 2023-05-31
permalink: /posts/2023/05/my-first-paper
tags:
  - Graduate student life
---

I am finally done with my first paper, and it is now out on arXiv!

## What is it on?

One-dimensional holomorphic dynamics. This means that I study the iteration of holomorphic functions, in particular rational maps $f: \hat{\mathbb{C}} \to \hat{\mathbb{C}}$ acting on the Riemann sphere $\hat{\mathbb{C}}$. In my paper, I am looking at two problems.

Firstly, recall from the classical [classification of Fatou components](/posts/2021/11/classification-of-fatou-components) that a maximal domain $U$ in which a rational map $f$ is conjugate to a rotation is either simply connected, in which we call $U$ a _Siegel disk_, or double connected, in which we call $U$ a _Herman ring_. The Herman ring is special in the sense that it has a natural deformation space associated to it. Roughly speaking, we can stretch it and vary its conformal [modulus](/posts/2020/09/extremal-length); doing so gives a different rational map with essentially the conformal dynamics outside the iterated preimages of the Herman ring. The problem is as follows: what is the limit of a deformed Herman ring as we take its modulus to shrink to zero?

Secondly, this is somewhat a related problem that can be posed separately. I introduced the term _Herman curve_ (suggested by my advisor Dima) to denote an invariant Jordan curve $X$ of a rational map $f$ such that $f: X \to X$ is conjugate to an irrational rotation and $H$ is not contained in the closure of a Siegel disk nor a Herman ring. The first examples of Herman curves that we know are round circles; we can find these in Blaschke products, which automatically preserve the unit circle. The problem is as follows: do there exist rational maps having Herman curves that are not round circles?

The paper answers the two questions above partially. I restrict the study to rotation numbers $\theta$ that are of _bounded type_, i.e. the [continued fraction](/posts/2021/01/continued-fractions) expansion $[0; a_1,a_2,\ldots]$ of $\theta$ has a uniform bound $B\geq \sup_{i \in \mathbb{N}} a_i$. In this class of rotation numbers, the boundary of any Herman ring $H$ with bounded type rotation number is always a pair of [quasicircles](/posts/2021/12/quasicircles) with dilatation depending only on $B$, the degree of $f$, and the modulus of $H$. The bulk of the work is to show that assuming the dynamics of $f$ outside of $H$ is 'simple', $H$ has _a priori bounds_: the dilatation of the boundary of $H$ is in fact independent of the modulus. This implies that when we deform $H$ such that its modulus shrinks to zero, there is a limiting rational map of the same degree and the associated limit of degenerating Herman rings is in fact a Herman quasicircle! This geometric limit construction allows arbitrary degree and combinatorics, and in particular it produces Herman curves that are not round circles in general.

If you happen to be interested in any of these things that I have been discussing, I gave a recorded [talk](https://www.youtube.com/watch?v=c-gUa7KJucY) at IMPAN, Poland, and also a [poster](https://impa.br/wp-content/uploads/2022/11/Poster-Willie-Rush-Lim-nova-versao-poster-rio-2160-3840.pdf) session at IMPA, Brazil. Check them out, and feel free to ask me any questions!

## Thoughts and tips

Having more than 50 pages, this paper is rather long. The research process started in the beginning of 2021, and by the end of the same year, I had a lot of things written and they just had to be compiled together. I finished writing a full draft of the paper in March 2022. From then until now, there has been many little things added, including lemmas within long proofs of some small theorems, figures, and even a new, albeit fairly short, section. Throughout the editing process, I might have probably read through the whole manuscript more than twenty times.

I found this [guide](http://www.math.uchicago.edu/~may/VIGRE/VIGRE2010/piiUJM2up.pdf) by Steven Kleiman to be very useful. However, I will point out a few tips, based on my experience, on writing a paper.
1. Once you have results, you should try to write them down somewhere as soon as possible. Revisiting something you have done in a (somewhat) distant past may take more work.   
2. Once you think your results are ready to be compiled to form a paper, then start writing the paper! I personally think that the introduction should always be written first. The introduction should tell a story without any technical details conveying how the results fit in the larger field of mathematics you are working on. Why are you writing this paper? Why did the author bother spending a long time writing it? What is the main theorem? Why should the reader be interested in the problem? Is this related to anything anyone has done in the past? The introduction is the first thing any reader, be it an expert or a graduate student, would read and you would want to leave a mark to them regardless of whether or not they will read past the introduction.   
3. Reread what you have written, and if you think that there are some parts that are ambiguous or missing, do the repair. Sometimes you may think that your proof is a little too long. If you tried shortening it to no avail, consider breaking it down into a number of lemmas or claims, or adding some diagrams. These little changes help navigate readers in the course of your proof.   
4. Be patient. Send your manuscript to your advisor and some of your colleagues. Ask what they think and use the feedback to make the paper even better. Take a break from it for a week or two. Reread and judge your manuscript yourself with a more refreshed point of view. Repeat until you are 1000% pleased with your manuscript.
