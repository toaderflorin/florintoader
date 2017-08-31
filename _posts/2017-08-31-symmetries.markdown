---
layout: post
title:  "Surprinsingly, Providence Doesn't Involve Accounting"
description: "The normal rules of physics don't apply to the quantum world, but if you're reading this, I guess you already knew that. One example of this is particles going through small potential barriers without having the energy to do so, like in this example..."
date: 2017-08-31-energy 10:13:11 +0300
categories: jekyll update
---
You see, the normal rules of physics don't apply to the quantum world, but if you're reading this, I guess you already knew that.

<iframe width="740" height="415" src="https://www.youtube.com/embed/K64Tv2mK5h4" frameborder="0" allowfullscreen></iframe>

<br />
One example of this is *quantum tunneling*, the propery of particles being able to go through small potential barriers without having the energy to do so, like in this example. The wave function of the particle hitting the obstacle looks the one in the picture below. As you can see, most of the wave reflects back, but a part of it goes through, so there is a *probability* the particle crosses the barrier. 

![image-title-here](/images/tunneling.gif){:class="img-responsive"} 

It seems that the particles care about energy but only somewhat... and nature seems pretty forgiving in what it lets them do and don't do. But what would you say if I told you that there isn’t such a thing as fundamental law in nature saying that energy in system must be conserved? 

### Just What Is Energy? First, A Teensy Bit Of Calculus... ###
When Newton figured out the moon orbiting around the Earth, and objects falling on Earth have the same cause, he didn’t have a computer to do computations with, so he invented calculus — which is just derivatives and integrals.

![image-title-here](/images/derint.gif){:class="img-responsive"} 

Integrals are an analytical way of summing stuff up. Derivatives give you the variation of a function and integrals are the opposite of derivatives. For example:

1. Speed is the variation of the position of an object in relation to time — you can get the speed of the object at any point in time if you know it’s position, by differentiating it in relation to time.

2. Alternatively, you can get the position of the object at any time, if you know the speed at all times, by integrating or summing up the speed over time.

Let’s consider a specific problem: throwing a rock into the air at a specific angle.

![image-title-here](/images/trajectory.png){:class="img-responsive"}

There’s a number of questions we could ask, for example: 

1. Where is the rock and/or what speed it has at moment **t**? These are *time dependent* questions.

2. How high will the rock get into the air, how far away from the thrower will the rock land? etc. These are *time independent* questions.

And if you want to answer *time independent* question you could of course put the equations of motion that describe the [dynamics of the system](https://en.wikipedia.org/wiki/Lagrangian_mechanics) (which would normally consist of a set of time dependent differential equations) into a computer, simulate what happens and see the end result. Of course they didn't have computers back in the day, like I said, so they had to be a bit more inventive. Turns out if you integrate the equation of motion over time, you can get rid of the **t** parameter and get the answers to your question. That's what [Hamiltonian mechanics](https://en.wikipedia.org/wiki/Hamiltonian_mechanics) is. The Hamiltionian gives us the *total energy* of a system.

*Energy is just a mathematical gimmick, it’s not a real physical thing. It’s simply a sum. For example, kinetic energy is the integral of momentum.*

### God Is Not Counting ###

*The law of conservation of energy* just says this sum stays constant over a period of time in BIG (non-quantum) systems. Small quantum systems violate energy conservation laws ALL THE TIME. In fact, let’s have a look at the Heisenberg uncertainty principle: 

![image-title-here](/images/heisenberg.gif){:class="img-responsive"} 

In a nutshell, it tells us that we cannot know both the position and the speed of a particle with arbitrary precision, but if we tweak the mathematics around a little bit we get the time-energy uncertainty relation which is mathematically equivalent but says:

*...particles can violate the law of energy conservation, but the more they violate this law the less stable the particle is.*

That’s interesting and **very weird**, but it turns out there would be a way to understand it that makes logical sense, because quantum mechanics is inherently random. Let me use an analogy: let’s say we he have a physical system consisting of two players, and each of them starts out with $100. They toss a coin and if it’s heads, player A gives player B $1, and if it’s tails, vice-versa. If this coin would be a perfectly symmetric coin 50%-50% (most real coins are not), the game could theoretically go on forever with both player hovering around $100, give or take — so we can say their money is conserved. Now if the coin is biased on the other hand, meaning there is a slight asymmetry, one player would start to gain money over time while the other would lose over the long term. The bigger the asymmetry of the coin, the faster the game would be over, the players would each be on their own merry way and our physical system will disintegrate. Nobody's up there counting and saying "hey, we got 3 heads in a row, it's time for tails". It's just random, only the repartition is 50%-50%. God's not an accountant.

So what does this have to do with the real world? First, we know that particles are stable ripples in quantum fields. Second, we know that “empty space” is not empty, it’s full of virtual particles — things like quarks, electrons, neutrinos with variable masses, electromagnetic and color (see quantum chromodynamics) charges pop in and out of existence all the time as quantum fluctuations, which violate energy conservation laws. But because they violate symmetries like the law of conservation of energy, these ripples are not stable and the more they violate it the more unstable they are and the faster they disappear, just like in the above example the bigger the asymmetry of the coin, the faster the game is over. 

*Energy conservation is only a law, because we can't see the stuff that doesn't obey it. It's nothing more than a statistical effect.*

![image-title-here](/images/foam.jpeg){:class="img-responsive"} 

Here’s another simple example of symmetry: the nucleus of an atom and its electron shell have exactly the same electric charge, but with opposite signs. If this wouldn’t be the case, the atom wouldn’t be stable — it would attract enough electrons until the net charge balances out. So what’s the takeaway here? Asymmetric states are not stable, they are transitory.

Think of it this way... there’s no law that says butterflies (or any species for that matter) have to be symmetric, but evolution weeds out asymmetric individuals pretty fast. Same with particles, so it's almost like we are dealing with some sort of universal natural selection. Symmetry and harmony go hand in hand, and I've discussed the concept of [harmony in physics](http://florintoader.net/harmony) at length.

![image-title-here](/images/butterfly.png){:class="img-responsive"} 

And we can actually go further then energy and generalize this concept. In fact there is even a mathematical theorem called [Noether's theorem](https://en.wikipedia.org/wiki/Noether%27s_theorem) which says:

*Every differentiable symmetry of the action of a physical system has a corresponding conservation law.*

Let's see what that means. First of all, a symmetry refers to the property of an object to be *invariant under a transformation*. One example of that would be a sphere: if you take any sphere and you rotate it by any number of degrees in any direction, it will look the same — that's what *invariant* means. And in our case, the action was rotation, but it can be something else like translation or reversing the direction of a spatial or time coordinate. The butterfly in the picture has *mirror symmetry*, meaning we can flip the direction of the y axis and it looks the same etc. 

### A Primer On Gauge Symmetries ###

By looking at the [Euler-Lagrange equation](https://en.wikipedia.org/wiki/Euler%E2%80%93Lagrange_equation), we can see that:

1. The law of conservation of energy is a consequence of the fact that the Lagrangian doesn't depend on *t*. This means that the laws of physics don't change with time.

2. The conservation of momentum is a consequence of the fact the Lagrangian is invariant under spatial translations. The laws of physics are the same both here and on the moon.

3. The conservation of angular momentum is a consequence of the rotational symmetry of the Lagrangian. And so on...

But there's also a slew of other very interesting symmetries. *T Symmetry* or *time reversal symmetry*, for example, says that if we flip the direction of the arrow of time, we get the same laws, which is really interesting because time seems to be flowing forward, we seem to be getting irreversibly old etc. (but this is for another article). *C Symmetry* or *charge conjugation* tells us that if we flip the sign of the charge of something around, it doesn't make any difference. Indeed, if our world would be made out of anti-particles instead of particles, we wouldn't notice any difference — keep in mind that the electro-weak interaction violates C symmetry, but that's a more advanced topic. *P Symmetry*, *parity*  or mirror symmetry is the property of a system that says it's laws don't change if we flip the sign of a spatial coordinate. Weak interactions also violate this symmetry.

You can also combine these symmetries — for example CP symmetry refers to *both* C symmetry and parity in conjunction, which means that reversing the charge of the particles and mirroring the system spatially should give us a system indistinguishable from the original. This was introduced because the weak interaction violated both C and P symmetries, but it turns out that it also [violates CP symmetry](https://en.wikipedia.org/wiki/CP_violation). What is needed to describe the weak force is [CPT symmetry](https://en.wikipedia.org/wiki/CPT_symmetryx): you get this by also adding T symmetry to the mix.

So how do we know which interactions obey what symmetries and which not, if everything is so random in quantum mechanics? The same way we would find out if a coin is biased or not. But instead of tossing the coin a gazillion time and counting the results, we smash things at high speeds a gazillion times, we sift through the debris and we plot the results on curves and see what comes out.

![image-title-here](/images/correlationp.png){:class="img-responsive"} 

So far so good.

Now the 6.4 billion dollar question is *if the universe started from a single symmetric point, and the laws are so symmetric, where does all this variance and uniformity we see in the world around us come from?* 

Stay tuned.

