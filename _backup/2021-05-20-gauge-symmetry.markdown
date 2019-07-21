---
layout: post
title:  "Gauge Symmetry In A Nutshell"
description: "Not that long ago, Lawrence Krauss appeared on Rogan's podcast and we got this as a result. Eric Weinstein decided this explanation wasn't good or intuitive enough, so he thought of explaining gauge symmetry in terms of fiber bundles and he brought up a Hopf fibration to exemplify. To people struggling to understand the concept, I doubt it's much help.
"
date:   2019-07-10 09:13:11 +0300
image: "/images/hopf2.jpg"
---
Not that long ago Lawrence Krauss appeared on Rogan's podcast and we got [this](https://www.youtube.com/watch?v=YP-tPE7WO64) as a result. It also didn't take Eric Weinstein long to decide this explanation wasn't good or intuitive enough, so he thought of [explaining gauge symmetry](https://www.youtube.com/watch?v=2xiEEtoa-_4) it in terms of [fiber bundles](https://en.wikipedia.org/wiki/Fiber_bundle) and he brought up a [Hopf fibration](https://en.wikipedia.org/wiki/Hopf_fibration) to exemplify.

An artist's impression of this mathematical object would look something like this:

![crowd](/images/hopf2.jpg){:class="img-responsive"}

To people struggling to understand the concept, I doubt it's much help and also the fact that we're calling it gauge invariance (or gauge symmetry) isn't helping either because what we should be calling it is *local phase invariance*. We owe the term *gauge* to Hermann Weyl and it comes from various railroad gauges -- Weyl was trying to do something Einstein did with his theory of general relativity and show that a quantum theory of electromagnetism would be invariant under arbitrary scale changes, but this turned out to be wrong.

Endless ink has been spilled about what quantum mechanics *means* and it's not something we'll settle anytime soon (nor is it the subject of this article) but because of the nature of the theory (and wave-particle duality), quantum mechanics uses wave functions that ascribe *probability* to events and we   have equations to describe how these functions evolve in time. A fairly localized wavefunction for a particle propagating through space would look something like this the following image. Of course, setting up an experiment that aims to detect whether the particle is there, will not find a spread, it will find a precise location.

![wave](/images/wave.gif)

Whenever we're dealing with waves, we have *amplitudes* and *phases*, so physicists love to use complex numbers because of [Euler's formula](https://en.wikipedia.org/wiki/Euler%27s_formula). It also gives us the unit circle for complex numbers with an amplitude of 1.

![circle](/images/circle.png){:class="img-responsive"}

Regardless of what science popularizers like Krauss tried to do, there is no magic anecdote that will make you understand it and there's no a-ha! moment, because at its core this is a feature of the mathematical underlying model. But before explaining what a "gauge" symmetry is, we need to explain what symmetry is in general mathematical terms and there's a bit of confusion going around: when people think of the term *symmetry*, they think about this sort of thing, but it's important to point out this is a specific kind of symmetry -- it's *mirror symmetry* which is simply *invariance* under flipping the object around an axis (and this symmetry corresponds to that particular axis).

![butterfly](/images/butterfly.jpg){:class="img-responsive"} ![spherical](/images/spherical.png)

A sphere embedded in 3D space has a continuous symmetry -- it's invariant under arbitrary small rotations in any direction. A cube on the other end is invariant under rotations of 90 degrees.

For any location in space at a certain time, the wave function of the Schrödinger equation returns a complex number and its amplitude (length) gives you the probability of finding the particle at that certain location in space. An interesting mathematical tidbit is the fact that changing the *phase* of a complex number leaves its amplitude unchanged but what's even more interesting is that for a field of probability we can do this *at every point in space*, so we say we have a local symmetry! OK, so far so good, it seems there's some redundancy in our description but sometimes too much choice is not a good thing, so we can just settle on a gauge.

Phase is a little bit like deciding when 12:00 noon is, it's essentially arbitrary and we don't really care what time it is as long as the time zones don't have to interact between them.

![timezones](/images/time-zones.png){:class="img-responsive"}

But as soon as different time zones need to interact and you need to define the notion of simultaneity, things get interesting really fast. Say you are a businessman  and you need to send an email to schedule a meeting or you need to travel across time zones -- if you just use your own local time it's going to cause confusions, so what you need to do is correct it depending on the destination time zone. need to know how various time zones relate to one another, something like *this zone connects to this zone and we have a one hour difference, or we have half an hour, or whatever* so you need a *map* -- or in mathematical terms, a [connection](https://en.wikipedia.org/wiki/Connection_(mathematics)). A connection is just a way of describing how the curvature of the surface varies from place to place in terms of how the tangent vectors on the surface vary.

![connection](/images/connection.png){:class="img-responsive"}

So why do we need a connection, can't we tell exactly how a manifold is curved by the way it is embedded in a higher dimensional space? Well, we can, but it turns out we don't have to use an embedding -- in a stroke of genius, Gauss figured out that you can the curvature of a 2D surface just by angles and distances, without the need to consider the 3D space this surface exists in, and the connection is just that -- it tells you how the surface varies. Physics also involves a lot of differential equations(which involve operators such as [gradients](https://en.wikipedia.org/wiki/Gradient) and [curls](https://en.wikipedia.org/wiki/Curl_(mathematics))), which work great in flat (Euclidean) manifolds, but the moment your space has some intrinsic curvature, things become problematic, because you need to know how directions (and the tangent space in general) varies from point to point.

What does this have to do with our Hopf fibration? Well, a Hopf fibration is nothing more than a [3-sphere](https://en.wikipedia.org/wiki/3-sphere) -- we're all familiar with 2D spheres embedded in flat 3D space, but we can construct them in any number of dimensions.

A fiber bundle is nothing more than a cartesian product of spaces - you have your base space and at each point in this space there's another space (these are the fibers): this combination is the bundle. The Hopf fibration defines the 3-sphere as a basic 2D sphere that has a circle at each point, so if we approximate the Earth and we say it's a sphere and we also assume each point on the Earth can set its own time zone, what we get is a Hopf fibration.

*Our wavefunction is a mathematical object that lives in one of these geometrical constructions and the extra degrees of freedom in the bundle represents gauge freedom.*

So why do we care about all this? We care because the real world is not made out of one particle, there's more of them. And the moment you want to describe multiple interacting particles (say you have a bunch of electrons), you can't use Schrodinger's equation anymore, you need to use [quantum field theory](https://en.wikipedia.org/wiki/Quantum_field_theory) which models fields as a set of harmonical oscillators at each point in space (and takes the view that particles are local excitations in this field), so in a sense it resembles a mattress with just a pinch of extra complication to make things interesting. If the springs were just standing there, minding there own business, each oscillating on its own, the field would be gauge invariant no problem, but QFT defines particles differently. Most people are familiar with ![crowd](/images/emc2.svg){:class="formula"} but that just gives you the rest mass of a particle, the actual formula is ![crowd](/images/energy-mom.svg) which also involves momentum and if you pay close attention, it also contains negative energy solutions (which represents antimatter -- the bottom hyperboloid).

![crowd](/images/onshell.png){:class="img-responsive"}

So we want to have our field equations to obey this momentum energy relationship, but at the same time we want them to be gauge invariant because again, we cannot measure wavefunctions -- we can only tell if a particle is there or not. And since our field equations involve derivatives on vector spaces, but if your space is curved you can't compute them as you would in flat space because you need to also take the curvature into account, so you need to correct for this. Which is why instead of normal directional derivatives we use covariant ones -- they are just regular directional derivatives with the extra correction term.
