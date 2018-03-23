---
layout: post
title:  "Special Relativity Requires That Antimatter And Spin Exist"
description: "Antimatter is interesting because it was predicted by Paul Dirac's equation before it was actually discovered in a laboratory and for a while this prediction was actually problematic because no one had actually seen such an exotic form of matter.
"
date:   2018-01-12 11:13:11 +0300
image: "/images/dirac.jpg"
---
Antimatter is one of those things that most people regard as the stuff of science fiction but the reality is it's very much established science. If you aren't familiar with special relativity go ahead and have a look at my [article](http://florintoader.net/special-relativity) now -- it's something that you absolutely must grasp before delving into subjects like quantum field theory.

![crowd](/images/dirac.jpg){:class="img-responsive"}

This form of matter is interesting because it was predicted by Paul Dirac's equation before it was actually discovered in a laboratory and for a while this prediction was actually problematic because no one had actually seen such an exotic form of matter. Heisenberg even went as far as to call Dirac's equation garbage, but considering how strange the quantum world was beginning to look at the turn of the century, he probably should have known better.

### The Schrödinger Equation
The story of quantum field theory is interesting: when Schrödinger tried to describe what happens to an electron using his famous equation, he actually tried to make it compatible with Einstein's theory of special relativity but he was not able to and so the equation uses Newtonian concepts of time and space. But because he wasn't able to work out all the details, he decided to publish the version non compatible with special relativity which he thought was still novel enough, and which looks like this:

![crowd](/images/schrod.svg){:class="img-responsive"}

*H* is the Hamiltonian operator and represents the energy of the system and it's a differential operator of the second order:

![crowd](/images/hamiltonian.svg){:class="img-responsive"}

and where the inverted triangle is called the [Laplacian](https://en.wikipedia.org/wiki/Laplace_operator):

![crowd](/images/laplacian.svg){:class="img-responsive"}

If we were to try and tweak it and replace the terms with the [Lorentzian](https://en.wikipedia.org/wiki/Lorentz_covariance) concepts of time and space that special relativity adheres to, we would get the Klein Gordon equation which has a host of problems: first and foremost, the wave-function *isn't unitary* -- integrating (summing up) the function over the whole space doesn't give you 100% probability, which is absurd because the electron has to be *somewhere* with 100% probability. Heck, it's value isn't even constant so you cannot scale it by a factor to get 100%.

### The Pauli Equation
Second, it doesn't take electron spin into account which is a big problem. Not only do electrons come into two varieties (up and down), they sit at slightly different energy levels in the electron shell, so if you were actually to zoom in on this picture, you would see two very close lines instead of single ones (this is called the *fine structure* of the hydrogen atom).

![crowd](/images/hydrogen-spectrum.png){:class="img-responsive"}

To correct for this, Wolfgang Pauli extended Schrödinger's work and came up with a similar equation that has a wave-function with *two* components (&#936;<sub>+</sub> and &#936;<sub>-</sub>), each corresponding to a spin state.

![crowd](/images/pauli.svg){:class="img-responsive"}

It has however the same fundamental problem: it's not compatible with special relativity.

### The Dirac Equation
When trying to come up with a compatible quantum theory, Dirac tried the opposite approach: instead of trying to tweak the Schrodinger equation to obey special relativity rules, he postulated there's *another* equation that's *Schrodinger like* in structure and set out to figure out what the parameters are if they were to be compatible with special relativity.

![crowd](/images/dirac2.svg){:class="img-responsive"}

As a quick note, everybody is familiar with <i>E=mc<sup>2</sup></i> but that formula is valid only for non-moving particles -- it gives us the *rest mass* of a particle or object in its own frame of reference. Physicists tend to use the *energy-momentum relation* when doing calculations which is <i>E<sup>2</sup>=(pc)<sup>2</sup> + (m<sub>0</sub>c<sup>2</sup>)<sup>2</sup></i> and this is also what Dirac used. He postulated that there is some formula who's parameters obey this relationship.

So using Schrodinger's as a starting point, he realized that figuring out the coefficients is a factoring problem.


Dirac soon realized that for that to happen, the coefficients of the equation need to be at a minimum 4&times;4 matrices just as Pauli had used 2&times;2 matrices to model particles with spin which means the wave function now has four scalar components, &#936;<sub>1</sub>, &#936;<sub>2</sub>, &#936;<sub>3</sub> and &#936;<sub>4</sub>. Two of those components are wave functions for the familiar left and right handed electrons, but what to make of the other two? Moreover, these are the negative energy part of the solution which appear because of the fact that *E* is squared in the energy-momentum relationship. These negative energy solutions were so problematic that the scientific community almost gave up on the theory -- it was only the fact that the other two solutions were in such great accordance with experiment that any attempt to salvage the equation was made.

### The Dirac Sea
Dirac assumed the negative energy levels correspond to real states (although he wasn't sure what exactly they meant), but then the question was what to make of them? It was known that electrons tend to occupy the lowest energy states available to them so naturally all electrons we see should have spontaneously emitted light and fall lower and lower to levels corresponding to minus infinity.

To explain why that doesn't happen, Dirac postulated that all the negative energy states are already filled.

*In effect there is an infinite sea of electrons occupying those levels.*

![crowd](/images/diracsea.png){:class="img-responsive"}

So what happens then? A negative energy electron could absorb a photon of just the right frequency to jump up a quantum level?
