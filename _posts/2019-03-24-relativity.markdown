---
layout: post
title:  "What Exactly Was Bothering Einstein?"
description: "In 1905, a young Albert Einstein put out a paper which he called <i>Zur Elektrodynamik bewegter Körper (On The Electrodynamics Of Moving Bodies)</i> that would forever change the way we think about space and time and among other things, it says that space contracts, time dilates and even the notion of simultaneity is relative and observer dependent.
"
date:   2019-03-24 11:13:11 +0300
image: "/images/einstein.jpeg"
---
In 1905, a young Albert Einstein put out a paper which he called *Zur Elektrodynamik bewegter Körper (On The Electrodynamics Of Moving Bodies)* that would forever change the way we think about space and time and among other things, it says that space contracts, time dilates and even the notion of simultaneity is relative and observer dependent.

And as strange as that sounds, you have to consider the fact that nobody walks around and thinks <i>hmm, I think that if I move at a certain speed relative to the Earth, time would have to pass slower for me</i> without a very strong reason, yet Einstein's theory says this absolutely must happen, it gives us the *exact rate* at which it happens and we can also build very precise atomic clocks that can measure differences in the passage of time and they are in perfect agreement with predictions.

![einstein](/images/einstein.jpeg){:class="img-responsive"}

And of course, relativity isn't exactly new -- we take it for granted now, but before Galilei, people actually believed that heavier objects fall faster than lighter ones. He also introduced the concept of *inertia* centuries ago (an object that is in motion stays in motion and an object that's stationary remains stationary, unless acted upon). He also realized that the concept of *absolute* motion is meaningless and that one can only talk about motion in relation to a frame of reference.

*Galilean relativity makes sense intuitively for most people. If I'm in a car that's moving at 100km/h and I overtake another car that's moving at 80km/h (relative to the road), I would perceive the relative speed to be 20 km/h.*

Extremely surprising, this is wrong. Yet in figuring this out, Einstein didn't think in terms of cannonballs falling from high towers and speeding bullets, he was preoccupied with how electromagnetism looks for different observers traveling at relative speeds to one another.

In fact, before Maxwell people used to think as electricity and magnetism as two different phenomena. The existence of strange materials like magnetite that act on certain metals without having to touch them was known for a long time and we also discovered electricity and electric fields -- non other than Benjamin Franklin proved that lighting *actually is* electricity with his famous key and kite experiment. Then something interesting happened: in 1820 [Oersted showed](https://en.wikipedia.org/wiki/Oersted%27s_law) that a moving electric charge generates a magnetic field and in 1834 Faraday carried out his famous [induction experiment](https://en.wikipedia.org/wiki/Faraday%27s_law_of_induction) showing that a magnetic field can create an electric current in a wire, so it was clear that the two phenomena must somehow be related. It was Maxwell who managed to unify the different concepts under one framework which he called *electromagnetism* -- he is credited with creating the first unified field theory in the history of physics. His realization was that if a variable magnetic field creates a variable electric field and vice versa, then what you have is a [transverse wave](https://en.wikipedia.org/wiki/Transverse_wave) and he was even able to calculate the speed at which this wave propagates through space.

![em-wave](/images/em-wave-small.png){:class="img-responsive"}

<br/>
And to quite a lot of people's surprise, the speed was very close to 300 000 m/s, which is what the speed of light was known to be.

Light was known to have wave like properties for quite some time and naturally it was assumed it propagates through some kind of medium, a medium which was called the [luminiferous aether](https://en.wikipedia.org/wiki/Luminiferous_aether). And sure enough, people did set out to find traces of this aether, with the most famous of the attempts being the Michelson-Morley experiment. It was know at the time that the Earth was moving around the Sun at about 100 000 km/h and that the Sun was also moving around the galactic center, so what Michelson and Morley did was they tried to measure the *difference* in speed between light coming directly from the Sun and light moving perpendicularly using an [interferometer](https://en.wikipedia.org/wiki/Interferometry), in the hope they would be able to infer what that absolute speed of the Earth might be.

![em-wave](/images/ether.jpg){:class="img-responsive"}

*To their dismay. they didn't find any*.

The result of this experiment was considered very weird because the notion that the Earth was stationary was long ago abandoned. So in order to save the idea, various tweaks to the aether theory had to be introduced -- one such idea was the *aether drag*, which speculated that as objects move, they drag this aether along which would explain why no difference in speed was detected. Another idea, coming from Hendrick Lorentz, was that since electromagnetism mediates interactions between molecules (and movement of particles affects electromagnetic forces), the interferometer arm contracts in length in the direction of motion of the Earth in such a way that no difference in speed is detectable -- the compression factor would have to be ![factor](/images/factor.svg) if you work out the math. He also came up with the concept of [local time](https://en.wikipedia.org/wiki/Lorentz_ether_theory#Local_time) which implied a dilation relationship (to which he imputed no physical meaning, he simply regarded it as a calculation tool).

Einstein would later go on to claim that the Michelson-Morley experiment had no influence on his thinking, but that he was familiar with the negative results of other ether drift experiments (as well as that of the Fizeau experiment, which disproved the aether drag hypothesis). In his 1905 paper, referring to Faraday's induction experiment of 1834, he wrote:

>It is known that Maxwell's electrodynamics – as usually understood at the present time – when applied to moving bodies, leads to asymmetries which do not appear to be inherent in the phenomena. Take, for example, the reciprocal electrodynamic action of a magnet and a conductor. The observable phenomenon here depends only on the relative motion of the conductor and the magnet, whereas the customary view draws a sharp distinction between the two cases in which either the one or the other of these bodies is in motion. For if the magnet is in motion and the conductor at rest, there arises in the neighborhood of the magnet an electric field with a certain definite energy, producing a current at the places where parts of the conductor are situated. But if the magnet is stationary and the conductor in motion, no electric field arises in the neighborhood of the magnet. In the conductor, however, we find an electromotive force, to which in itself there is no corresponding energy, but which gives rise – assuming equality of relative motion in the two cases discussed – to electric currents of the same path and intensity as those produced by the electric forces in the former case.

![magnet](/images/induction2.jpg){:class="img-responsive"}

Faraday's experiment consisted of a magnet and a coil of wire and he showed that a magnet inside the coil creates an electric current in the wire of the coil. Einstein was however concerned with what happens if we move either of the two objects.

We can consider the following cases for relative motion:
  1. We move the coil over the magnet with speed __*v*__.
  2. We move the magnet inside the coil with speed __*v*__.
  3. Both the coil and the magnet are moving such that the relative speed between them is __*v*__.

In case number one, the current is induced in the coil because Maxwell's field equations say that a magnetic field creates a force only on moving charges. In case number two, moving the magnet creates a variable magnetic field which in turn generates a variable electric field which produces the voltage. But the value for the voltage inside the coil is exactly the same, yet the equations treat these two cases entirely different phenomena, which clearly bothered Einstein.

>The idea, however, that these were two, in principle different cases was unbearable for me. The difference between the two, I was convinced, could only be a difference in choice of viewpoint and not a real difference. Judged from the moving magnet, there was certainly no electric field present. Judged from the aether, there certainly was one present.

If there was a preferred reference frame such as an aether, having a distinction between the two cases would make sense because we would be able to distinguish the movement of the objects in each case in relation to this frame, but it seems both from experiment and mathematics that only *differences* in speed are detectable, which if one is to take the idea of the aether seriously, must be very strange. 3. is also strange because you cannot use Galilean transformations for speeds and coordinates -- the voltage would vary a little bit when compared to 1. and 2. and Einstein found he had to correct the coordinate transformations with the same factor as Lorentz had done before him.

Heavily influenced by Mach's [positivism](https://en.wikipedia.org/wiki/Positivism) and also being aware of the negative results of the previous aether drift experiments, he made no attempt to justify its existence. He pointed out that since we can't really detect absolute motion in relation to a preferred frame of reference, there is no need to assume there is one.

He simply postulated that:

1. The laws of physics are the same in all inertial frames of reference.
2. The speed of light is always *c* and doesn't depend on the speed of the observer.

The formulas for space contraction, time dilation and combining velocities arise quite naturally from these two postulates if you work out the math. A very important thing to point out is that he didn't try to *explain* why the speed of light is constant like Lorentz had done before him, he simply required it to be true -- the other predictions are just a consequence of the two postulates.

Einstein further wrote:

>Thus the existence of the electric field was a relative one, according to the state of motion of the coordinate system used, and only the electric and magnetic field together could be ascribed a kind of objective reality, apart from the state of motion of the observer or the coordinate system. The phenomenon of magneto-electric induction compelled me to postulate the principle of relativity.

Let's exemplify with another thought experiment using the following setup: assuming we have a wire through which an electric current flows (again with speed __*v*__) and an electrically charged object placed next to the wire, we can again think about the forces that appear on the object in the two reference frames:

  1. In the wire's frame of reference, the electrons move at speed __*v*__, so their frame contracts which changes the net charge density of the wire from neutral to negative and this in turn acts on the charged object.
  2. In the current's frame of reference, the positive ions in the wire now appear to be moving (so their frame contracts) and so the wire net electric charge density is positive, which means the electric force points in the other direction. But because the charged object also appears like it's moving, there is a magnetic force that counteracts the electric force and the sum of these two forces is exactly the same as for number 1.

Einstein's major insight was that the phenomena we see are a byproduct of one's frame of observation (hence *relativity*): *what looks like an electric field to me is a magnetic field to aunt Marge, if she's moving at a relative speed that's big enough.* But there's something else that's even more interesting: if you take the Lorentz transforms and you apply them to something that moves at the speed of light (essentially any elementary particle in the absence of a Higgs field), they tell you that space contracts to zero and time dilates to infinity and pretty much stops flowing.

![dilation](/images/time-dilation.png){:class="img-responsive"}

Does that mean that these notions are meaningless for individual particles? If so, what are space and time?
