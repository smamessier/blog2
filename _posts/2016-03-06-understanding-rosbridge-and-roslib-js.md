---
layout: post
title: Using Rosbridge and Roslib JS
date: '2016-03-06 05:27:53'
tags:
- dev-tutorials
---

ROS
---
The Robot Operating system (ROS) was originally developped by Willow Garage ...

Why Rosbridge ?
---------------
ROS is already a versatile piece of software offering a native C++ library as well as extensive bindings for python. However, other scripting/programming languages cannot directly benefit from the implementation of the ROS communication protocol as it is the case for Javascript or Java. Rosbridge was developed to fill that gap.

####Pros
* Uses generic network protocols (TCP, Websockets)
* Connects web interfaces to the ROS network.
* Offers throttling, queueing optimizations.
####Cons
* Breaks ROS' decentralized network architecture.

Roslib JS
---------

```javascript
var ros = new ROSLIB.Ros({
 url: 'ws://localhost:9090'
})
``` 
