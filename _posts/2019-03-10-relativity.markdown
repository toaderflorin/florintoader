---
layout: post
title:  "What Exactly Was Bothering Einstein?"
description: "In 1905, a young Albert Einstein put out a paper that he called <i>On The Electrodynamics Of Moving Bodies</i> that would forever change the way we think about space and time (no, he didn’t call his work Special Relativity). Among other things, it says that space contracts, time dilates and even the notion of simulaneity is relative is observer dependent.
"
date:   2019-03-09 11:13:11 +0300
image: "/images/einstein.jpeg"
---
In 1905, a young Albert Einstein put out a paper which he called *Zur Elektrodynamik bewegter Körper (On The Electrodynamics Of Moving Bodies)* that would forever change the way we think about space and time (no, he didn't call his work *Special Relativity*). Among other things, it says that space contracts, time dilates and even the notion of simultaneity is relative and observer dependent. 

Let's be serious, nobody walks around and thinks: <i>hmm, I think that if I move at a certain speed relative to the Earth, time would have to pass slower for me</i>. Yet Einstein's special theory of relativity says this absolutely must happen, it gives us the *exact rate* at which it happens, and we can also build very precise atomic clocks that can measure differences in the passage of time and they are in perfect agreement with predictions.

![einstein](/images/einstein.jpeg){:class="img-responsive"}

It should be noted that the notion of relativity isn't exactly new. Galileo had already introduced the concept of *inertia* centuries ago (an object that is in motion stays in motion and an object that's stationary remains stationary, unless acted upon). He also realized that the concept of *absolute* motion is meaningless, and that one can only talk about motion in relation to a frame of reference. 

*Galilean relativity makes sense intuitively for most people. If I'm in a car that's moving at 100km/h and I overtake another car that's moving at 80km/h (relative to the road), I would perceive the relative speed to be 20 km/h.*

Extremely surprising, this is wrong. But in figuring this out, Einstein didn't think in terms of cannonballs falling from high towers and speeding bullets, he was preoccupied with how electromagnetism looks for different observers traveling at relative speeds to one another. 

Before Maxwell, people used to think as electricity and magnetism as two different phenomena. People had known of the existence of strange materials such as magnetite that act on certain metals without having to touch them (permanent magnets create *magnetic* force fields around them). We also discovered electricity and electric fields. We discovered we can create electricity by friction, and XXX showed that lighting *actually is* electricity. But then something interesting happened. In 1820 [Oersted showed](https://en.wikipedia.org/wiki/Oersted%27s_law) that a moving electric charge generates a magnetic field and in 1834 Faraday carried out his famous [induction experiment](https://en.wikipedia.org/wiki/Faraday%27s_law_of_induction) showing that a magnetic field can create an electric current in a wire, so it was clear that the two phenomenons must somehow be related. It was Maxwell who managed to unify the different concepts under one framework which he called *electromagnetism* -- he is actually credited with creating the first unified field theory in the history of physics. His realization was that if a variable magnetic field creates a variable electric field and vice versa, then what you have is a [transverse wave](https://en.wikipedia.org/wiki/Transverse_wave) and using the known values for electric and magnetic permeability, he was even able to calculate the speed at which this wave propagates through space.

![em-wave](/images/em-wave-small.png){:class="img-responsive"}

<br/>
And to quite a lot of people's surprise, the speed was very close to 300 000 m/s, which is what the speed of light was known to be. Maxwell had shown that light is an electromagnetic wave!

So if light is a wave then the natural intuition would be to ask: *a wave propagating through what?* And sure enough, people did set out to find traces of whatever medium light propagates through, a medium which they dubbed a *[luminiferous aether](https://en.wikipedia.org/wiki/Luminiferous_aether)*, the most famous being the Michelson-Morley experiment. 

![em-wave](/images/ether.jpg){:class="img-responsive"}

The result of this experiment was considered very weird because the notion that the Earth was stationary was long ago abandoned. So in order to save the idea, various tweaks would have to be introduced. 

Lorentz had the idea that since electromagnetism mediates interactions between molecules, the fact that the interferometer moves creates a change in the strength of the fields and the distances between atoms contract along the direction of movement. Since light would be going in both directions through the arm and so the relative speeds would be __*v - c*__ and __*v + c*__. Since __*(v - c)(v + c)*__ equals __*v<sup>2</sup> - c<sup>2</sup>*__, so dividing by __*c<sup>2</sup>*__ we get __*1 - v<sup>2</sup>/c<sup>2</sup>*__. Taking the square root of this value, Lorentz calculated what compression factor would ensure no light difference would be detectable in the arms of the interferometer and came up with the following formula:

![em-wave](/images/contraction.svg){:class="img-responsive"}

Similarly, one can come up with a *dilation* relationship for time:

![dilation](/images/dilation.svg){:class="img-responsive"}

This definitely feels quite contrived and after-the-fact-ish. Also Lorentz didn't modify the concept of space, he simply hypothesized that the arm would contract because of the changes in interaction forces introduced by the aether.

Einstein later claimed that the Michelson-Morley experiment had no influence on his thinking, but that he was familiar with the results of other negative ether drift experiments (as well as that of the Fizeau experiment). In his 1905 paper he recalls the Referring to Faraday's experiment, he wrote: 

>It is known that Maxwell's electrodynamics – as usually understood at the present time – when applied to moving bodies, leads to asymmetries which do not appear to be inherent in the phenomena. Take, for example, the reciprocal electrodynamic action of a magnet and a conductor. The observable phenomenon here depends only on the relative motion of the conductor and the magnet, whereas the customary view draws a sharp distinction between the two cases in which either the one or the other of these bodies is in motion. For if the magnet is in motion and the conductor at rest, there arises in the neighborhood of the magnet an electric field with a certain definite energy, producing a current at the places where parts of the conductor are situated. But if the magnet is stationary and the conductor in motion, no electric field arises in the neighborhood of the magnet. In the conductor, however, we find an electromotive force, to which in itself there is no corresponding energy, but which gives rise – assuming equality of relative motion in the two cases discussed – to electric currents of the same path and intensity as those produced by the electric forces in the former case.

![magnet](/images/induction2.jpg){:class="img-responsive"}

We can consider the following cases:
  1. We move the coil over the magnet with speed __*v*__.
  2. We move the magnet inside the coil with speed __*v*__.
  3. Both the coil and the magnet are moving such that the relative speed between them is __*v*__.

In case number one, the current is induced in the coil because Maxwell's field equations say that a magnetic field creates a force only on moving charges. In case number two, moving the magnet creates a variable magnetic field which in turn generates a variable electric field which produces the voltage. But the value for the voltage inside the coil is exactly the same, yet the equations treat these two cases entirely different phenomena and it's clear this bothered Einstein. 

>The idea, however, that these were two, in principle different cases was unbearable for me. The difference between the two, I was convinced, could only be a difference in choice of viewpoint and not a real difference. Judged from the moving magnet, there was certainly no electric field present. Judged from the aether, there certainly was one present. 

If a preferred reference frame such as an aether would exist, having a distinction between the two cases would make sense because we would be able to distinguish the movement of the objects in each case in relation to this frame, but it seems both from experiment and mathematics that only *differences* in speed are detectable, which if one is to take the idea of the aether seriously, must be very strange. Number three is also strange because you cannot use Galilean transformations for speeds and coordinates -- the voltage would vary a little bit and just as Lorentz had done before, Einstein found he had to correct the coordinate transformations using the gamma factor when going from one frame to another to get consistent results.

**tl;dr** The solution of Maxwell's equations is a wave that propagates at speed 

Heavily influenced by Mach's [positivism](https://en.wikipedia.org/wiki/Positivism) and and also being aware of the previous negative aether drift experiments, he made no attempt to justify its existence. He pointed out that since we can't really detect absolute motion in relation to a preferred reference frame, there is no need to assume an aether needs to exists.

He simply postulated that:

1. The laws of physics are the same in all inertial frames of reference.
2. The speed of light is always *c* and doesn't depend on the speed of the observer.

The formulas for space contraction, time dilation and combining velocities arise quite naturally from these two postulates if you work out the math. A very important thing to point out that is he didn't try to *explain* why the speed of light is constant like Lorentz had done before him, he simply required it to be true -- the other predictions are just a consequence of the two postulates.

*In fact, for something that moves at the speed of light, the relative speed of an observer makes no difference!*

Einstein further wrote:

>Thus the existence of the electric field was a relative one, according to the state of motion of the coordinate system used, and only the electric and magnetic field together could be ascribed a kind of objective reality, apart from the state of motion of the observer or the coordinate system. The phenomenon of magneto-electric induction compelled me to postulate the principle of relativity.

So Einstein's major insight was that the phenomena we see are really a byproduct of one's frame of observation (hence the name *relativity*): *what looks like an electric field to an observer is a magnetic field to another.* 

Let's exemplify with another thought experiment using the following setup: assuming we have a wire through which an electric current flows (again with speed __*v*__) and an electrically charged object sitting next to the wire, we can again think about the forces that appear on the object in the two reference frames -- the frame of the electrically charged object near the wire and the frame of the electrons in the wire. Because the electrons in the wire move at a speed in relation the object, space contracts in this reference frame and the overall spatial density is slightly different than that of protons, which means the wire has a net electric charge which acts on the charged object. 