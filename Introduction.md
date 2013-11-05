#An Introduction to EM Inversion

##Overview

This document is intended as an introduction to electromagnetic (EM) inversion for fourth-year undergraduates. EM inversion is essentially the process of using measured EM field information to make inferences about that field elsewhere in space--for example, EM inversion is extremely important in biomedical imaging, where measured EM data can give us information about what is happening inside the human body.

**NB. This document is a work in progress, and shouldn't be considered authoritative by any means. Feel free to contribute by submitting a pull request or emailing the author.**

##Background

Introductory EM courses (together with our knowledge of math, and a basic understanding of numerical methods) will have provided enough of a background to reach a general understanding of how an EM inversion process could work--here we'll briefly review some of those foundational concepts and also consider some of the challenges involved in implementing such a system.

 * Green's function in EM
 * Modal expansion
 * Ill-posed problems, generally
 * Fredholm's integral equation (of the first kind)
 * A note about computational complexity

##Source reconstruction

 * An explanation of *Differences between modal expansion...* and *An improved super-resolution source reconstruction method* from Sarkar's group

##Solving the Fredholm integral equation numerically

 * An explanation of Per Christian Hansen's *Numerical tools for analysis and solution of Fredholm integral equations of the first kind*

##Current Developments

 * MR stuff (current research)
