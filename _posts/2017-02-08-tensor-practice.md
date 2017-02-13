---
layout: mathpost
title:  "Tensor Practice"
date:   2017-02-07
categories: review math
---

1. Tensor Review: Tensors are real!
2. Tensor Practice: index notation and Einstein summation convention

## 1. Tensor Review: Tensors are real!
A brief, but useful, definition of an $n$-rank tensor is that it is a _real-valued function of $n$ vectors_. This means that it is an object into which we can put $n$ vectors and expect a scalar out. Scalars are nice because they don't transform when we change viewpoints or perform coordinate transforms. There are many notations for a tensor:
$
\mathbf{T}, \mathbb{T}, \overleftrightarrow{T}, \underline{\underline{T}},
$
and many ways to indicate how we put vectors into them, such as with dots $\cdot$, like in our definition of rotational, kinetic energy $\mathbf{\omega}\cdot\mathbb{I}\cdot\mathbf{\omega}$. This works for tensors of rank 2, but becomes more difficult for higher rank tensors (do we put the third vector over it? the fourth below? the fifth .... in front??). [Kip Thorne](http://pmaweb.caltech.edu/Courses/ph136/yr2012/) offers an alternative that I like because it reminds me of the functional nature of tensors and translates nicely into pseudo-code when I need to do numerics. (Read chapter 1 of the linked text for a very readable summary of tensors in physics.) He writes a tensor as
$$
\mathbb{T}\left(\underline{\;}, \underline{\;}\right),
$$
where the number of spots tell you the rank (the number of input vectors). If the order of the inputs doesn't matter, then the tensor is _symmetric_. If the order does matter, we can label the inputs to keep them straight:

$$
\mathbb{T}\left(\underline{\;}_i, \underline{\;}_j\right).
$$

This suggests a nice shorthand for how to write a tensor, the way you'll see fairly often, as an object with many indices telling you how many vectors can be put into it, $\mathbb{T}_{ij}$.

Let's take a look at a couple of tensors. We'll start with the one from class, $\mathbb{1} (\underline{\,}, \underline{\,})$, which takes two inputs - it is a rank-2 tensor. It is also symmetric, so we don't need to label it's inputs. Let's put a position vector $\mathbf{r}$ into both slots, and what do we get? How about different position vectors? The tensor $\mathbb{1}$ gives us a sense of distance. We call the tensor that defines distance for a vector space the _metric tensor_, and usually denote it with a $\mathbf{g}$. For flat spaces, $\mathbf{g}$ is constant and doesn't depend on where you are, an assumption relaxed in General Relativity.

Let's try another. The moment of inertia tensor $\mathbb{I}\left(\underline{\,}, \underline{\,}\right)$. We can define the output of tensors for different kinds of inputs. If we put in a normal vector (just one), we get the moment of inertia along a particular axis. If we put in an angular velocity vector, we call it the _angular momentum_ vector. And if we put in two angular velocity vectors, we call it twice the _rotational kinetic energy_ (a scalar, more on this later).

To play with the moment of inertia tensor and understand a derivation from class, we need to introduce one more tensor, the Levi-Civita tensor $\mathbf{\varepsilon}$. This tensor defines the cross product. What is its rank? Well, when we put in two vectors, say $\mathbf{a}\times\mathbf{b}$, what comes out? A vector! But a tensor is a real-valued function, so there's one more spot to put a vector, making it the rank-3 tensor

$$\mathbf{\varepsilon}\left(\underline{\,}_i, \underline{\,}_j, \underline{\,}_k\right).$$

This tensor is not symmetric (in fact, it's also called the [_anti-symmetric tensor_](https://en.wikipedia.org/wiki/Levi-Civita_symbol)), so I need to label the inputs. If I put three position vectors into $\mathbf{\varepsilon}$, what do we call that scalar? You may remember that the magnitude of the cross product is the area of the parallelogram defined by the two input vectors. Throw in another vector and what you have is a volume! Like the metric tensor, the Levo-Civita tensor tells us something very important about our vector space.

### Index Notation and Einstein summation convention
With a set of basis vectors, we can write a vector $\mathbf{a}$ by its components along those basis vectors $(a_1, a_2, a_3)$ which we can abbreviate as $a_i$ where $i$ goes from 1 to 3. A very important operation with vectors is the dot product, which is written and computed by
$$
\mathbf{a}\cdot\mathbf{b} = a_1b_1 + a_2b_2 + a_3b_3 = \sum_{i=1}^3 a_ib_i = a_ib_i.
$$
The last term in the above has our abbreviated vector notation and makes use of the _Einstein summation convention_. The convention is, to save time writing summation symbols, to implictly sum over indices any time an index is repeated.

To see how this convention works with tensors, we'll continue on with the example of the dot product. We already saw above that the dot product can be represented as a rank-2 identity tensor $\mathbb{1}$ or the metric tensor $\mathbb{g}$. That is,

$$
\mathbf{a}\cdot\mathbf{a} = \mathbb{1}(\mathbf{a},\mathbf{a}) = \mathbf{a}\cdot\mathbb{1}\cdot\mathbf{a},
$$

which we can write as \\(a_i\mathbb{1}_{ij}a_j,\\), where as before the summation over both indices (independantly) is implied. The components of the identiy tensor can be represented by a delta function

$$
\delta_{ij} = \left\{\begin{align}1& \text{ if } i=j\\ 0& \text{ otherwise}\end{align} \right. .
$$

Now, when we sum over all the $i$ and $j$ combinations, the only terms that won't be zero are the terms where $i$ equals $j$. Hence, the above reduces to

$$a_i\mathbb{1}_{ij}a_j = a_i\delta_{ij}a_j=a_ia_i,$$

which is the dot product that we wanted to compute. This notation makes it easier to represent and perform computations with many tensors of various ranks.


## Tensor Practice
Let's practice manipulating tensor equations by proving a relation we had in class. We said that the rotational kinetic energy, given by

$$
T_\text{rot} = \frac{1}{2}m (\mathbf{r}\times\omega)\cdot(\mathbf{r}\times\omega),
$$

could be written as 

$$
T_\text{rot} = \frac{1}{2}\mathbf{\omega}\cdot\mathbb{I}\cdot\mathbf{\omega}.
$$

Prove this. To help, use the identity
$$
\varepsilon_{ijk}\varepsilon_{lmk} = \delta_{il}\delta_{jm} - \delta_{im}\delta_{jl}.
$$

We write $$\mathbf{r}_i\times\omega$$ as $$\varepsilon_{ijk}r_j\omega_k$$ (note that the only unpaired index is $i$, which indicates the components of the cross product resultant vector). The second factor needs to be writte as $\varepsilon_{ilm}r_l\omega_m$, with the $i$ repeated to signify the dot product between these vectors. None of the other indices can be repeated because they are already paired. Plugging in, and simplifying the delta functions,

$$
T_\text{rot} = \frac{1}{2}\omega_k\left[m\left(r_jr_j \delta_{km} - r_kr_m \right)\right]\omega_m.
$$

See that this has precisely the form we want! $\mathbf{\omega}$'s on either side of something with two indices ($k$ and $m$). Remembering that $\delta_{km}$ gives the compoments of the identity tensor, this can be written in a coordinate-independent way as

$$
T_\text{rot} = \frac{1}{2}\mathbf{\omega}\cdot\left[m\left(\left(\mathbf{r}\cdot\mathbf{r}\right)\mathbb{1} - \mathbf{r}\mathbf{r}\right)\right]\cdot\mathbf{\omega}.
$$

This is the form of the moment of inertia tensor we used in class and on the homeworks.














