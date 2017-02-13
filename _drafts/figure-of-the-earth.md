---
layout: mathpost
title:  "Figure of the Earth"
date:   2017-02-06 11:42:44 -0500
categories: jekyll update
---
In 1735 two expeditions left France to determine the shape of the Earth, one to Peru and the other to Lapland. Two theories led to contradictory results. The French Cartesians computed, using their theory of space-filling vortices, that the Earth should be _prolate_. The British, following Newton and ... determined the Earth should be _oblate_.

We are going to prepare a theoretical prediction of the Earth's flattening to compare the results of the experiment.

Our preparation will proceed as follows:
1. Use Huygens' centrifugal potential
2. Blah

Starting from the centrifugal acceleration
\\[
\frac{\vec{F}_\text{cent}}{m} = -\vec{\omega}\times(\vec{\omega}\times\vec{r}),
\\]

derive an expression for the centrifual potential \\(\chi\\) such that

\\[
-\vec{\nabla}\chi = \frac{\vec{F}_\text{cent}}{m}.
\\]


For an Earth flattened by a small amount \\(\epsilon \equiv \frac{a-c}{a}\\), the gravitational potential is
\\[
\Phi_g\simeq-\frac{GM}{r}\left[1 + \frac{4}{15}P_2(\cos\theta) + \mathcal{O}(\epsilon^2)\right].
\\]
In the above, \\(\mathcal{O}(\epsilon^2)\\) means that this approximation is only good to first order $\epsilon^$, however, because I'm assuming \\(\epsilon\ll1\\), these higher-order terms are unnecessary (it's good practice to check this afterward). Additionally,
\\[
P_2(x) = \frac{1}{2}(3x^2 - 1)
\\]
is the second Legendre polynomial, a class of polynomials that show up a lot when working in spherical coordinates.

To develop the centrifugal potential, we have several approaches available to us. Since we know the geometry of the problem (we're on the surface of a near-sphere), we can evaluate the cross products in the centrifugal acceleration. Taking \\(\vec{\omega}\\) (the Earth's rotation) to be along the \\(\hat{z}\\) axis and a radius vector \\(\vec{r}\\) from the center of the Earth to a point on it's surface at colatitude \\(\theta\\) to be in the x-z plane, \\(\vec{\omega}\times\vec{r} = \omega r \sin\theta\hat{y}\\). Thus,
\\[
\frac{\vec{F}_\text{cent}}{m} = r \omega^2\sin(\theta) \hat{x}
\\]
or in spherical coordinates,
\\[
= r\omega^2\sin\theta(\sin\theta \hat{r} + \cos\theta\hat{\theta}).
\\]
The function \\(\chi\\) whose gradient is that vector is, by a little inspection and some playing around,
\\[
\chi = -\frac{\omega^2 r^2}{2}\sin^2\theta = -\frac{\omega^2r^2}{3}\left[1-P_2(\cos\theta)\right].
\\]

At the surface, for an equilibrium shape to exist, the centrifugal acceleration must be balanced by another force, in this case gravity. Another way of phrasing this is that the surface is an equipotential, which means \\(\Phi_g + \chi = c\\), where we are free to set \\(c=0\\). Doing this and comparing terms, we discover
\\[
\epsilon = \frac{5}{4}\frac{\omega^2r^3}{GM},
\\]
And using values appropriate for the Earth, \\(\epsilon = 1/233\\).

Using the most recent geodetic data (e.g., the GRACE satellite, which measures the Earth's gravity), we can pull out the order-2 bulge and find \\(\epsilon = 1/298.26\\).
