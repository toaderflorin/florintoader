---
layout: post
title:  "Quantum Mechanics 101"
description: "When I was trying to learn guitar, the first thing that I learned was the scales. You know, to play solos like Jimi or Slash, and the first one I picked up was the A minor scale..."
date: 2017-08-10 21:13:11 +0300
categories: jekyll update
---
The thing people find most confusing about quantum mechanics is the *wave-particle duality*, namely how the individual blocks of matter can be waves and particles at the same time. I really hated writing this article because it's really dry and technical, but to get to the juicy and interesting stuff, you need a minimal understanding of some core concepts.

### The Double Split Experiment ###

 To showcase wave particle duality, let's look at the double split experiment, which is probably one of the most famous physics experiments of all time. It  is quite simple: it consists of an electron gun firing electrons **one by one**, a detector screen at the other end, and a plate in the middle with two slits cut out of it close to one another. Everytime a particle is fired it can either go through one of the slits, or hit the plate. If it goes through, it's going to hit the detector screen and leave a mark.

 Watch the following animation:

<iframe width="740" height="415" src="https://www.youtube.com/embed/Xmq_FJd1oUQ" frameborder="0" allowfullscreen></iframe>

If electrons were like little balls, you'd expect to see to clumps of points. What you see instead is an interference pattern made out of individual points, like this:

![image-title-here](/images/buildup.png){:class="img-responsive"} 

The reason this is strange is because we are sending electrons through **one by one**. So what exactly interferes with what? Is half of the electron going through one slit and half of it through the other? 

*Moreover, if we place a detector at one of the slits, the interference pattern is doing to dissappear! Really weird stuff!*

According to the Copenhagen interpretation of quantum mechanics, we can never deterministially predict what a particle will do, we can only predict the probability of it doing something in the form of a *wave spreading through space*. For the mathematically minded, we're talking about a field of complex numbers that permeates all space. This means we have a *phase* and an *amplitude* for each point in space. Here's what a complex number looks like:

![image-title-here](/images/complex.png){:class="img-responsive"} 
 
*i is the square root of -1, and y is the imaginary part of the complex number. The reason is called imaginary is because there obviously isn't any real number that multiplied with itself gives us -1.*

The phase refers to the angle of the segment and the amplitude refers to length of the segment. The phase is what allows us to achieve constructive / destructive interference effects. The probability of a particle being in a specific area is given by the integral of the amplitude of the field over that specific area. The Schrödinger equation tells us how this *wave of probability* evolves in time. The wave of a particle propagating through space would look something like this:

![image-title-here](/images/wave.gif){:class="img-responsive"} 

The amplitude of this wave (which is always a positive number) will give you the rough position of where the particle is located. 

### Heisenberg's Uncertainty Principle ###
Here's an interesting by product of the Schrodinger equation: the more localized the wave for the position of the particle, the bigger the spread for the speed of the particle (the first order derivative in relation to time and viceversa).

![image-title-here](/images/schrodinger.png){:class="img-responsive"} 

This can be easily derived out of the Schrödinger equation but I won't bother because nobody is going to read this. But it puts a limit on precisely we can measure the location and the speed of a particle at the same time:

![image-title-here](/images/uncertainty.svg){:class="img-responsive"} 

Here's how you can interpret this: if you want to know the position of a particle, you need to shine light on it. And the more precisely you want to measure the position, the higher frequency photons you need to use, because these have a higher resolving power. But the higher the frequency, the higher the energy of the photon and the higher the momentum of the particle imparted on the particle. In fact if you whant to know the postion of the particle with arbirtrary precision, you need to use photons so high in energy that they are going to bump the particle so hard that in the next moment it can be anywhere else in the universe! Of course, there's a bit more to this, but I am trying to keep things simple.

Now if you're like me, you're wondering how can a particle be in two places at the same time and interact with itself or how can a *wave of probability* interact with the edges of the slits which are material in nature etc. Stay tuned...