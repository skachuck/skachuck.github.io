---
layout: mathpost
---

I was asked to use the time to practice writing down Lagrangians for systems, so we proposed the following problems.
1. The toy in pediatricians' offices across the country, where a small wooden block slides (we'll assume frictionlessly, though they often have disappointingly large friction) along a wire bent into a circular helix.
2. A spring suspended from the roof of a train car going at a constant velocity $v$
    a. At first the problem seems upsettingly easy, but...
    b. what happens when the mass is accidentally displaced a small bit from the vertical?

## Wooden block on circular helix
There are two parts to writing down a Lagrangian $\mathcal{L}$ - choosing a suitable set of generalized coordinates, and then writing down the kinetic and potential energies in terms of those coordinates only. It helps to start (as with so many problems) by defining an origin and drawing a position vector to all the points of interest. In this problem, there's just one point of interest: the location of the mass $m$. It's most general position vector is written $\mathbf{r} = x\hat{\mathbf{x}} + y\hat{\mathbf{y}} + z\hat{\mathbf{z}}$. Now there's this funny constraint that the particle is forced to reside along a wire. This restricts the particle's motion to a one-dimensional line, so we should be able to identify a single generalized coordinate.

The circular helix is defined by a radius $r$ and a spacing between coils $h$, which we'll assume is constant because that one kid hasn't gotten to this toy yet. The position vector can be expressed
$$\mathbf{r} = r\cos\theta\hat{\mathbf{x}} + r\sin\theta\hat{\mathbf{y}} + \frac{h}{2\pi}\theta\hat{\mathbf{z}}$$.
With this in hand, we can differentiate to find the general velocity
$$\dot{\mathbff{r}}=\left[-r\sin\theta\hat{\mathbf{x}} + r\cos\theta\hat{\mathbf{y}} + \frac{h}{2\pi}\hat{\mathbf{z}}\right]\dot{\theta}$$.
Thus the kinetic energy $T=\frac{1}{2}m\dot{\mathbf{r}}^2 = \frac{1}{2}m\left[r^2 + \left(\frac{h}{2\pi}\right)^2$
The potential can be expressed $V=mgz=\frac{mgh}{2\pit}\theta$. Putting these together, the Lagrangian is
$$\mathcal{L}=T-V = \frac{1}{2}m\left[r^2 + \left(\frac{h}{2\pi}\right)^2 - \frac{mgh}{2\pit}\theta.$$

Using the Euler-Lagrange equation, 
$$\frac{d}{dt}\frac{\partial\mathcal{L}}{\partial\dot{\theta}} - \frac{\partial\mathcal{L}}{\partial\theta}=0,$$
we determine the equation of motion to be
$$\ddot{\theta}=\frac{g\left(\frac{h}{2\pi}\right)}{\left[r^2 + \frac{h^2}{(2\pi)^2}\right]}.$$

Follow-on questions:
1. Are there any conserved quantities pertaining to this Lagrangian? What are they?
