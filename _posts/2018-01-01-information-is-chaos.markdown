---
layout: post
title:  "Information Is Chaos"
description: "Riddle me this: which image do you think has more information, the one on the left or the one or the right?
If you guessed the one on the left, you were correct. Please note I am not talking about *useful information* (as in useful to humans), I was talking about pure information.
"
date: 2018-01-03 11:13:11 +0300
categories: science
---
Riddle me this: which image do you think has more information, this one?

![image-title-here](/images/horse.jpg){:class="img-responsive"}

Or this one?

![image-title-here](/images/noise.jpg){:class="img-responsive"}

If you guessed the first one, you were wrong. Please note I am not talking about *useful information* (as in useful to us humans), I was talking about pure information as in bits. Which is interesting--but first, let us first look at how this notion of "bits" came about.

### A Bit Of Information Theory
With the invention of the telegraph, people could communicate across long distances very fast using Morse code and then phone lines. But as you probably know from the days of analogue TV signal cables, the quality of the signal isn't that great. The reason for this is simple: over a certain distance, losses and interference from the outside weaken the signal in the cables and it needs to be reamplified--this however also introduces noise. This problem was so bad that sending a telegram from the West coast to the East coast (or vice versa) was problematic because of the interferences in the signal were so bad, the operator at the other side of the line couldn't understand the meaning of the message in Morse code. Of course, this method of communication has an interesting benefit: as long as the intention of the person sending the message can be still understood, the message can be cleaned up and resent.

So let's say you were trying to send a telegram from New York to Seattle. An operator on the other side of the continent might have trouble making out the beeps because of all the noise, but why not send the signal to a closer destination where it's still intelligible and the operator there can forward it?

*Actually this is the gist of how digital signals work. Because you know that the possible values are only ones and zeros, if you are getting something like 0.971 on the line you can safely assume it's 1, so it's very easy for relays to clean up the signal.*

Also, the transformation from an analogue signal to a signal composed out of 0 and 1 is not that hard to do. Let us now look at the specifics. Say we have a sequence of 4 bits. This means there will be a total of 16 possible combinations.

*states = 2 x 2 x 2 x 2 = 2<sup>4</sup>*

If we know the total number of distinct states a system can be in, we can figure out how many bits we need to encode that state like so:

*bits = log<sub>2</sub>(states)*

We'll get back to bits in a few moments, but first we need to take...

### A Small Detour In Our Story
This might look familiar:

![image-title-here](/images/normal_distribution.png){:class="img-responsive"}

This is commonly referred as a "bell curve" or normal distribution (Gaussian distribution) and is commonly used statistics. You might have seen it in charts showing IQ distribution among the population, but where does it come from?

Think of it this way: if you toss two dice, there are a lot more ways to get a value in the middle, than to get 2 or 12. When the number of dice goes to infinity, the individual blocks disappear and the curve becomes continuous.

![image-title-here](/images/probab3.jpg){:class="img-responsive"}

*What Gaussian distribution essentially says there is a lot of ways you can be mediocre.*

Keep this in mind when we look at real physical application.

### Boltzmann Entropy
When scientists were trying to figure out what heat is, they initially envisioned it as some sort of fluid that can flow between warm objects (possessing this fluid) and cold objects, or warm parts of an object to cooler parts until the "pressure" of this fluid equalizes. Eventually they settled upon the idea that heat is actually an internal jittering motion of the constituents of matter, but nonetheless temperature tends to equalize in an isolated system. Also, temperature is not that much different than pressure--if you put a bunch of gas in a container (say in a corner), the gas eventually spreads out and the pressure equalizes.

Why is that? Well the answer is simple: there are a lot more ways for the particles making up the gas to be arranged in an uniform way in the container than for them to be in a special case all bundled up in a corner (as you've seen from the dice example). Of course, the pressure repartition isn't exactly uniform--there are small variations, but they happen around the median value.

Ludwig Boltzmann formalized the concept of "entropy" by defining it as

![image-title-here](/images/boltzmann.svg){:class="img-responsive"}

where *W* is the total number of indistinguishable microstates a system can be in and *k<sub>B</sub>* is a proportionality constant.
