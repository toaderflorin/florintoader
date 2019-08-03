---
layout: post
title:  "The Redux Async Flow And Handling Side Effects"
date:   2017-07-20 06:39:37 +0300
description: "
The first thing that needs to be mentioned is that Redux, while fluxish in nature, is not an exact canonical implementation of the Flux architecture. Instead of using a dispatcher that sends actions to multiple stores, it uses a single store which keeps the state for the whole application, and a concept known as a reducer which is essentially a function that gets the current state and an action, and produces a new state based on the action...
"
icon: "logo-redux.png"
categories:
---

The first thing that needs to be mentioned is that Redux, while *fluxish* in nature, is not an exact canonical implementation of the Flux architecture. Instead of using a dispatcher that sends actions to multiple stores, it uses **a single store** which keeps the state for the whole application, and a concept known as a *reducer* which is essentially a function that gets the current state and an action, and produces a new state based on the action.

It looks something like this:

![redux](/images/redux.png){:class="img-responsive center-image"}

Redux is heavily inspired by Elm, which is a functional programming language, and it takes quite a few cues from it—the application
state reducer (in a real application, we are actually chaining multiple reducers into a big one, because otherwise the whole thing would become
unwieldy very fast), needs to be a *pure* function - which means it's not allowed to have *side-effects*. An action is just a plain object - the only requirement is that this object has to have a *type* property. An action creator is just a plain JS function that returns an action object. It looks something like this:

<script src="https://gist.github.com/toaderflorin/dbd3ad78285ecd7decfec8cd88877eb3.js"></script>

And a reducer would look something like this:

<script src="https://gist.github.com/toaderflorin/7c5ad3feedd8d6047cf29fb27efa9782.js"></script>

This is the Redux *synchronous flow*. Obviously, real world applications are more complicated than that because the client needs to sync with
the server, which means there are side-effects, but before we look at the async flow, let's get into...  

## A Bit Of Functional Programming

Let's explore the concepts of pure / unpure functions and side-effects by looking at some code:

<script src="https://gist.github.com/toaderflorin/867f25d45b36c65b8b409e3eca851091.js"></script>

If you worked with the standard Flux implementation by Facebook, you might have come across the concept of *action creators*. They are just normal JavaScript functions that return an action, which can be any type of JS object in Redux, the only requirement is to have a *type* property of type string. The first function is *pure* because it's return result is **always** reproducible for the same input parameter, which is not the case for the second function.

Now have a look at the following function:

<script src="https://gist.github.com/toaderflorin/96c280e5330d84851f103710ed381524.js"></script>

This function is said to have side-effects, because it changes a global variable which then changes the return value on subsequent
calls. Obviously, functions that have side-effects are not pure.

We went over the basic Flux architecture and some simple functional concepts. However in the real world, web applications are rarely this simple.
This initial architecture diagram is missing an essential aspect: server-side access. Obviously, this introduces side-effects, so as a result, the reducers
won't be pure anymore.

## Enter Redux Thunk

Since Redux allows for custom middleware, we can use something called *Redux Thunk* to help us. It is important to be aware that without
middleware, Redux only supports a synchronous flow. So what is a *thunk*? It's just a function - it wraps an expression, so you can delay
the evaluation of the result of that expression. Here's a code sample straight from the library documentation:

<script src="https://gist.github.com/toaderflorin/7961dfce75a8d1748b4192e3d16ed611.js"></script>

How does this help us you might ask?

*If you pass an expression as a parameter to another function, it will get evaluated within the same JavaScript event tick. If you pass a **thunk**
however, that function can evaluate it whenever it wants. This means you can do **async** stuff easily.*

And this is important because modern web applications are mostly asynchronous in their nature - you usually build a rich responsive client which communicates with an API. This means when the user presses a button, or does something that needs fetching data, you usually show spinners and such. The standard way to handle this is using the Redux *Thunk middleware*.

This is how you set it up:

<script src="https://gist.github.com/toaderflorin/b4754731b7a7ed4967cc7fcbb0fb3d9e.js"></script>

So instead of dispatching normal action objects, we will be dispatching *async actions*, or thunks. This means we have have to change our action creators to return functions instead of plain objects. Let us make a request to the server, and see how that would work. Obviously, that is an asynchronous action because it takes some time, and we might also want to show some sort of indication to the user that the request is ongoing - something like a spinner. And now let's add the asynchronous action.

We are using **axios**, a popular framework for making http requests.

<script src="https://gist.github.com/toaderflorin/4519a92c396ee2bb912bece07983a2cc.js"></script>

The reducer is going to receive the sync actions dispatched and will take appropriate steps to reduce the application step. The async actions are the place where we are handling the "dirty" stuff, like making an http request.

For the sake of simplicity, I chose to dispatch the actions inline, but we could (and should) extract them in a different action creator method. I also used the same action called *GET_ITEMS*, but you could use different actions for indicating the start, end and a potential error occurence in the occurrence eration.
