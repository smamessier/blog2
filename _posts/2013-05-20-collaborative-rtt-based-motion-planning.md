---
layout: post
title: Collaborative RRT-based motion planning
date: '2013-05-20 20:50:00'
tags:
- projects-edu
---

Computing collision-free paths for multi-robot environments is a fundamental issue in the world of robotic path planning. Rapidly exploring Random Trees (RRTs) have been proven to be a very powerful method to design quick and efficient single-query path planners. Unfortunately, RRTs struggle with multi-robot worlds due to the explosion of the degrees of freedom and the increase in complexity for collision avoidance between moving agents in close proximity. In this project,we present a method that revolves around the idea of collaborative RRT (cRRT) search that shares information between all the robots in the environment. Planning by combining all the robots into a single high-dimensional RRT many times is unable to compute a collision-free path in a reasonable amount of time or tree nodes. Our method however, takes advantage of the power of RRTs on lower dimensional configurations and collaborates searches between all robots in order to compute collision- free paths for all.

Full-report below:


<iframe src = "/ViewerJS/#/docs/gatech/planning/report.pdf" width='100%' height='800' allowfullscreen webkitallowfullscreen></iframe> 