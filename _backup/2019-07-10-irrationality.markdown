---
layout: post
title:  "The Rationale Behind Human Irrationality"
description: "<i>You do not need science to survive, but you need to survive to do science</i> a wise man once said, and truer words have never been spoken-because from an evolutionary point of view when shit/fan colission is imminent, making a good enough decision REALLY FAST is better than making the best decision if that takes a few minutes."
date:   2019-07-10 11:13:11 +0300
image: "/images/brains.jpg"
---
<i>"You do not need science to survive , but you do need to survive to do science"</i> a wise man [once said](https://medium.com/incerto/how-to-be-rational-about-rationality-432e96dd4d1a) and truer words have never been spoken -- because from an evolutionary point of view reacting fast to a situation is

*The brain doesn't do backtracking, it mostly uses greedy strategies.*

If the brain had an architecture, it would be of the [Big Ball Of Mud](https://blog.codinghorror.com/the-big-ball-of-mud-and-other-architectural-disasters/) variety. In general, finding the best solution involves exploring the whole solution space which is an O(n<sup>m</sup>) affair [complexity-wise](https://discrete.gr/complexity/), while greedy algorithms are O(n), not to mention that even your average brain consumes a lot of glucose, so ideally you'd prefer to take a shortcut and for your brain to simplify things or get answers from working memory whenever possible.

<iframe width="740" height="415" src="https://www.youtube.com/embed/UBVV8pch1dM" frameborder="0" allowfullscreen></iframe>

Derek has a wonderful explanation of the logical brain and the shortcut brain. But then he always has wonderful explanations.

### Agency, Evolution And Neural Networks
The Mayans thought they had to sacrifice virgins to the gods in order for the sun to continue rising each morning. Some people refuse to fly on Friday the 13th. You or I might look up at the sky, see a cloud that looks like a rabbit and think *"how quaint, how'd that sh#t get up there?"* etc.

![rabbit-cloud](/images/rabbit-cloud.jpg){:class="img-responsive"}

Regardless, our brains have a tendency to see patterns or divine [agency](https://en.wikipedia.org/wiki/Agency_(philosophy)) where there is none (from rodent lookalike cumulus to bad omens in medieval times) and it's interesting to think why and how that came about from an evolutionary perspective.

Let's first look at an artificial neuron which models (sort of) a real life one. A schematic of it would look like this:

![neuron-diagram](/images/neuron-diagram.png){:class="img-responsive"}

The output of a neuron can function as the input for another one and so complex networks can be created. In our case, a neuron is just a function that does a weighted sum of all its inputs and if the result is *greater* than a certain threshold value, it produces this value as an output, otherwise it outputs zero. Now here's where things begin to get interesting: the value of this threshold is very important because if it's too high, the neurons will fail to fire and detect patterns but if it's TOO LOW, we are going to have a lot of false positives.

![lioness](/images/lioness.jpg){:class="img-responsive"}

The activation thresholds in the neurons making up our brains are largely dependent on evolutionary proccess and here's the thing: they have evolved to err strongly on the side of false positives because mistakenly taking something moving in a bush for a lion is harmless, but actually missing the silhouette of a lion would have been fatal. Which means we have a propensity to see patterns where there aren't any.

<i>
This also includes creating elaborate explanations like religious beliefs and superstitions.
</i>

### The Triune Brain Theory
According to this theory, the human brain is made out of three "layers" and those layers are interdependent. The *reptilian* part of the brain is responsible for basic locomotion functions such as standing upright, the fight / flight response and the regulation of the endocrine system. The *limbic system* is responsible for emotions, such as love, fear, envy and so on. And finally, we have the *neocortex* which is the part of the brain that's responsible for conscious thought.

![triune](/images/triune.png){:class="img-responsive"}

<i>
You can think of the brain like being not that much unlike a 3-tier software application where one layer sits on top of the other.
</i>

Dwell on that for a little while.

You'd be tempted to assume that people are rational beings, but that turns out not to be true--in fact people are *backwards-rational* and I'll explain in a minute exactly how the whole thing works. It is known that individuals with brain trauma on the limbic system level have a hard time making decisions such as deciding what to it or where to go on vacation. so the neocortex might have a lot of computational power but it needs the limbic system to assign an emotional desirability "score" for the possible outcomes it's evaluating.

You might have noticed something interesting: trying to convince people that have a strong opinion on a subject with logical counter arguments or physical proof actually has the opposite effect--it makes them cling to their initial position on the topic even more stubbornly. Moon landing conspiracy theorists, for example, when presented with photos from Chinese satellites of the Apollo gear on the Moon, usually come up with complex explanations on how these photos could also have been faked. And this is where *cognitive dissonance* comes into play: if a person is presented with evidence that contradicts a moral set of values (which is essentially just the emotional operating system of that person) that person will do quite a lot of backwards justification to salvage that belief system.

There's a widely circulated story of King Frederick the Great, the [Potato King](https://en.wikipedia.org/wiki/Frederick_the_Great) (which might be largely anecdotal, but very instructive nonetheless) who famously tried to convince his subjects to include the newly imported potato into their diets in order to resolve the problem of famine that was plaguing his kingdom at the time, to which they responded <i>"not even our dogs would touch them so what use are they to us?"</i>. The king then proceeded to declare the potato as being "royal" and only fit for royal consumption, while at the same time instructing his royal guards to be lax in the guarding of the royal potato fields. Lo and behold, reverse psychology was just as effective then as it is now, and the commoners (wanting to get their hands on the forbidden fruit) started to steal from the king's garden and grow their own, until the king was "forced" to concede that the potato isn't as royal as he once claimed. Problem solved.
