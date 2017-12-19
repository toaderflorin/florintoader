---
layout: post
title:  "The Language Of God: Part 1"
description: "Show a picture of Einstein and most people would recognize who he is. A lot of people would be able to recognize Heisenberg and certainly even more people have heard of him, even though they don't know how a picture of him would look like..."
date:   2017-12-19 11:13:11 +0300
image: "/images/weyl.png"
---
Show a picture of Einstein and most people would recognize who he is. A lot of people would be able to recognize Heisenberg and certainly even more people have heard of him, even though they don't know how a picture of him would look like. Surprisingly, considering this man's contribution to science and mathematics, not many people who are not in the field have heard of him.

![weyl](/images/weyl.png){:class="img-responsive"}

Einstein used the phrase "reading the mind of God" a lot when talking about physics--to be more precise, he said something along the lines of:

*I want to know how God created this world. I'm not interested in this or that phenomenon, in the spectrum of this or that element. I want to know His thoughts, the rest are details.*.

Of course, Einstein used "God" as a stand-in for "the laws of the universe", but what most people don't know is that is as perceptive as he was, he still relied of the work of Hermann Minkowski to describe the mathematical underpinnings of General Relativity. You can look at what's happening and have an intuitive understanding of the processes at work, but if you want to describe and formalize everything, you need to understand this "language". And that language is mathematics.

If you follow physics blogs, you might have read that the main problem in physics right now is combining relativity with quantum mechanics. That's not correct, Paul Dirac did that in 1928 and he also predicted the existence of anti-matter, so that's not the problem. The problem is we don't know how to create a quantum theory of gravity, because no attempt at this is [renormalizable](https://en.wikipedia.org/wiki/Renormalization), but that's something for another day. Mathematicians are the unsung heroes of the field and you can think of this article as a small homage to Weyl. If it wasn't for him, we wouldn't have *representation theory* or *gauge theory*. So here we go.

### Speaking The Language: Algebraic Groups
We are going to start with the basics, the equivalent of "gugu gaga", if you will: groups. Groups are "abstract algebraic structures"--a group consists of a set of *elements* (say all positive integers smaller than 100) and an *operation*. Let's call our group G. We will annotate the operation with "•".

* First of all, the operation • between any two elements, *a* and *b*, such as a • b = c must produce a c that's part of the group set.

* Second, this operation must be associative, such that *(a • b) • c = a • (b • c)*.

* Third, the group must have an "identity" (or "zero") *i* that leaves any element from the set unchanged under the operation, such that *a • i = i • a = a*

* Also each element must have an "inverse" *a<sub>i</sub>*, such that *(a • a<sub>i</sub>) = i*

* This is not a requirement for groups, but if *(a • b) = (b • a)*, the group is called commutative or *abelian*. Otherwise it's called non commutative or non-abelian.

A simple example would be the [circle group](https://en.wikipedia.org/wiki/Unitary_group), the group of all complex numbers with absolute value 1 where the operation of the group is multiplication.

![weyl](/images/modulo.svg){:class="img-responsive"}

Multiplying two complex numbers with absolute value 1 yields another complex number with absolute value of 1. Not only that, but multiplication is equivalent with the addition of phases.

*Groups are concepts that allows us to model real life stuff. They also allow us to look at all this stuff and see patterns such as symmetries.*

I spoke about the concept of delved into [symmetries]() somewhat, but I didn't formalize the concept.
