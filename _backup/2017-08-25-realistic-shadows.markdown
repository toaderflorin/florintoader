---
layout: post
title:  "Behind The Magic: Realistic In-Game Shadows"
description: "Lately, I’ve been fascinated by just how realistic environments the Unreal Engine can create. I mean, compared to Unity, it seems surreal. Or unreal, if you will. Looking closely at the demo, I think it boils down to three things..."
date: 2017-08-24 21:13:11 +0300
categories: science
image: "/images/dfields.jpg"
---

Lately, I’ve been fascinated by just how realistic environments the Unreal Engine can create. I mean, compared to Unity, it seems surreal. Or unreal, if you will.

<iframe width="740" height="415" src="https://www.youtube.com/embed/8kdjJ1qsL2c" frameborder="0" allowfullscreen></iframe>

Looking closely at the demo, I think it boils down to three things:

1. Realistic indirect illumination
2. Soft shadows and proper ambient occlusion
3. Screen space depth of field

### The Standard Shadow Algorithm ###
The simplest shadowing algorithm in 3D graphics works like this: to see if light hits a certain point in space or not, you trace a line from that point to the location of the light and see if it intersects anything. If it does, the point is shadowed, if not, it is lit. The way you actually implement this in real time on the GPU, is by rendering how the light “sees” the scene in all six directions (up, down, left, right, front, behind) and create a cube map. The cube map contains the distance from the light source to the nearest occluder.

When rendering the scene, for each pixel of a particular polygon, you check against the depth map. Based on the position of the point you are rendering, you calculate the angle with the light source and you get the corresponding cube face and the *u* and *v* coordinates for that direction. If your point's distance to the light source equals the distance in the depth map (use a small bias here, there might be numerical errors), it means your object is the occluder for that direction, and it is lit. If the distance is bigger, it means there’s something else closer to the light, so this area is in shadow.

![lighting1](/images/lighting1.jpg){:class="img-responsive"}

You can see the result of this technique in the picture. Now obviously, this is not what shadows look like in the real world.

### Area Shadows ###
The reason why shadows are not hard in the real world is because light sources have volume. For example, the sun is not a point, it’s a disc (as seen from Earth). This means objects have penumbras which are lit by only part of the light source. The bigger the light source, the more diffuse the shadow is.

![lighting2](/images/lighting2.jpg){:class="img-responsive"}

We could try to blur our shadow, but that doesn’t look realistic because a real soft shadow is sharp near the object and gets softer with distance. A real soft shadow (called actually area shadow) looks like this:

![lighting3](/images/lighting3.jpg){:class="img-responsive"}

The way this is implemented in non real-time rendering engines, is by simulating how light behaves in the real world and casting a lot of rays in various directions and averaging out the result. The disadvantage of this approach is that the technique produces an image which is noisy if not enough photons are traced (you can actually see the individual photons), and very time consuming if you are tracing and averaging enough photons to get rid of the noise.

The Unreal Engine team actually managed to pull off the area shadow effect quite nicely. Just check out the following video.

<iframe width="740" height="415" src="https://www.youtube.com/embed/-xai0iBffUc" frameborder="0" allowfullscreen></iframe>

This demo doesn’t contain indirect illumination, so the areas not directly lit are pitch black. You can however see how nice the shadows are: pretty sharp near the objects and then they get smoother and softer with distance. It turns out there is a really cool trick that actually helps making this on the GPU. This is a wonderful technique developer by Iñigo Quilez and makes use of already existing concepts such as ray-marching and signed distance fields.

### Signed Distance Fields ###
What are signed distance fields? To answer that, let’s explain what a distance function is. A distance function is bound to an object (such as a sphere, or something more complicated), and for each point in space, it returns the smallest distance from that point to the object. A signed distance function returns positive values if the point is outside the object, and negative values for points inside the object. The distance function for a sphere looks like this:

<script src="https://gist.github.com/toaderflorin/efe0081985123837ac7244815341650e.js"></script>

Obviously, for complex objects the distance functions are complicated and they usually involve taking each polygon into account, so they are time consuming to calculate. This is why for a complex polygon mesh, the distance function is pre-calculated and saved into a three dimensional (volume) texture. Valve recently created a cool paper describing how to do this in two dimensions for text. Epic is doing the same thing in three dimensions. [Check it out](http://www.valvesoftware.com/publications/2007/SIGGRAPH2007_AlphaTestedMagnification.pdf) if you are interested in the details.

UE actually allows visualizing the distance fields in a level. This is pretty cool.

![dfields](/images/dfields.jpg){:class="img-responsive"}

This is another interesting concept, and it’s not really that new. The algorithm involves tracing a ray by getting closer and closer to the actual objects, using spheres, like the one in the image. At each step, the closest distance to the scene can be inferred via the distance field we just discussed so this is a fairly cheap operation on the GPU. Nvidia has an article describe the technique in detail [here](http://http.developer.nvidia.com/GPUGems2/gpugems2_chapter08.html).

As you can see from the Nvidia article, there are many applications for ray-marching. Epic is also using this approach for ambient occlusion, and working on a global illumination algorithm based on them.

### Back To Lighting ###
How can this be applied to lighting? In the pixel shader, you start from the position of the pixel in 3D space and then trace your way towards the light source. If you hit something, obviously the point you are rendering is in shadow.

But here’s where it gets interesting. Because you are tracing your ray along a path, you know when you are getting close to other objects that might be partially occluding your light. The closer the traced ray comes to an object, the darker the shadow. This is not necessarily physically accurate, but provides a nice approximation. If there are multiple objects in the way affecting the shadow, we pick the closest. We use this to calculate an shadowing coefficient, like so:

<script src="https://gist.github.com/toaderflorin/2e341d9b52d084926fea20df353a64a9.js"></script>

where K is a constant that depends on the values you are using for distances and makes the whole thing look good :). The shadow coefficient should be capped to 1. The result should be something like this.

<iframe width="740" height="415" src="https://www.youtube.com/embed/HEtGeBOyKCY" frameborder="0" allowfullscreen></iframe>

Also, check out the nice ambient occlusion in the demo.
