---
layout: post
title:  "A Brief Introduction To Higher Mathematics"
description: "Show a picture of Einstein and most people would recognize who he is. A lot of people would be able to recognize Heisenberg and certainly even more people have heard of him, even though they don't know how a picture of him would look like..."
date:   2017-12-21 11:13:11 +0300
image: "/images/lie8.jpg"
---
Einstein used the phrase "reading the mind of God" a lot when talking about physics--to be more precise, he said something along the lines of:

*I want to know how God created this world. I'm not interested in this or that phenomenon, in the spectrum of this or that element. I want to know His thoughts, the rest are details.*.

Of course, Einstein used "God" as a stand-in for "the laws of the universe", but what most people don't know is that is as perceptive as he was, he still relied of the work of Hermann Minkowski to describe the mathematical underpinnings of General Relativity. You can look at what's happening and have an intuitive understanding of the processes at work, but if you want to describe and formalize everything, you need to understand "the language of God".

And that language is mathematics.

![weyl](/images/weyl.png){:class="img-responsive"}

Getting back to Einstein, show a picture of him and most people would recognize who he is. Still quite a few people would be able to recognize Heisenberg and certainly even more have heard of him, but not many a folk have even heard of Hermann Weyl--which is surprising, considering the man's contribution to science and mathematics.

If you follow physics blogs, you might have read that the main problem in physics right now is combining relativity with quantum mechanics. That's not correct, Paul Dirac did that in 1928 and he also predicted the existence of anti-matter, so that's not the problem. The problem is we don't know how to create a quantum theory of gravity, because no attempt at this is [renormalizable](https://en.wikipedia.org/wiki/Renormalization), but that's something for another day.

Mathematicians are the unsung heroes of the field and you can think of this article as a small homage to Weyl. If it wasn't for him, we wouldn't have *representation theory* or *gauge theory*. But before we get into the sweet stuff, we need to lay the ground work. So here we go.

### Algebraic Groups
Let's start with the basics: groups. Groups are "abstract algebraic structures"--a group consists of a set of *elements* (say all positive integers smaller than 100) and an *operation*. Let's call our group G. We will annotate the operation with "•".

* First of all, the operation • between any two elements, *a* and *b*, such as a • b = c must produce a c that's part of the group set.
* Second, this operation must be associative, such that *(a • b) • c = a • (b • c)*.
* Third, the group must have an "identity" (or "zero") *i* that leaves any element from the set unchanged under the operation, such that *a • i = i • a = a*
* Also each element must have an "inverse" *a<sub>i</sub>*, such that *(a • a<sub>i</sub>) = i*
* This is not a requirement for groups, but if *(a • b) = (b • a)*, the group is called commutative or *abelian*. Otherwise it's called non commutative or non-abelian.

A simple example would be the [circle group](https://en.wikipedia.org/wiki/Unitary_group), the group of all complex numbers with an absolute value of 1 where the operation of the group is multiplication.

![rot2](/images/circle-group.svg){:class="img-responsive"}

Multiplying two complex numbers with absolute value 1 gives us another complex number with absolute value of 1. Duh.

![weyl](/images/modulo.svg){:class="img-responsive"}

Not only that, but multiplication is equivalent with the addition of phases.

*Groups are concepts that allows us to model real life stuff. They also allow us to look at all this stuff and see patterns such as symmetries.*

I spoke about it of delved into [symmetries]() somewhat, but I didn't formalize the concept.

### Transformations
When you're working with coordinate systems, you tend to use a lot of spatial transformations. For example, if we would want to rotate a point of coordinates *x, y* around the origin by a &theta; angle, we would have the following equations:

![rot1](/images/rot1.svg){:class="img-responsive"}

Which in matrix form looks like:

![rot2](/images/rot2.svg){:class="img-responsive"}

More complex transformations (in 3D) or [Lorentz transformations](https://en.wikipedia.org/wiki/Lorentz_transformation) take more complex matrices and these matrices can me multiplied for complex transforms.

### Symmetry Groups
Since we now have a notion of what transformations and groups are, we can define the notion of *symmetry groups*. The symmetry group *for a certain object* (such as a geometric object, say a sphere or cube, or a signal etc.) consists of all the transformations that leave that object unchanged.

Let me exemplify: if we have a sphere, we can rotate it by any arbitrary amount in any direction (and we can also mirror it--or flip it in any direction) and the resulting object would be *indistinguishable* from the original.

![sphere](/images/sphere.svg){:class="img-responsive"}

The matrix rotation over an arbitrary axis with an arbitrary angle theta looks like this:

![rot-random](/images/rot-random.svg){:class="img-responsive"}

The matrix looks complicated, so don't worry about it! What is important is that we can have any value for &theta; and for the orientation of the axis *(u<sub>x</sub>, u<sub>y</sub>, u<sub>z</sub>)* so we are dealing with a *smooth symmetry set*. The set of the symmetry group for a cube is not smooth--we can rotate it by an arbitrary amount (nor flip it) for obvious reasons.

### Lie Groups
Lie groups are interesting because they combine geometry with algebra. Actually, before we define what a Lie group is, we need to explain what manifolds are: a simple manifold would be something like a sphere or ellipsoid, which approximates the surface of the Earth. We can have even more complicated manifolds such as the one in the picture, not to mention that we can have more than 2 dimensions.

![rot2](/images/manifold.PNG){:class="img-responsive"}

Lie groups are groups in which the elements of the group also form a *differentiable* or [smooth manifold](https://en.wikipedia.org/wiki/Differentiable_manifold). That simply means the manifold is continuous (it doesn't have any holes in it) and its surface is smooth, meaning that there aren't any jagged angles.

### Group Representation
Groups in and of themselves tend to be quite abstract and *representation theory* is a way to make them more tractable and intuitive. In representation theory, the elements of the group can be represented by matrices which are essentially geometric transformations.
*A representation of a group is another group, where the elements are transformation matrices like the ones we presented earlier and the group operation is matrix multiplication.*

What those matrices look like depends on what group we are trying to create a representation of, but keep in mind the whole idea behind them is to reduce more complicated problems to linear algebra problems, which are usually a tad easier to tackle.

The simplest group that lends itself easy to representation theory is the circle group--the circle is one of simplest manifolds there are and the elements of the circle group's representation look like this:

![rot2](/images/representation.svg){:class="img-responsive"}

A group representation is a [*homeomorphism*](https://en.wikipedia.org/wiki/Homeomorphism). In general, a function *f(x)* is a homeomorphism if:

*f(a·b)=f(a)·f(b)*

This means the representation of *e<sup>i&theta;<sub>1</sub></sup>·e<sup>i&theta;<sub>2</sub></sup>* is the same as multiplying the representations of  *e<sup>i&theta;<sub>1</sub></sup>* and *e<sup>i&theta;<sub>2</sub></sup>*. Just try it out.

### Why Do We Care About All This?
Well, we care because symmetries ARE the laws of physics. One simply needs to analyse the results of millions of collisions in an accelerator, plot the results and look at the patterns (or symmetries) of the resulting signal in order to deduce the laws that govern the interactions.

![rot2](/images/curved.jpg){:class="img-responsive"}

The laws of quantum electrodynamics are described by the [U(1)](https://en.wikipedia.org/wiki/Unitary_group) symmetry group. Electroweak interactions as we perceive them in our day to day lives are described by a [spontaneously broken symmetry](https://en.wikipedia.org/wiki/Spontaneous_symmetry_breaking) of the SU(2)xU(1) group etc. Don't worry about that means for the time being, we'll get to it in future articles. Also, all of this happens in an arena that's quite different from the flat Euclidean space we're all used to from our day to day experience, because as you can see in this Hubble deep space image, space actually is curved and quantum field theory needs to take this into account--and that's where representations of Lie groups come in very handy.

I'll refer back to this article once we get to the sweet stuff.
