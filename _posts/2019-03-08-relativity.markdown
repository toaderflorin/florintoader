---
layout: post
title:  "What Exactly Was Bothering Einstein?"
description: ""
date:   2019-03-07 11:13:11 +0300
image: "/images/einstein.jpeg"
---
In 1905, a young Albert Einstein put out a paper that he called *On The Electrodynamics Of Moving Bodies* that would forever change the way we think about space and time (no, he didn't call his work *Special Relativity*). Among other things, it says that space contracts, time dilates and even the notion of simulaneity is relative is observer dependent. 

Let's be serious, nobody walks around and thinks: <i>hmm, I think that if I move at a certain speed relative to the Earth, time would have to pass slower for me</i>. Yet Einstein's special theory of relativity says this absolutely must happen, it gives us the *exact rate* at which it happens, and we can also build very precise atomic clocks that can measure differences in the passage of time and they are in perfect agreement with predictions.

![einstein](/images/einstein.jpeg){:class="img-responsive"}

It should be noted that the notion of relativity isn't exactly new. Galileo had already introduced the concept of *inertia* centuries ago (an object that is in motion stays in motion and an object that's stationary remains stationary, unless acted upon). He also realized that the concept of *absolute* motion is meaningless, and that one can only talk about motion in relation to a frame of reference. 

*Galilean relativity makes sense intuitively for most people. If I'm in a car that's moving at 100km/h and I overtake another car that's moving at 80km/h  t(relative to the road), I would perceipe the relative speed to be 20 km/h.*

Object trajectories are consistent:

And yet, this must be wrong. But in figuring out why this is, Einstein didn't think in terms of cannonballs falling from high towers and speeding bullets. He was preocupied with how electromagnetism looks for different observers travelling at relative speeds to one another.

Before Maxwell, people used to think as electricity and magnetism as two different phenomena. We had strange materials such as magnetite that act on certain metals without having to touch them, and we learned how to create electricity by statically charging objects through friction.

But then something interesting happened. In xxxx A showed that a moving electric charge generates a magnetic field.

Maxwell's genius lied in his ability to combine the work of the people before him, people like Faraday and Gauss, into a single comprehensive framework -- he's actually credited with the first unified theory in the history of physics. His realisation was that if a variable magnetic field creates a variable electric field and vice versa, then what you have is a [transverse wave](https://en.wikipedia.org/wiki/Transverse_wave) and using the known values for electric and magnetic permeability, he was even able to calculate the speed at which this wave propagates through space.

![em-wave](/images/em-wave.gif){:class="img-responsive"}

And to quite a lot of people's surprise, the speed was very close to 300 000 m/s, which is what the speed of light was known to be. Maxwell had shown that light is an electromagnetic wave!

So if light is a wave then the natural intuition would be to ask: *a wave propagating through what?* And sure enough, people did set out to find traces of whatever medium light progagates through, which they dubbed a *[luminiferous ether](https://en.wikipedia.org/wiki/Luminiferous_aether)*, the most famous being the Michelson-Morley experiment. 

![em-wave](/images/ether.png){:class="img-responsive"}

The result of this experiment was considered very weird because the notion that the Earth was stationary was long ago abandoned. So in order to save the idea, various tweaks were introduces. Lorentz had the that since electromagnetism mediates the interactions between molecules the apparatus might contract along the direction of movement because of the changes in interaction force because of the movement and he was able to calculate what the contraction factor might be:

![em-wave](/images/contraction.svg){:class="img-responsive"}

What's interesting is in his 1095 work, Einstein took a different approach. Referring to Faraday's famous induction experiment, he wrote: 

*It is known that Maxwell's electrodynamics – as usually understood at the present time – when applied to moving bodies, leads to asymmetries which do not appear to be inherent in the phenomena. Take, for example, the reciprocal electrodynamic action of a magnet and a conductor. The observable phenomenon here depends only on the relative motion of the conductor and the magnet, whereas the customary view draws a sharp distinction between the two cases in which either the one or the other of these bodies is in motion. For if the magnet is in motion and the conductor at rest, there arises in the neighborhood of the magnet an electric field with a certain definite energy, producing a current at the places where parts of the conductor are situated. But if the magnet is stationary and the conductor in motion, no electric field arises in the neighborhood of the magnet. In the conductor, however, we find an electromotive force, to which in itself there is no corresponding energy, but which gives rise – assuming equality of relative motion in the two cases discussed – to electric currents of the same path and intensity as those produced by the electric forces in the former case.*

To demonstrate what he meant, let's simplify things and instead of a coil, let's use a simpler setup:

1. Imagine you have a magnet and a small object like a ball statically charged with electricity (which we charge) and a magnet.
2. Let's now assume that our electrically charged object moves at a constant speed *v* in one direction perpendicular to the magnetic field. This would create a force on the particle.
3. Let's now keep the charged object stationary and move the magnet instead, which means that as we move it, the magnetic field will vary in time at each point in space. This in turns causes an electric field which acts on the charged object.

The force generated on the object is exactly the same even though we described what seem entirely two different scenarios, wo only the relative speed between the magnet and the charge matters! Alternatively, the charged object could be moving at *v/2* in one direction and the magnet at *v/2* in the other and so on. You would assume that the force is the same because *v/2 - (-v/2)* is *v*, but there's a slight difference in the force on the object than in the previous examples. It's not big, but it is there. 

It seems that the classic law of addition of velocities doesn't work -- if you want to make the equations work, you need to use the following law:

![em-wave](/images/velocity.svg){:class="img-responsive"}

In fact, if one studies Maxwell's equations, a strange fact pops out: *the speed of propagation of the wave doesn't depend on the speed of the observer, which is in stark violation with classical relativity.*

So in order for the laws electromagnetism to hold (which were tested thoroughly), Einstein was forced to abandon classical relativity. He postulated:

  1. The laws of physics are the same in all inertial frames of reference.
  2. As measured in any inertial frame of reference, light is always propagated in empty space with a definite velocity c that is independent of the state of motion of the emitting body.

Number one makes sense because observers travelling at different speeds need to agree on what's happening, it's pretty much basic logic. Number two is weird to us intuitively, but we know it's happening both from the mathematics **and** experiment.

Einstein, being heavily influenced by Mach's positivism, simply stated that since we cannot detect an ether we have no reason to assume it's there. But what we do know is that 1. and 2. are correct because it's something that we can see and that's all we need.

Time dilation:

![einstein](/images/time-dilation.png){:class="img-responsive"}