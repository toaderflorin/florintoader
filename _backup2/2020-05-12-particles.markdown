---
layout: post
title:  "Particles Are Not Really Particles"
description: "Antimatter is interesting because it was predicted by Paul Dirac's equation before it was actually discovered in a laboratory and for a while this prediction was actually problematic because no one had actually seen such an exotic form of matter.
"
date:   2019-05-11 11:13:11 +0300
image: "/images/header.jpg"
---
When people think of particles, they think flying bullets or incadescent embers rising up from a camp fire in the night. Newtonian mechanics itself is built around forces acting on particles moving in space: you can track them individually, you know what they do and so forth. If a baseball is coming towards you, you have an intuitive feeling for where it is. 

In a nutshell, when people think of particles, they think of something like this:

![em-wave](/images/header.jpg){:class="img-responsive"}

Of course, the whole particle being in two places at the same time comes from the [double slit experiment](https://en.wikipedia.org/wiki/Gauge_theory) and the particle being both a wave and a, well, "particle" comes from [Louis DeBroglie](https://en.wikipedia.org/wiki/Wave%E2%80%93particle_duality).

How can something be both a particle (which implies being pointlike) and a wave (which implies being spread out)? We really do have a philosophical conundrum on our hands which is why quantum mechanics is so hard to understand -- most physicists would say *shut up and calculate, we don't do philosophy*. Feynmann famously said that if you think you understand quantum mechanics you don't really understand quantum mechanics, but is that really so? Actually, not really.

*The truth is we have multiple explanations about what quantum mechanics means and we cannot agree on one.*

If you're into physics, you've mostly likely heard about Heisenberg's uncertainty principle which says that we cannot know both the position and speed of a particle simultaneously and that particles can be in multiple places at the same time and other such weird things.   IThere isn't anything particularly surprising about Heisenberg's principle because waves don't have an exact location in time, they are spread somewhat.
Imagine you drop a pebble into a pool. The more localized the wave is, the taller/deeper the peaks and throghs are and viceversa. 
<br/><br/>
`
![em-wave](/images/schrodinger2.png){:class="img-responsive"}

The momentum wavefunction happens to be the [Fourier transform](https://en.wikipedia.org/wiki/Fourier_transform) of the position wavefunction, so this happens to work out quite nicely.

This isn't particularly weird. QM actually became weird when Born suggested we can use this wavefunction to calculate probability. In this particular example, the wavefunction gets the location as an input parameter and returns a complex number and it must be unitary and square integrable because obviously we want to get a real number for probabilities and it must be exactly 1 over the whole space.

People are crediting [quantum field theory](https://en.wikipedia.org/wiki/Fourier_transform) (and implicitly Paul Dirac) with quantizing the electromagnetic field and coming up with a relativistic theory of the electron but in my opinion he did something far more important than that: QFT doesn't try to track what *this* or *that* particle is doing. Instead, it deals with vibrating fields, it takes into account that this vibration energy is quantized (it comes in discrete chunks) and  treats individual particles as units of vibtration energy. 

Not that long ago, this photograph was snapped using a "quantum" camera: 

![em-wave](/images/hydrogen.jpg){:class="img-responsive"}

The blue part is the electron. You'd be excused if you think it's moving very fast, but that's not what's happening -- what we have is some kind of oscillating field.

The wavefunction for Heisenberg's equation just takes the location as an input and returns a complex number. Pauli's wave function takes spin into acount (which can be up or down), so now the wave function needs to have two components - so it is a column vector with two rows. Dirac found that in order to make the physics of the electron be compatible with relativity, he had to use a four component function and his equation had negative energy solutions that we had no idea what to do with at first so he was inclined to discard his theory. Until he figured out that he can treat these solutions as antiparticles so the equation is describing not only spin up and down electrons but also spin up and down positrons. Moreover, when a positron would encounter an electron, they would annihilate and would release energy. So we have a field and at each point in this field we have a column vector of four complex numbers. Now this is obviously an abstraction, it has to be a model of something because to get any kind of meaningful prediction, you would have to apply an operator on this.

So let's try and put everything together. Let's say we have one and only electron sitting about. But this electron isn't a standalone entity, it's something in a field and because of fluctuations in this field, it's surrounded by a sea of virtual matter-antimatter pairs and as it's moving about it will at some point into contact with a positron which means it will annihalate and a free virtual electron becomes unpaired and and takes the place of our "old" electron. You could have tried the same thought experiment with three or three hundred electrons and it would pretty much go the same, their number (and overall charge) is conserved -- which is a byproduct of U(1) [gauge symmetry](https://en.wikipedia.org/wiki/Gauge_theory), but we won't get into that. 

![em-wave](/images/vacuum.png){:class="img-responsive"}

Right off the bat, we notice a couple of things. First of all, it's pointless talking about the identity of a particle because it disappears almost instantly. Second, we cannot observe the virtual particles but they do have an effect on the "real" particles and they bump them around in a seemingly random fashion (may I say, stochasticaly?).

Don Lincoln has a nice intuitive explanation for what a Higgs boson is, what it here.

<iframe width="860" height="455" src="https://www.youtube.com/embed/joTKd5j3mzk" frameborder="0" allowfullscreen></iframe>

<br />
You can apply that line of reasoning to all particles and think of them as phenomenona occuring in fields. It's like you have a pot of boiling water and you have enough energy in one place, bubbles start to form. Unlike bubbles in a boiling pot, the particles we get are all the same shape and size. But we do get more of them as we have more energy concentrated in one spot. 

I'd also like to argue that fields aren't really fundamental either. If you would ask a physicist the describe a glass of whater, he or she would describe it as a field that obeys the [Navier Stokes equations](https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_equations). And while that's not entirely untrue, the equations are just an idealization or aproximation. If you zoom in, you have water molecules. If you zoom in even more, you have protons, electrons and neutrons. 

Now let's have a look at what happens if you take the rules of QFT and *zoom in* to shorter and shorter distance scales (and hence higher energy scales).

![em-wave](/images/renormalization.png){:class="img-responsive"}

There is a small (but distinct chance) that your virtual photons would turn into electron-positron pairs which would then merge back into another photon. But there is also a chance that one of the electrons emits a virtual photon that in turn splits into another virtual pair and so forth. And you need to take these posibilities into acount when calculating how fields propagate in time, otherwise your calculations don't come out properly. 

Only there's a catch.