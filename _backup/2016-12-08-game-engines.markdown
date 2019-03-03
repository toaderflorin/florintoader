---
layout: post
title:  "A Short History Of 3D Game Engines"
description: "Another post from the “how it’s made” series. I chose to focus on Id Software, because back in the day, they were pioneers and everybody was copying them. Not to mention, John Carmack is a legend in the industry..."
date:   2016-12-08 21:13:11 +0300
categories:
image: "/images/doom.jpeg"
---
Another post from the “how it’s made” series. I chose to focus on Id Software, because back in the day, they were pioneers and everybody was copying them. Not to mention, John Carmack is a legend in the industry.

### Wolfenstein ###

This game is considered by many the grand father of 3D shooters.

<iframe width="740" height="415" src="https://www.youtube.com/embed/561sPCk6ByE" frameborder="0" allowfullscreen></iframe>

The implementation is simple: the whole level is actually 2D, and it’s stored in a grid-like structure like this:

What the engine does is it figures out in which square of the grid the player is, and then for each vertical line on the screen, it traces a ray through this grid to see where it intersects something. So 320×200 screen resolution means 320 rays traced. When the ray hits a wall, it draws that section of the wall as a vertical line on the screen.

![image-title-here](/images/level1.gif){:class="img-responsive"}

Now you might have noticed a few things. First, all the walls are vertical and at 90 degree angles. Second, there are no floors. Third, the player cannot look up or down. Number one is the consequence of the grid system in the above picture. The second and third points are actually quite interesting, and has to do with the technological limitations of the processor at the time. Doing mathematically correct perspective texture mapping would require two divides per pixel, so this would have been quite slow. However, vertical walls have a very interesting property — vertical lines on them are parallel to the screen, so you calculate where the texture starts and ends, and do linear interpolation in between (their Z coordinate is constant). This means, you just have to add a small delta for each pixel — no perspective correction needed.

The enemies and objects are simply 2D pictures, called sprites.

### Doom ###
Now, Doom was really interesting when it came out. If you look at the game, it appears a lot more is happening than in Wolfenstein. You have floors, you have outdoor areas and you can see the sky. You have lighting, and the floors don’t even have to be at the same height — you can have stairs for example, and not just any stairs. You can have circular staircases, or odd angled staircases. It looks like a big step forward.

<iframe width="740" height="415" src="https://www.youtube.com/embed/IhaNyOAjd2g" frameborder="0" allowfullscreen></iframe>

Essentially, the maps in Doom are still 2D. They did away with the grid system however, and now the wall lines can be placed anywhere in space and at whatever angle to themselves. They still need to be vertical however, because of the same texture mapping limitation as in Wolf3D and also because the whole level is stored in 2D, not 3D. The map you just saw looks like this:

![image-title-here](/images/level2.gif){:class="img-responsive"}

The grid was replaced by a system called a binary space partition tree (done when compiling a level, not at run time). Compilation of a BSP tree works like this:

1. You take the whole level, pick an arbitrary wall line and extend it to infinity in both directions. Based on this line, you split the level in 2 parts (or partitions), on each side of the line. If the line extending towards infinity intersects other lines, you split these lines in two. Each part will go in it’s own partition.

2. You repeat this process on each partition until you can no longer split, and just have convex sectors (also called cells, or ‘leafs’). These cells can also be stored in a graph structure, but I am not sure if Doom does it.

3. For each sector, the floor / ceiling height and texture can be set. This trick allows the engine to create stairs and platforms.

For rendering, Doom still does ray-tracing for each vertical line on the screen, it just uses the BSP tree. The cells also are helpful for collision detection, like in Wolfenstein.

You might have noticed that Doom now has floors. Floors are somewhat more complicated to render than walls, but have a similar property: horizontal lines are parallel to the screen (instead of the vertical ones, for walls), so the variation in texture space is still linear (the only difference is that both the u and v coordinates now vary). When Doom does ray-tracing, it keeps a track of the sectors it traversed, gets the vertical wall intersections, renders the walls and then comes back and renders the floors using the trick I just mentioned. Lighting is done per sector, just like floor and ceiling height. Just check out this image.

![image-title-here](/images/doom.jpeg){:class="img-responsive"}

The lighting on the ceiling (and of course flooring) matches the stairs.

### Quake ###

For Quake, id was really ambitious. They actually wanted to make a fully 3D game, so you can look up and down, have 3D enemies, rooms on top of each other etc.

![image-title-here](/images/quake.jpeg){:class="img-responsive"}

Quake is indeed 3D, and this is how it works: First of all, the levels are actually modelled using a 3D editor, not a 2D one. Enemies are also 3D objects. The level is build out of volume brushes like rectangular boxes, tetrahedrons etc. Quake still uses BSP trees, it just does it in 3D — it uses polygon planes to split the level into subsections. The end result is a set of convex 3D cells, adjacent to one another.

Visibility calculation was a tricky problem to solve for Quake, as ray-tracing is no longer a viable solution. This would have to be done on a per pixel level now, so John Carmack and Michael Abrash (the creators of the engine) tried all sorts of things out (like beam trees, doing ray casting every 8×8 pixels), before settling on a pre-calculated visibility solution.

Michael has an awesome series of articles describing how they reached this solution:
http://www.bluesnews.com/abrash/

A PVS (potential visibility set) is just a data structure indicating cell “1321” can see cell “1235” and “1211”, “1211” can see “1321” and “1313”, and so on. At runtime, the engine checks the cell you are in, and then sees which cells are visible from there. The PVS is pre-calculated on compile time. The tricky part is actually calculating this set, and this works like this:

1. When splitting the level into convex cells, the engine uses virtual polygons to close up the cell. These are called “portals”, because they provide the transition between two cells. An example of a portal would be looking through a doorway, but not only. Basically, wherever two cells touch and there isn’t a wall, we have a portal.

2. If two cells communicate directly via a portal, they are connected in the PVS.

3. For non adjacent cells, Quake uses intersection of portals and clipping to see if a sequence of portals can be seen through (and not ray casting), but obviously this is a complicated computation and takes a lot of time to do for the whole level.

Again, Michael explaining how multiple portals are stacked. Apparently John Carmack spent several months on this problem.

http://www.gdcvault.com/play/1014234/Excerpt-Quake-Postmortem-Optimizing-Level

Let’s see how Quake does lighting. For walls and other static objects, the lighting is pre-calculated realistically (including bounced light) by tracing rays. The result is stored in very low resolution textures (called light maps). Dynamic lights, like the light from a rocket, are additive — they just light up areas in a certain radius. They don’t cast any shadows or GI, for obvious performance issues. Lighting on moving models is calculated at the polygon vertex level and it’s a lot more simplistic (it uses the Gouraud shading approach).

Texture mapping is also interesting. The rendering code is written in assembly and perspective correction for walls using the costly divide operations is not done on every pixel. It’s actually done every 8 pixels or so, and interpolated. Also, moving models like enemies don’t use perspective correct texture mapping, and this is visible if you get close (and on the weapons). Check out the difference between the corrected and uncorrected version:

![image-title-here](/images/quake2.png){:class="img-responsive"}

Unreal and Thief: The Dark Project also used BSP trees and precalculated lighting. Interestingly enough, Thief chose not to use a precalculated visibility solution, they actually saved the computed portals which were used real-time for determining what is visible and what is not. [Check it](http://nothings.org/gamedev/thief_rendering.html) out!
