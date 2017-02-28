---
layout: mathpost
---

# When Nonholonomic Constraints are not-so
We discussed how a _holonomic_ constraint can be written as
$$f(q_i, t) = 0,$$
and effectively means that you've chosen one generalized coordinate too many (in that you can now write one as a function of the others). But let's say that our constraint also included the velocities:
$$f(q_i, \dot{q}_i, t) = 0.$$
What if we had a constraint, however, that had the form
$$f(\dot{q}_i, t) = a_i \dot{q}_i + b?$$
Is there a condition under which such a constraint, which looks like it's nonholonomic, is actually holonomic? Well, if we can find a function $g(q_i, t)$ such that
$a_i = \frac{\partial g}{\partial q_i}$ and $b=\frac{\partial g}{\partial t},$
then we may rewrite our constraint

$$f(\dot{q}_i, t) = \frac{\partial g}{\partial q_i}\frac{d q_i}{dt} + \frac{\partial g}{\partial t} = 0.$$

But this is actually just

$$f(\dot{q}_i, t) = \frac{dg}{dt} = 0,$$

which can readily be integrated to

$$g(q_i, t) - \textrm{constant} = 0,$$

which is a holonomic constraint.
