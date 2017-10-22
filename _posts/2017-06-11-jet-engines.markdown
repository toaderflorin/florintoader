---
layout: post
title:  "Jet Engines Explained"
date:   2017-06-11 21:13:11 +0300
categories:
description: "The way a jet works is not that different from how a deflating balloon works: high pressure gas exits a small hole, and propels the balloon. The energy propelling the balloon actually comes the work we put in inflating the balloon...
"
image: "/images/f35-engine.jpeg"
---

The way a jet works is not that different from how a deflating balloon works: high pressure gas exits a small hole, and propels the balloon. The energy propelling the balloon actually comes the work we put in inflating the balloon. Inflating the balloon takes energy, so we can think of the balloon as an energy store.

WW1 and 2 era aircraft used propellers which were driven by Otto cycle engines, similar to the ones used in cars, but research into rockets (the Germans and their U2 rocket research were instrumental in the area) proved that just using the jet of burning gases can make a vehicle go much faster.

![image-title-here](/images/rocket.png){:class="img-responsive"}

Interestingly, rockets need two tanks: a fuel tank and an oxidizer tank. The fuel needs something to burn on — an oxidizing agent (in the case of the U2 rocket we are talking about compressed liquid oxygen). Liquid oxygen is compressed, so it takes very little volume, which means it has a high concentration, and is able to provide an intense reaction, which in turn gives the rocket a tremendous thrust. Naturally, you would want to use a similar principle with aircraft, and it turns out you can.

The only problem is, you need a way to compress air for the chemical reaction to be strong enough.

So you have to use a compressor. Turns out, it’s not very hard to build a jet engine, and the structure is fairly simple. I will try to explain it in layman’s turns.

![image-title-here](/images/jet.png){:class="img-responsive"}

So here it is:

1. The intake of the engine consists of a series of fans which squeeze incoming air into smaller and smaller spaces. This compresses the air, makes it hot, and slows it down.

2. The compressed air is then combined with fuel, which burns and produces hot high pressure gas (exhaust).

3. The exhaust spools up a turbine which is placed on the same shaft the compressor fans are, which in turn drives the compressor (this is where the turbo in turbojet comes from).

Now here’s an interesting thing: when the aircraft is stationary, the compressor fans are not spinning, so they are not injecting compressed air in the burn chamber. So how do you start a jet engine up, considering jet engines are too big to be started by an electric motor.?

1. Newer jets have APUs (auxiliary power units, used for powering the cabin and such), which help jump start the compressor. The APU is actually also a jet engine, but a smaller one, small enough to be jump started by an electric motor.

2. Alternatively, compressed air can be injected into the engine on the tarmac, which will spool up the turbine and spin up the compressor blades.

Next, let’s look at some interesting considerations. The amount of thrust an airplane produces is usually limited by the amount of air the plane can ingest. The bigger the engine intake, the bigger the thrust, but also the less aerodynamic the aircraft. The faster the engine spins, the more air the intake gobbles up, but also the bigger the air resistance for the blades cutting through the air and the louder the engine.

Also keep in mind that the influx of air is dependent on high fast the plane is going, so turbojets are not great at small speeds. One solution is to mount a propeller on the shaft, and use the much bigger blades to provide thrust to the plane. Since the blades are able to displace a much bigger volume of air, turboprops are more efficient at small speeds than turbojets and are also more quiet.

![image-title-here](/images/propeller.png){:class="img-responsive"}

The third alternative is the turbofan, which is a hybrid between a turboprop and a turbojet. The majority of modern day fighters are turbofans.

Instead of a propeller, you have a set of smaller fans which you encase in a hull for aerodynamic purposes. The inner section is similar in structure to a normal turbojet. This setup allow some of the air to bypass the core of the engine, making the engine more propeller or jet like, depending on the bypass ratio. Here’s how it works:

![image-title-here](/images/engine-anim.gif){:class="img-responsive"}

Legend and picture (courtesy of Wikipedia):

1. Nacelle
2. Fan
3. Low-pressure compressor
4. High-pressure compressor
5. Combustion chamber
6. High-pressure turbine
7. Low-pressure turbine
8. Core nozzle
9. Fan nozzle

So commercial aircraft have bulky, large bypass-ratio engines which are more economic to run whereas military jets have low bypass engines, as you can see in this cutaway of the F35’s turbofan.

![image-title-here](/images/f35-engine.jpeg){:class="img-responsive"}

The closed end section is empty, and allows the hot pressurized exhaust to mix with the bypassed air deep inside the plane, so that the heat signature of the plane from behind is greatly reduced. If more thrust is needed (for a dogfight), large quantities of fuel can be sprayed immediately after the turbine which is called reheat, but this is a very inefficient way of running the plane. Not to mention, the aircraft becomes easily detectable visually (at night), in infrared and by radar (the hot trail actually reflects radar waves pretty well).
