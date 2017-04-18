---
layout: mathpost
title:  "Perihelion Precession and the Method of Successive Approximations"
date:   2017-04-18 11:42:44 -0500
categories: jekyll update
---

# Perihelion Precession and the Method of Successive Approximations

We would like to compute the magnitude of the precession of the perihelion. In Homework 10, problem one, you'll do it one way, so here we'll do it using the _method of successive approximations_. First, let's remind ourselves of the problem. We have the effective potential for motion in gravity, and we add a term proportional to $1/r^3$

$$
U(r) = \frac{B}{r^2} - \frac{A}{r} - \frac{C}{r^3},
$$

with

$$\begin{align}
A&=GM_1M_2 & B&=\frac{L_z^2}{2\mu} & C&=?
\end{align}$$

What could $C$ be? $C$ looks almost like it could be a term that interacts the $A$ and $B$ terms. If we posit that $C\sim AB$, what do we need to get the units right? (It will help to think about which theory would link an $A$-like thing and a $B$-like thing).

This is a bit fast and loose, but general relativity links gravity ($A$) and motion ($B$), and since we're off by a unit of energy, let's choose the rest mass energy of one of the masses! In fact, the first order theory agrees and gives

$$
C=\frac{2AB}{M_2 c^2}.
$$

In fact a perturbation of exactly this sort is [expected from general relativity](https://en.wikipedia.org/wiki/Two-body_problem_in_general_relativity#Effective_radial_potential_energy) and provided one of the earliest confirmations of the theory, by [measuring the precession of the perihelion of Mercury](https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.19.361).

To solve this a different way from class, we'll consider the equation of motion for the new parameter $u=1/r$. Using this change, we can update equation of motion (from lecture 31)

$$\tag{31.13}
\frac{d^2u}{d\theta^2} + u = \frac{A}{2B}
$$

using the same method. We write the new addition to the energy as $Cu^3$, which has derivative $3Cu^2\frac{dU}{d\theta}$. Thus we expect

$$
\frac{d^2u}{d\theta^2} + u = \frac{A}{2B} + \frac{3C}{2B}u^2.
$$

$C$ is going to be small, so let's figure out what it does to the orbits to first order.

How shall we solve this? We'll use the _method of successive approximation_. The procedure is as follows:
[1] Pick a first guess $u_0$ that solves the unperturbed differential equation.
[2] Substitute this into the right hand side of the perturbed equation.
[3] Figure out what you need to add to your initial guess so that the new guess $u_1=u_0+f$ satisfies new perturbed right hand side.
[4] Repeat until you get cool physics.
For this problem, we only need to do this once.

For our first solution, we want the version that allows eccentric ($\epsilon$) orbits, hence

$$\begin{align}\tag{31.20}
u_0(\theta)&=\frac{1}{r(\theta)}=\frac{1}{r_0}(1+\epsilon\cos(\theta-\theta_0)), & r_0&=\frac{2B}{A}.
\end{align}$$

This solves the unperturbed differential equation

$$
\frac{d^2u_0}{d\theta^2} + u_0 = \frac{1}{r_0}
$$

(c.f. lecture notes).

Plugging this in to the perturbed right-hand side (and letting $\gamma=\frac{3C}{2B}$), we see that

$$
\frac{d^2u}{d\theta^2} + u = \frac{1}{r_0} + \frac{\gamma}{r_0^2}(1+2\epsilon\cos(\theta-\theta_0) + \epsilon^2\cos^2(\theta-\theta_0)),
$$

which, using the double-angle formula, implies

$$
\frac{d^2u}{d\theta^2} + u = \frac{1}{r_0} + \frac{\gamma}{r_0^2}(1+2\epsilon\cos(\theta-\theta_0) + \frac{\epsilon^2}{2}(1+\cos2(\theta-\theta_0))).
$$


Which term could be responsible for secular changes in the orbit?

The only term that could grow orbit-to-orbit and cause long-term changes is the one with a period that resonates with the existing orbit. That's the $\cos(\theta-\theta_0)$ term. The others only modify the unperturbed orbit slightly. Our method compels us to write

$$
u_1 = u_0 + u_\textrm{constant} + u_\textrm{precession} + u_\textrm{shape perturbation},
$$

where each new addition to $u_0$ comes from the respective term on the right-hand side. If we wanted to go to another order in our approximation, we would need to solve each one to be able to plug the full $u_1$ into the right-hand side and start again. That is, find the $u_\textrm{constant}$ that solves

$$
\frac{d^2u_\textrm{constant}}{d\theta^2} + u_\textrm{constant} = \frac{\gamma}{r_0^2}\left(1+\frac{\epsilon^2}{2}\right),
$$

and so on. But since we are only interested in the one piece of physics (that causes the angle of the perihelion to precess), we'll focus on that one. We need to find $u_\textrm{precession}$ that solves

$$
\frac{d^2u_\textrm{precession}}{d\theta^2} + u_\textrm{precession} = \frac{2\gamma\epsilon}{r_0^2}\cos(\theta-\theta_0).
$$

Remembering that

$$
\frac{d^2u}{d\theta^2} + u = D\cos\theta
$$

is solved by

$$
u=\frac{1}{2}A\theta\sin\theta,
$$

we set

$$
u_1 = u_0 + \frac{\gamma\epsilon}{r_0^2}\sin(\theta-\theta_0) = \frac{1}{r_0}\left(1 + \epsilon\cos(\theta-\theta_0) + \frac{\gamma\epsilon}{r_0}\sin(\theta-\theta_0)\right).
$$


Our goal now is to find by how much the perihelion $\theta_0$ precesses, which would be much easier if we could right our perturbed solution as

$$
u_1 = \frac{1}{r_0}(1+\epsilon\cos(\theta-\theta_0-\delta\theta)).
$$

Expanding this expression in small $\delta\theta$,

$$
u_1 \approx\frac{1}{r_0}\left[1+\epsilon\cos(\theta-\theta_0) + \delta\theta\epsilon\sin(\theta-\theta_0)
\right].
$$

Comparing terms in the expansion,

$$
\delta\theta=\frac{\gamma}{r_0}\theta.
$$

Therefore, after a full revolution, the perihelion has shifted by $\frac{2\pi\gamma}{r_0}$. Plugging in for the constants, 

$$
\Delta\theta_0 = 2\pi\frac{A}{2B}\frac{3C}{2B} =6\pi\frac{(GM_1M_2)^2}{c^2L_z^2}
$$

Since we can write $L_z^2=\mu GM_1M_2r_0(1-\epsilon^2)$ and taking $M_1\gg M_2$ so that $\mu\approx M_2$,

$$
\Delta\theta_0 = 6\pi\frac{GM_1}{c^2r_0(1-\epsilon^2)}.
$$

Check this against your solution in problem 1 of homework 10!