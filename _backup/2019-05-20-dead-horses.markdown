---
layout: post
title:  "A Tale Of Chance And Beating Dead Horses"
description: "I initially wanted to call this article <i>A Tale Eigenvalues Of Unitary Hermitian Operators And Beating Dead Horses</i>, but I realised that if I do that, nobody would read the article (not that many people do, anyway), so I decided againsted it."
date:   2019-05-16 11:13:11 +0300
image: "/images/coin.jpeg"
---
I initially wanted to call this article *A Tale Eigenvalues Of Unitary Hermitian Operators And Beating Dead Horses*, but I realised that if I do that, nobody would read the article (not that many people do, anyway), so I decided againsted it. 

Richard Feynman famously said that if you think you understand quantum mechanics, you don't really understand quantum mechanics and I've been wondering if that's really the case -- I mean, it's cool to cool to quote Feynmann if you want to look smart and it's cool to say that particles are in multiple places at the same  time (if you say tell me that, I would ask you to explain to me what you think a particle is). Quantum mechanics is a model and I think we understand it well, we just cannot agree what it means.

*It's reality we don't understand.*

Let's assume we have a spin half particle, say an electron (which is essentially a little bar magnet). If you put this electron in a magnetic field, based on its magnetic moment, it will be deflected, just like a normal magnet would. But what's interesting is this magnetic moments only has two values relative to a direction.

You don't see the electron, what see a little light bulb lighting up.

![einstein](/images/coin.jpeg){:class="img-responsive"}

In quantum mechanics we model quantum states as vectors in finite or infinite [Hibert spaces](https://en.wikipedia.org/wiki/Hilbert_space) ([Fock spaces](), if we're dealing with multiple particles). The word "dimension" gets thrown around a lot but *dimentionality* is a simple concept, it simply refers to the number of independent degrees of freedom an object or system has.

So let's say we have our standard gedanken experiment guinea pig, but instead of coupling its fate to a radioactive atom, we tie it to the spin of our electron.

![einstein](/images/cat.jpg){:class="img-responsive"}

In Dirac notation, we would write it down like this, which means our cat is half dead - half alive.

![einstein](/images/cat-dirac.jpg){:class="img-responsive"}

Let's get back to our vector in 3D space. We can apply an operator on it (say a rotation around the origin by a certain angle along a certain direct) and we get another vector:

![einstein](/images/operator.svg){:class="img-responsive"}

We can do a little [gauge fixing](https://en.wikipedia.org/wiki/Gauge_fixing) here and say that spin up always points, well up:

![einstein](/images/bloch.svg){:class="img-responsive"}


