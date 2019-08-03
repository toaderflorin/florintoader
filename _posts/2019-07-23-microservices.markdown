---
layout: post
title:  "Getting Microservices Right"
date:   2019-07-22 09:39:37 +0300
description: "
Microservices seem to be very popular these days and everybody wants to be with the in crowd. You can argue that microservices are just a flavor of SOA and that they have been around for quite some time, but undoubtedly the microservice revolution was brought about by containers and the cloud. Regardless of whether you're building backend applications, cloud applications, or what have you, the central tenets of high level design must apply.
"
icon: "lock.png"
categories:
---
Microservices seem to be quite a hot commodity (it looks like they've reached stage of *Peak of Inflated Expectations* on the Gartner hype cycle) and everybody these days and everybody wants to be with the in crowd and implement them in production, but there should be a question that should be on the architect's mind when adopting them: *do we actually need them?*, because like with most architectural approaches, they come both with advantages and drawbacks.

<br/><br/>

![my-password](/images/hype.jpg){:class="img-responsive"}

There is considerable overhead with creating a deployment, with setting up a reverse proxy but I'd like to say the cloud commoditized DevOps. Azure and AWS give you a Kubernetes control plane for free and they manage it for you - you can create a k8s cluster and set the policies with a few clicks. The same architectural common sense rules still apply. For example, you still want to have low coupling between the components (services) themselves. You care about how various microservices mutate state. Distributed systems also introduce problems related to distributed transactions. Using replication compounds this problem. Dan Ambramov has an interesting article about stateful components [here](https://redux.js.org/introduction/motivation).

Adopting something just because it's *cool* is most always a bad idea.

## Architectural Considerations
You can argue that microservices are just a flavor of SOA and that they have been around for quite some time, but there's a little bit more to the store (and even microservice proponents argue that this approach is *SOA done right*). SOA is a software architecture pattern, which application components provide services to other components via a communications protocol over a network and most of the time relies on the [enterprise service bus]() pattern, which is mostly discouraged when going with a microservices approach. Microservices are an architectural pattern that is closely related but there are enough differences that make it distinct from SOA. In both architectures, developers must deal with the complexity of architecture and a distributed system. Developers must implement the inter-service communication mechanism between microservices (if the message queue is used in Microservice architectures) or within ESB and services.

As developers, we build applications out of components and microservices are nothing more than REST distributed components. <b>That's it</b>. Some would say the microservice approach is SOA done right. Another advantage of microservices is you can scale out only portions of your application. Applications such as Facebook and Google run on a lot of nodes in the cloud, but not all nodes take up the same amount of resources. It's nice to be able to scale just where it's needed.

In a nutshell, the difference between a monolith and a microservice application would look like this:

![my-password](/images/microservices.png){:class="img-responsive"}

In architectural terms, we're mostly interested in cohesion and coupling. <b>Cohesion</b> refers to how strongly the members of a class or component are related and coupling refers to roughly how strongly entangled the components are. The first is good, the second one is bad so obviously you want more of the former and less of the latter. Cohesion is great because as a developer it makes it easy to know where to search for stuff. Imagine you have a bunch of drawers neatly organized: you have the socks in one, you have the shirts in another and so forth. If you need something, you just go to the respective drawer and pick out what you need and that's it. Coupling is a bit more interesting -- the main reason why you want to avoid

Because you want to insulate the microservices from one another as much as possible, you want to think about each of them mutates state so you want to design the schema of your state very carefully. While you could go with one database per microservice, the overhead associated with that is quite high and most likely you are not going to do it so it's not uncommon for microservices to hit various tables in one main DB.

## Domain Driven Design To The Rescue
A lot of people object to the DDD term because they think it sounds overly pompous, but as an approach DDD isn't that much different than Test Driven Design or Component Driven Design (for UI). When you're doing TDD, you write down the tests first and then the implementation. When your building your UI with CDD, you first create a set of UI components and then you think of what the UX / pages will be and you build them out components. With DDD, you jot down your domain objects and your bounded context first on paper and then you model your database state and create microservices along those lines.

![my-password](/images/sketch2.png){:class="img-responsive"}

We can ask:

* What exactly constitutes a microservice?
* Is this service too big and does it need breaking up?
* More importantly, can your architecture have too many microservices? What's the right granularity?

As always, there is no right and set answer. If services aren't small enough, then you obviously don't have micro-services. But there is such a thing as too much fragmentation - say you are refactoring an existing monolithic application which has over one hundred controllers. Should you turn each of them in a microservice? That might be an overkill. A good rule of thumb is to assign responsibility to a microservice. You can have an authentication microservice, a logging one. If you accept payments and refunds from your customers, you can create a payments microservice. You get where I'm going with this.

*In a sense, being good at microservices means being good at DDD.*

If for example you write Java or C# code and you update the public signature of a class and another class is using it, your application will no longer compile, so you immediately get a heads up. But that's not the case with microservices. A lot of companies use internal package repositories for shared functionality between projects (UI component packages are pretty common) and as a developer, whenever you are creating a new version of a package, you have to think about whether you've introduced breaking changes. Microservices compound this problem because different applications can use different versions of packages and not all projects have to be at the same. Microservices don't afford the same luxury and you need to pay. Packages and microservices allow you to finely control the development cycle of portions of your application, but as always, with great power comes great responsibility and you must pay close attention to what you are deploying and when. It is easy to break things if you're not being careful.

You also might not want to expose all of your functionality to a client.

![my-password](/images/gateway.png){:class="img-responsive"}

## Breaking Your Existing Monolith



## Embracing Polyglot Development
A cool thing about microservices is now that your application is decoupled into smaller pieces and these are standalone, you can use whatever development stack for each of them. While you don't necessarily want to go overboard with adding a lot of
