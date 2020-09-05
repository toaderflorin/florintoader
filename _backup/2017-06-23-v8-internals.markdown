---
layout: post
title: "Under The Hood: V8 Internals"
description: "Dynamic languages get a lot of love in the startup community, and it’s not hard to see why—they are mostly open source, they are cross platform, and it’s very easy get an application up and running because their syntax tends to be very terse, and you can write a lot of functionality with very little code. But as a wise man used to say, with great power comes great responsibility, and as great as Ruby on Rails is, it’s no secret that Ruby is not exactly fast—depending on the benchmark you’re using..."
date: 2017-06-16 06:39:37 +0300
icon: "v8.png"
categories:
---
![chrome](/images/chrome.png){:class="img-responsive img-left"}

Dynamic languages get a lot of love in the startup community, and it’s not hard to see why—they are mostly open source, they are cross platform, and it’s very easy get an application up and running because their syntax tends to be very terse, and you can write a lot of functionality with very little code. But as a wise man used to say, with great power comes great responsibility, and as great as Ruby on Rails is, it’s no secret that Ruby is not exactly fast—depending on the benchmark you’re using, it’s about two orders of magnitude (that’s 100 times) slower than something like Java. Of course as a whole, RoR applications are not that slow because a lot of execution time is spent in native extensions such as querying the database—Ruby and Rails only serve the purpose of gluing stuff together. Nevertheless, more and more companies are moving from Rails to node.js or Go, and they are doing it for performance reasons / scalability. Another reason to use node.js is the fact that you can share code between the server-side and the client-side, but I digress.

For those who have not used node.js, it uses Google’s V8 JavaScript engine which powers Chrome, and it’s fast. And the reason why it’s fast is because it actually compiles you JS code instead of interpreting it. The whole process works as follows:

1. V8 evaluates the JavaScript in your file and does just-in-time compilation to machine code using a compiler that’s designed to compile as fast as possible, and then stores the compiled code for that portion of the program.

2. V8 also maintains a hot-map of the code that runs. If it sees functions being run several times, it will use a second compiler which optimizes your code, but it’s slower.

3. The engine also relies heavily on making assumptions about your code, and optimizing preemptively.

What’s interesting is that V8 doesn’t treat objects as hash-tables, as most JS engines do—it instead creates a sort of struct with the properties of the object, which it calls a hidden class. You can think of this hidden class as similar to Ruby’s eigenclasses.

<script src="https://gist.github.com/toaderflorin/6dafc797abe6a17bb7d63d8d94e22fb5.js"></script>

If you add a new property to obj1, V8 is no longer able map the properties of the object to the same hidden class, so it will create a new one. V8 also tries to preemptively optimize your code and it does so by looking for repetitions.

*JavaScript is a dynamic language but the more you are using it as a statically typed language, the better of you are when it comes to optimizations.*

If you are using ES6 (and I recommend that you do because there are great transpilation / bundling tools such as Babel and Webpack, not to mention the current version of node.js 7.10 has native support for classes, lambdas, await/async and a lot of other nifty stuff)— I suggest you use classes to structure your project, and use getters and setters.

<script src="https://gist.github.com/toaderflorin/eb5fb6e45dd943a3f6ad87da7f1fe827.js"></script>

Of course, there’s nothing preventing you from modifying the “private” fields in JavaScript (except maybe a code review from your technical lead), and also there is nothing preventing you from adding new properties to the object (except using Object.freeze() but this has a performance penalty). Not only will this give you better encapsulation, but it will speed up your code because V8 is able to optimize it better. Of course, if you really want to have private members and proper static (compile time) type checking, you can use Facebook’s Flow, or Microsoft’s TypeScript.

Also, a lot of developers tend to use plain JS objects as dictionaries because objects are key-value pairs. However, knowing how the V8 compiler optimizer works, that’s not a very good idea. Computed property names are also problematic for the optimizer, and they make code also hard to understand, so they should be avoided. The Map object is great, if you need to use key-value pairs.

Another word of caution: be extra careful with arrays. Check out the following code:

<script src="https://gist.github.com/toaderflorin/2b22591a73bd61ad4b07dec88fdae5b7.js"></script>

As long as an array doesn’t have holes in it, it’s going to be treated as a contiguous memory area, which makes the code using it fast. However, if you get fancy like in the example above, you are going to have a sparse array, and V8 will convert it to a hash-table, which will make writing and reading slower.

**tldr;**

The closer your JavaScript program is to static typed code, the better V8 is going to be able to optimize your code using static analysis. You can use TypeScript / Facebook Flow to enforce this.
