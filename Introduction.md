#An Introduction to EM Inversion

##Overview

This document is intended as an introduction to electromagnetic (EM) inversion for fourth-year undergraduates. EM inversion is essentially the process of using measured EM field information to make inferences about that field elsewhere in space--for example, EM inversion is extremely important in biomedical imaging, where measured EM data can give us information about what is happening inside the human body.

**NB. This document is a work in progress, and shouldn't be considered authoritative by any means. Feel free to contribute by submitting a pull request or emailing the author.**

##Background

Introductory EM courses (together with our knowledge of math, and a basic understanding of numerical methods) will have provided enough of a background to reach a general understanding of how an EM inversion process could work--here we'll briefly review some of those foundational concepts and also consider some of the challenges involved in implementing such a system.

###Concepts

####Electric Current Density and Equivalent Magnetic Current

Electric Current Density **J** (a vector field) and Equivalent Magnetic Current **m** (also a vector field) can interchangeably be used to completely define the behaviour of an antenna. If either **J** or **m** are known, then the *free space* Magnetic Vector Potential (**A**, also a vector field) and the Electric Field **E** or Magnetic Field **M** (also vector fields) can be completely described at any point surrounding the antenna. In other words, if we know the distribution of current on an antenna, we can know what its radiation pattern will look like in free space. EM inversion is about using those properties to gain insights, either about the space in question (if the behaviour of the source antenna is known, then we can learn about a space by measuring the electric field around it, ie. observing how it's different from the expected pattern in free space) or about the source antenna (if we're measuring in pseudo-free space, then we can use the measured field to gain insight about the source antenna).

####Green's function

[Green's function](http://en.wikipedia.org/wiki/Green's_function) is not a single function, but rather a *type* or *class* of function that is particularly useful for solving certain kinds of differential equations. Basically, for an inhomogeneous differential equation (ie. a wave equation) described by `L * u(x) = f(x)`, there is often* a corresponding function `G` such that the integral of `G(x,s) * f(x)` with respect to `s` is equal to `u(x)`--`G` in this case would be the Green's function, and it's a very signficant idea because it means that for physical systems which we understand and where such a function exists, we can always solve for `u(x)` as long as `f(x)` is known.

* Mathematicians will have fun describing the specific cases where a Green's function may or may not exist. For wave equations, I think there will always be one.

####Modal expansion

For a planar wave where **E** (or, interchangeably, **M**) are known for any plane orthogonal to the wave, the Fourier transform can be used to determine **E** or **M** for any other far-field plane orthogonal to the wave. This has similar implications to the discussion of **J** and **m** above.

####Fredholm integral equation (of the first kind)

A [Fredholm integral equation](http://en.wikipedia.org/wiki/Fredholm_integral_equation) is the form of equation used with a Green's function, as described above (ie. the integral of `K(x,y) * f(y)` with respect to y).

###Challenges

####Ill-posed problems

Ill-posed problems are the opposite of [well-posed problems](http://en.wikipedia.org/wiki/Well-posed_problem)--that is, either no unique solution exists or the solution's behaviour does not change continuously with the initial conditions. Of course, we're generally not interested in problems where no unique solution exists, but we're unlucky in the sense that inverse problems often have the characteristic of having a solution which changes drastically depending on the initial conditions.

####A note about computational complexity

Any application of EM inversion intended for real-world use must take into account the computational (or algorithmic) complexity involved. For example, a biomedical solution with marginal increases in image quality may not be acceptable if it requires increasing processing time by an order of magnitude. As such, it is helpful to consider the cost of various inversion techniques in measures of computational complexity such as ["Big O" notation](http://en.wikipedia.org/wiki/Big_O_notation) and I will attempt to do so as much as possible.

##Source reconstruction

 * An explanation of *Differences between modal expansion...* and *An improved super-resolution source reconstruction method* from Sarkar's group

##Solving the Fredholm integral equation numerically

 * An explanation of Per Christian Hansen's *Numerical tools for analysis and solution of Fredholm integral equations of the first kind*

##Current Developments

 * MR stuff (current research)
