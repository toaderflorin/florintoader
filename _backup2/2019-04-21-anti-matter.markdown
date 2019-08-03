---
layout: post
title:  "Proving The Existence Of Antimatter With Mathematics"
description: "Antimatter is interesting because it was predicted by Paul Dirac's equation before it was actually discovered in a laboratory and for a while this prediction was actually problematic because no one had actually seen such an exotic form of matter.
"
date:   2019-04-20 11:13:11 +0300
image: "/images/dirac.jpg"
---
Antimatter is one of those things that most people regard as the stuff of science fiction, but it's very much real and established science, and interestingly, its existence was established mathematically. If you aren't familiar with special relativity go ahead and have a look at my [article](http://florintoader.net/relativity) now -- it's something that you absolutely must grasp before delving into subjects like quantum field theory. Here's an interesting thing about Einstein: he wasn't that good at maths, at least not when he started out as a young physicist. It actually took his good friend Hermann Minkowski to put special relativity on a rigorous mathematical foundation. 

Most people are familiar with E=mc2, but the correct relationship is:

![crowd](/images/mass-energy.svg){:class="img-responsive"}

Dirac's theory was also interesting in its historical context because nobody had seen anything resembling antimatter so there was quite a pushback from the scientific community. Heisenberg even went as far as to call Dirac's equation garbage, but considering how strange the quantum world was beginning to look at the turn of the century, he probably should have known better.

When Schrödinger tried to describe what happens to an electron using his famous equation, he actually tried to make it compatible with Einstein's theory of special relativity but he was not able to and so the equation uses Newtonian concepts of time and space. 

![crowd](/images/klein-gordon.svg){:class="img-responsive"}

But because he wasn't able to work out all the details, he decided to publish the version non compatible with special relativity which he thought was still novel enough, and which looks like this:

![crowd](/images/schrodinger.svg){:class="img-responsive"}

*H* is the Hamiltonian operator and represents the energy of the system and it's a differential operator of the second order:

![crowd](/images/hamiltonian.svg){:class="img-responsive"}

and where the squared inverted triangle is called the [Laplacian](https://en.wikipedia.org/wiki/Laplace_operator).  The equation can be solved analytically and this gives us the stable orbits of the electrons, the orbitals. The stable orbits are [*eigenvalues*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of the Hamiltonian.

![crowd](/images/orbitals.png){:class="img-responsive"}


If we were to try and tweak it and replace the terms with the [Lorentzian](https://en.wikipedia.org/wiki/Lorentz_covariance) concepts of time and space that special relativity adheres to, we would get the Klein Gordon equation which has a host of problems: first and foremost, the wave-function *isn't unitary* -- integrating (summing up) the function over the whole space doesn't give you 100% probability, which is absurd because the electron has to be *somewhere* with 100% probability. Heck, it's value isn't even constant so you cannot scale it by a factor to get 100%.

To correct for this, Wolfgang Pauli extended Schrödinger's work and came up with a similar equation. This equation has a wave-function with *two* components (&#936;<sub>+</sub> and &#936;<sub>-</sub>), each corresponding to a spin state and A and B are the electric and magnetic potentials and σ = (σ<sub>x</sub>, σ<sub>y</sub>, σ<sub>z</sub>) are three 2&times;2 matrices called the Pauli matrices. It has however the same fundamental problem: it's not compatible with special relativity. When trying to come up with a compatible quantum theory, Dirac tried the opposite approach: instead of trying to tweak the Schrödinger equation to obey special relativity rules, he postulated there's *another* equation that's *Schrödinger like* in structure and set out to figure out what the parameters are if they were to be compatible with Einstein's theory.

Dirac realized that a formula that would obey the energy-momentum relationship would have to look like this:

![crowd](/images/dirac2.svg){:class="img-responsive"}

He tried to find a formula that looks like this:

![crowd](/images/dirac-generic.svg){:class="img-responsive"}

Which means he would have to factor the diferential operator like this:

![crowd](/images/dirac6.svg){:class="img-responsive"}

Dirac soon realized that for that to happen, A, B, C and D need to be at a minimum 4&times;4 matrices just as Pauli had used 2&times;2 matrices to model particles with spin which means the wave function now has four scalar complex components.

Applying all the necessary conditions for unitarity / relativity and solving the resulting equations gives us A, B, C and D, which are called the *Dirac gamma matrices*.

![crowd](/images/gamma-matrices.svg){:class="img-responsive"}

Putting everything together, and using Einstein's summation convention over repeated indices, we get:

![crowd](/images/dirac-eq.svg){:class="img-responsive"}

Two of those four components are wave functions for the familiar left and right handed electrons, but what to make of the other two? Moreover, these are the negative energy part of the solution which appear because of the fact that *E* appears squared in the energy-momentum relationship. These negative energy solutions were so problematic that the scientific community almost gave up on the theory -- it was only the fact that the other two solutions were in such great accordance with experiment that any attempt to salvage the equation was made.

Dirac assumed the negative energy levels correspond to real physical states, but then the question was what to make of them? It was known that electrons tend to occupy the lowest energy states available to them so naturally all electrons we see should have spontaneously emitted light and fall lower and lower to levels corresponding to minus infinity. To explain why that doesn't happen, Dirac postulated that all the negative energy states are already filled.

*In effect there is an infinite sea of electrons occupying those levels.*

So what happens then? A negative energy electron could just emit and absorb random energy photons like a normal electron would do but (and would wiggle around on the same energy level), but it could also absorb a photon of just the right frequency to jump up a quantum level and become a positive energy electron. In effect, we have a *hole* in the negatively charged electron sea and this hole would act exact like a positively charged particle. If a free electron happens to encounter such a hole, it will "fall" in it thus disappearing and eliminating the extra energy as a photon.

This all sounds quite un-scientific, but sure enough positrons were discovered a few years later thus confirming Dirac's relativistic quantum theory.
