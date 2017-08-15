---
layout: mathpost
type: teaching
categories: classmech 3318 math
course: 'PHYS3318: Classical Mechanics' 
---

With the Hamiltonian interpretation of dynamics as flow and transformations in phase space, we're beginning to see the geometric underpinnings of physics. Let's probe this connection a bit and explore a topic from the homework assignment, the _Poisson Bracket_. The Poisson Bracket in phase space has the following defintion:
$$
\{A, B\}=\sum_k\left(\frac{\partial A}{\partial q_k}\frac{\partial B}{\partial p_k} - \frac{\partial B}{\partial q_k}\frac{\partial A}{\partial p_k}\right).$$

## Infinitessimal generators of transformations
For a general function of the generalized coordinates and momenta $A=A(\mathbf{q},\mathbf{p})$, let's imagine how it changes under infinitessimal transformations $A\to A+\delta A$. You'll be exploring in class and the homework the nature of some of these transformations, but for now let's accept that we can write $\delta A$ in reference to the Poisson bracket as $\delta A=-\\\{\delta G, A\\\}$, where $\delta G$ is called the infinitessimal generator of the transformation. Let's derive some concrete examples of these $\delta G$.

### Generator of translations
First, consider a translation of everything in our space. How does our physics change and what could generate the change? To answer this, let's see what happens to an infinitessimal translation in $A$, i.e., $A(\mathbf{q}+\mathbf{\varepsilon}, \mathbf{p})$. As always, the first step is to expand to first order in the small bit.

$$
A(\mathbf{q}+\mathbf{\varepsilon},\mathbf{p}) = A(\mathbf{q}, \mathbf{p}) + \varepsilon_i\frac{\partial A}{\partial q_i}$$

We're looking to extract something that looks like a Poisson bracket, so let's insert an identity $\frac{\partial p}{\partial p}$ and add in zero $\frac{\partial p}{\partial q}$.

$$= A(\mathbf{q},\mathbf{p}) + \frac{(\varepsilon_i p_i)}{\partial p_i}\frac{\partial A}{\partial q_i} - \frac{\partial A}{\partial p_i}\frac{\partial(\varepsilon_i p_i)}{\partial q_i}$$

But there's the Poisson bracket we were looking for:

$$= A(\mathbf{q},\mathbf{p}) - \{\varepsilon_i p_i, A\}.$$

Comparing this to the form above, we see that $\delta G=\delta p_i$. Thus we may say that the generator of infinitessimal translations is the momentum "operator" (to borrow some language from quantum mechanics).

### Infinitessimal generator of rotations
This exercise is a little more challenging, because writing down the infinitessimal transformation is a bit more involved. As before, we want to know how our function of interest changes when we rotate it's consituents $A(R_{ij}q_j,R_{ij}p_j)$. Expanding this in an small quantity requires us to recall the rotation transformation. In 2D, a rotation of $\theta$ can be expressed,

$$\left[\begin{array}{c}x'\\y'\end{array}\right] = \left[\begin{array}{c c}\cos\theta & -\sin\theta\\ \sin\theta&\cos\theta\end{array}\right]\left[\begin{array}{c}x\\y\end{array}\right].$$

For an infinitessimal rotation $\delta\theta$, this can be approximated as

$$\left[\begin{array}{c}x'\\y'\end{array}\right] = \left[\begin{array}{c c}1 & -\delta\theta\\ \delta\theta&1\end{array}\right]\left[\begin{array}{c}x\\y\end{array}\right]=\left[\begin{array}{c}x-\delta\theta y\\y+\delta\theta x\end{array}\right].$$

Thus for a function $f(\mathbf{x})$, the rotation about the z-axis $f(R_{ij}x_j)$ can be approximated

$$f(R_{ij}x_j)\approx f(\mathbf{x}) + \delta\theta \left(y\frac{\partial f}{\partial x} + x\frac{\partial f}{\partial y}\right) = f(\mathbf{x}) + (\delta\theta \hat{z})\cdot\left(\mathbf{x}\times\frac{\partial f}{\partial\mathbf{x}}\right).$$

Now, expanding out our function to first order (and remembering the handy Levi-Civitia tensor for index notation),

$$A(R_{ij}q_j,R_{ij}p_j) = A(q_i,p_i) + \delta\theta_i\epsilon_{ijk}q_j\frac{\partial A}{\partial q_k} + \delta\theta_i\epsilon_{ijk}p_j\frac{\partial A}{\partial p_k}.$$

This time we need to be more careful with the identity we insert because the problem inherently requires more than one dimension. The identity here can be written as the Kronecker Delta $\delta_{k\alpha}=\frac{\partial q_k}{\partial q_\alpha}=\frac{\partial p_k}{\partial p_\alpha}$. Also, in anticipation of pulling out a Poisson bracket, we can switch the order of the terms. Thus

$$A(R_{ij}q_j,R_{ij}p_j)=A(q_i,p_i) + \delta\theta_i \epsilon_{ijk}\left[p_j\frac{\partial q_k}{\partial q_\alpha}\frac{\partial A}{\partial p_\alpha} + q_j\frac{\partial p_k}{\partial p_\alpha}\frac{\partial A}{\partial q_\alpha}\right].$$

Noting that $\frac{\partial p_j}{\partial q_\alpha}=\frac{\partial q_j}{\partial p_\alpha}=0$, we may pull terms into the derivatives.

$$A(R_{ij}q_j,R_{ij}p_j)=A(q_i,p_i) + \delta\theta_i \epsilon_{ijk}\left[\frac{\partial p_j q_k}{\partial q_\alpha}\frac{\partial A}{\partial p_\alpha} + \frac{\partial p_k q_j}{\partial p_\alpha}\frac{\partial A}{\partial q_\alpha}\right].$$

One of the properties of the Levi-Civita tensor is that $\epsilon_{ijk}=-\epsilon_{ikj}$, allowing us to switch the indices of one of the terms (so that the $p$s and $q$s always have the same index). 

$$A(R_{ij}q_j,R_{ij}p_j)=A(q_i,p_i) - \delta\theta_i \epsilon_{ijk}\left[\frac{\partial q_j p_k}{\partial q_\alpha}\frac{\partial A}{\partial p_\alpha} - \frac{\partial q_j p_k}{\partial p_\alpha}\frac{\partial A}{\partial q_\alpha}\right].$$

Recognize the Poisson bracket in the above:

$$A(R_{ij}q_j,R_{ij}p_j)=A(q_i,p_i) - \{\delta\theta_i\epsilon_{ijk}q_jp_k, A\}.$$

We can now identify the infintessimal generator of rotations as $\delta G=\delta\theta_i\epsilon_{ijk}q_jp_k$. What is this in vectors (not index notation)? Is this the answer you expected?

### Infinitessimal generator of time propagation
Perform this same analysis to find the generator of the transformation that takes $A\left(q(t),p(t)\right)$ to $A\left(q(t+\delta t),p(t+\delta t)\right)$.

## Note on conservation laws
We learned from Noether's Theorem that continuous symmetries in the Hamiltonian are associated with conserved quantities. We can use the formalism developed here and in the homework assignment as further demostration of this. Take, for instance, translational symmetry along one of the generalized coordinates $q_i$. What relationship must $H(q_i,p_i)$ and $H(q_i+\varepsilon,p_i)$ have if $H$ has translational symmetry? Using the last problem from the homework, which asks you to find the total time derivative of an arbitrary function in terms of the Poisson bracket, and the analysis here, what value is conserved? Is it the one you expected for translational symmetry?
