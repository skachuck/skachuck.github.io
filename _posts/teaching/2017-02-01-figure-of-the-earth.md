---
layout: mathpost
title:  "Figure of the Earth"
date:   2017-02-01 11:42:44 -0500
type: teaching
categories: 3318 classmech history
course: 'PHYS3318: Classical Mechanics'
---
The year is 1735 and two expeditions have just left France to determine the shape of the Earth, one to Peru and the other to Lapland. Two theories lead to contradictory results. The French Cartesians compute, using DeCartes' theory of space-filling vortices, that the Earth should be _prolate_. The British, following Newton determine the Earth should be _oblate_. An earlier measurement to the north and south of Paris had confirmed the Cartesian result (side question: what was the measurement they were taking?), but still the French Academy is being infiltrated by Newtonians, and King Louis XIV was willing to fund a larger expedition to demonstrate the dominance of French scientists. We want to generate a theoretical prediction for the Earth's departure from a sphere so that we have something to compare with the expeditions' results.

Newton prepared a prediction, but we suspect he may be off. But we have the benefit of Christiaan Huygens' elucidation of a strange consequence of the Earth's rotation - that the magnitude of the acceleration felt by objects depends on latitude. Through private communication, he's provided us with some expressions.

Our preparation will progress as follows:
1. Starting from the centrifugal acceleration

$$
\frac{\vec{F}_\text{cent}}{m} = -\vec{\omega}\times(\vec{\omega}\times\vec{r}),
$$

derive an expression for the centrifugal potential $\chi$ such that

$$
-\vec{\nabla}\chi = \frac{\vec{F}_\text{cent}}{m},
$$

2. Combine this potential with Newton's gravitational potential on an oblate spheroid to generate an expression for the polar flattening, and
3. Using our best estimates of the Earth's physical parameters, estimate the magnitude of the flattening.

## 1. Centrifugal Potential
To develop the centrifugal potential, we have several approaches available to us. Since we know the geometry of the problem (we're on the surface of a near-sphere), we can evaluate the cross products in the centrifugal acceleration. Taking $\vec{\omega}$ (the Earth's rotation) to be along the $\hat{z}$ axis and a radius vector $\vec{r}$ from the center of the Earth to a point on it's surface at colatitude $\theta$ to be in the $x$-$z$ plane, $\vec{\omega}\times\vec{r} = \omega r \sin\theta\hat{y}$. Thus,

$$
\frac{\vec{F}_\text{cent}}{m} = r \omega^2\sin(\theta) \hat{x}
$$

or in spherical coordinates,

$$
= r\omega^2\sin\theta(\sin\theta \hat{r} + \cos\theta\hat{\theta}).
$$

The function $\chi$ whose gradient is that vector is, by a little inspection and some playing around,

$$
\chi = -\frac{\omega^2 r^2}{2}\sin^2\theta = -\frac{\omega^2r^2}{3}\left[1-P_2(\cos\theta)\right].
$$

Note that

$$
P_2(x) = \frac{1}{2}(3x^2 - 1)
$$

is the second Legendre polynomial, a class of polynomials that show up a lot when working in spherical coordinates.

## 2. Gravtiational Balacne
For an Earth flattened by a small amount $\epsilon \equiv \frac{a-c}{a}$, some careful integration of Newton's universal inverse-square law indicates a gravitational potential of

$$
\Phi_g\simeq-\frac{GM}{r}\left[1 + \frac{4}{15}P_2(\cos\theta) + \mathcal{O}(\epsilon^2)\right].
$$

In the above, $\mathcal{O}(\epsilon^2)$ means that this approximation is only good to first order $\epsilon^$, however, because I'm assuming $\epsilon\ll1$, these higher-order terms are unnecessary (it's good practice to check this afterward).

At the surface, for an equilibrium shape to exist, the centrifugal acceleration must be balanced by another force, in this case gravity. Another way of phrasing this is that the surface is an equipotential, which means $\Phi_g + \chi = c$, where we are free to set $c=0$. Doing this and comparing terms, we discover

$$
\epsilon = \frac{5}{4}\frac{\omega^2r^3}{GM},
$$

## 3. 
And using values appropriate for the Earth, $\epsilon = 1/233$. Indeed this number is adequately less than 1 to have ignored the higher order terms.

Jumping back to the present to use the most recent geodetic data (e.g., the GRACE satellite, which measures the Earth's gravity), we can pull out the order-2 bulge and find $\epsilon = 1/298.26$. What are some reasons for our overestimated bulging?
