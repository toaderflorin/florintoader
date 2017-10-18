---
layout: post
title:  "Confused About What Gauge Invariance Means?"
description: "
I'm pretty sure you encountered the term <i>gauge invariance</i> or <i>gauge symmetry</i> if you're into physics, and you most likely can explain what some gauge symmetries like parity or time reversal symmetry are, but what exactly does the gauge in gauge symmetry or invariance refer to? I will try to give a simple ex<planation. The term <i>gauge</i> was coined by Hermann Weyl, and the idea is pretty simple..."
date: 2017-10-18 10:13:11 +0300
---
I'm pretty sure you encountered the term *gauge invariance* or *gauge symmetry* if you're into physics, and you most likely can explain what some gauge symmetries like *parity* or *time reversal symmetry* are, but what exactly does the "gauge" in gauge symmetry or invariance refer to? I will try to give a simple explanation. The term "gauge" was coined by Hermann Weyl, and the idea is pretty simple: in physics, there are certain parameters which are set by us, such the origin of the coordinate system, or the lowest potential energy level in the system etc.

*What we care in a gauge theory is relations or differences between objects (or particles).*

![magnetic field](/images/voltage.gif){:class="img-responsive"}

One such example is measuring the tension between two points in a wire. As you can see, the device has two probes and the voltage can be calculated as V<sub>1</sub>-V<sub>0</sub>, where V<sub>0,1</sub> are the potentials of the two points. Keep in mind that the meter can only measure differences, so for convenience we can consider V<sub>0</sub>=0 and V<sub>1</sub> is going to be our tension. You can think of V<sub>0</sub> as the "frame of reference", to which you are measuring everything else.

Here's another example: you can perform drop a ball either on the surface of the Earth or in a plane (provided the plane flies at a constant speed and the altitude isn't too high that the gravitational constant changes significantly), the laws are the same regardless of the total potential of the system (which is higher for the plane because it's at high altitude). The ball will take the same time to drop to the floor, regardless. This is a special case of gauge invariance, it's *invariance under translation in relation to altitude* because we moved our system by some amount up in the air, but we got the same behavior of the ball.

In general, a "symmetry" refers to the property of an object to be invariant (not to change) under an operation. I've wrote about various gauge symmetries at length [here](http://florintoader.net/accounting). A gauge theory is a quantum field theory who's Lagrangian (the equation that tells us how the field evolves over time) has one ore more gauge symmetries.
