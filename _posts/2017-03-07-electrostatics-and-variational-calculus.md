---
layout: mathpost
---

# Variational Calculus and Electrostatics
We have used variational calculus in the course to determine what functionals obey certain fundamental physical rules (i.e., minimum time, minimum action). The process has almost always required the use of integration by parts. In this problem, we'll see how integration by parts generalizes to vector quantities and use this to determine the form of the scalar electric potential that minimizes the field's energy.

## Integration by Parts
Integration by parts is the flip side of the product rule. The product rule says that, when differentiating a function, which is the product of two other functions $a(x)$ and $b(x)$, I can differentiate piecemeal

$$
\frac{d}{dx}(ab) = \frac{da}{dx}b + a\frac{db}{dx}.
$$

Now, if I have a integrand of the form $\frac{da}{dx}{dx}$,

$$
I=\int_{x_0}^{x_1}\frac{da}{dx}bdx,
$$

I can change the object of differentiation if I find it convenient to do so. Substituting from the product rule,

$$
\begin{align}
I &= \int_{x_0}^{x_1}\left[\frac{d}{dx}(ab) - a\frac{db}{dx}\right]dx\\
&=\int_{x_0}^{x_1}\frac{d}{dx}(ab)dx - \int_{x_0}^{x_1}a\frac{db}{dx}dx.
\end{align}
$$

The first term is a total differential, so it integrates immediately:

$$
I = \left.(ab)\right|_{x_0}^{x_1} - \oint_{x_0}^{x_1}a\frac{db}{dx}dx.
$$

To make the extension to vector equations, we'll focus on functions that can be written $a\nabla b$ and prove Green's First Theorem, by way of the divergence theorem. Remember, the divergence theorem is a statement of the integral of a complete divergence over a volume is controlled by it's behavior on the surface of the volume:

$$
\int_V \nabla\cdot(a\nabla b)d^3x = \int_s (a\nabla b)\cdot \mathbf{n}d^2x.
$$

Using this, determine 

## Electric potential
The electric field $\mathbf{E}(\mathbf{x})$ can be written as the gradient of a potential $\mathbf{E}=\nabla\psi(\mathbf{x})$, and it's energy can be written as a functional of the potential:

$$
I[\psi]=\frac{1}{2}\int_V(\nabla\psi\cdot\nabla\psi) d^3x - \int_V\rho\psi d^3x.
$$

The first term on the right hand side is the familiar definition of the electric field energy, and the second term is the interaction term between the field and any electric charge densities $\rho$  in the volume $V$ of interest. Note that $\rho$ is the charge densities in approripate units $\rho=\rho_0/\epsilon_0$. Let's investigate what potential $\psi$ minimizes this energy.

The problem proceeds using variational calculus of the energy with respect to potential fields. That is, start by assuming $\psi^*$ minimizes the energy, and perturb it slightly $\psi = \psi^\star + \delta\psi$. Expand the energy to first order terms in $\delta\psi$ and proceed to the condition of minimization on the field $\psi^\star$.

Does it seem familiar?
