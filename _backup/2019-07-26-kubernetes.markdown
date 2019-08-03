---
layout: post
title:  "Simple Kubernetes"
date:   2019-07-26 09:39:37 +0300
description: "
Microservices seem to be very popular these days and everybody wants to be with the in crowd. You can argue that microservices are just a flavor of SOA and that they have been around for quite some time, but undoubtedly the microservice revolution was brought about by containers and the cloud. Regardless of whether you're building backend applications, cloud applications, or what have you, the central tenets of high level design must apply.
"
icon: "lock.png"
categories:
---
While there are a lot of in depth articles describing how to set up a Kubernetes cluster, I thought I would create a really short succinct article describing the anatomy of a k8s cluster.

* A cluster is made up of nodes (real or virtual machines) and these can be master or worker nodes. Yes, you can have more than one master node if you want high availability and in this case a master election algorithm is run to determine the leader of the cluster.
* A worker node contains one or more [pods]() -- the pod is essentially the basic unit of k8s.
* A pod contains one or more container images.
* We of course need to expose our cluster to the outside world so we need a [service]() which maps internally to a [deployment]().
