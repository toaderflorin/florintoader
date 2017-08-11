---
layout: post
title:  "Special Relativity Made REALLY Simple"
description: "At the end of the 19th century, it was already known that light because it exhibits all sorts of wave like effects such as interference etc. and Maxwell already showed that light is an electromagnetic wave.
"
date:   2017-08-09 21:13:11 +0300
categories: jekyll update
---
At the end of the 19th century, it was already known that light was a wave of *something* because it exhibits all sorts of wave like effects such as interference etc. and Maxwell already showed that light is electromagnetic in nature. So if light was a wave, it must propagate through a medium - the scientists at the time postulated that there is something called an ether that permeates all space. It was also known that not only the Earth moves around the Sun, but also the Sun moves around the center of the galaxy and so forth, so they wanted to figure out what's the absolute speed of our planet / solar system in relation to this ether which was thought to be stationary and would provide a cosmic reference frame. 

![image-title-here](/images/ether.png){:class="img-responsive"} 

Michelson and Morley devised an interesting experiment where they tried to compare the speed of light in different (perpendicular) directions using a very sensitive interferometer. To their surprise, they found none. Surely the Earth couldn't have been stationary, mankind has given up on that idea a long time ago. Everybody was perplexed by the result, and try as they mind, they couldn't figure out what was wrong with the experiment.They improved the apparatus, but to no avail. At one point, Hendrick Lorentz even suggested that objects contract slightly over their trajectory, to explain why the Michelson Morley interferometer measures the exact same speed.

One person that wasn't surprised by the results of the experiment was Einstein. He was studying Maxwell's equations of electromagnetism and noticed something interesting - the speed which the electromagnetic wave propagates doesn't depend on the speed of the observer. Sure, an observer moving in the same of the direction of the lightbeam causes a shift in the observed frequency of the light (the waves appear compressed, this is called the Doppler shift), but not in the speed. Light can never stay still!

*No matter how fast you are moving, even if you are moving at 99% the speed of light, the wave always travels at 300 000 m/s relative to you.*

This is why this is hard to comprehend for most people. One would assume that if you are travelling at 70% of the speed of something, you perceive the speed of that thing, whatever it might be to be 30% relative to you. This is how Newton described things, and this aproximation works at low speeds, say the speed of a rock or arrow flying towards you. Keep in mind that our brain evolved for millions of years to keep us alive (and the conditions back then were much different then they are now). This is why it's hard for you to picture what I'm talking about in your head, but trust me, you're not the only one. But let's not get side-tracked.

To figure out of the implications of a constant speed of light, Einstein came up with the following thought experiment: Imagine a moving platform. One observer is staying in on top of the platform, and the other one is standing on the side. Two light bulbs on the side on switch on. This is what the first observer sees: 

<img src="/images/simultaneity1.gif" width="650">

And this is what the second observer sees, keeping in mind that light always moves at the same speed, regardless of the speed at which the platform moves.

![image-title-here](/images/simultaneity2.gif){:class="img-responsive"} 

To the first observer, the light bulbs appear to have been turned on at the same time. But to the second, it seems there is a delay. Simultaneity is relative! If the platform would have moved the other way, the order of events would have appeared to be different. At first look, it doesn't make sense, it doesn't seem logically consistent. So we have quite a bit of conudrum on our hands. Hendrick Lorentz tried to solve this inconsistency by postulating that moving objects contract slightly on their direction of movement and time slows down a little bit for them. No, it wasn't Einstein that came up with these!

Here are the Lorentz transforms for space contraction and time dilation that we are so familiar with:

![image-title-here](/images/lorentz.gif){:class="img-responsive"} 

Einstein hated this. He thought it was contrived - what we developers call a hack, because it was so ugly and unelegant. Here's what he came up with:

1. The speed of light is constant and *fundamental*.
2. Space and time are *not absolute*, they are intertwined and they form one single 4D entity.

I will explain what that means in a minute, but first, think about this: in space, there is no absolute up, or down or whatever. Up is just relative to wherever the astronaut's head is pointing at.

![image-title-here](/images/up.jpg){:class="img-responsive"} 

So acording to Einstein, time is just a position in a 4D space called Minkowski space. Here's what a Minkowski space with one time dimension and one spatial dimension would look like:

![image-title-here](/images/planes.png){:class="img-responsive"} 

An observer's *NOW* would be just a slice in this simple 2D spacetime. But because observers moving at different speeds perceive different things to be simultaneous, what's in that slice differs based on the speed and the direction of the observer. The Lorentz transformations are just projections on various axes in this Minkowski spacetime. You can also see that the notion of one meter, or one second is meaningless because they are relative. Even the order of events which events happen is relative to the observer, so time the flow of time in the way we perceive it sort of an illusion. An interesting by product of this is that space time *just is*. Time is just a coordinate or position in space time. *Now* is not an absolute concept, it's just now *for me*, and just for this version of me who's 34 years and a couple of months old. For somebody else 5 years from now, *now* is different, because it is just a postion of spacetime.

The Lorentz transformations are a byproduct of *rotating the camera* (if you will) in this 4D space.

(We know for example that things in the future can affect things in the past, thanks to delayed choice quantum eraser experiments, but I'm not going to get into that here, because that's going to complicate things a great deal - so the concept of time is quite fuzzy)

Is everything predestined?