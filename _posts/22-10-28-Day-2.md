---
layout: post
title:  "Graph Compute, Day 2 -- Dev Workflow And Kernel Profiling"
date:   2022-10-28 4:30:00
categories: 100Days
---


# 100 Days of learning about graph compute -- Day 2

We will want to be able to take look at in performance monitoring and tracing as we actually do any analysis or try out any code that we develop. In order to learn, we need to push hard enough to the point where we break things, but we just need to know where the line is and why. That means having perfmon data on where the bottlenecks are.  Pushing the system helps us understand how computation happens on different machines and where things are get sticky or stuck. Yes, we could just use CoLab but we want to know what's happening under the hood beyond just what the Jupyter notebook processing indicators might indicate. 

[Kernel profiling](https://developer.nvidia.com/nsight-compute), tracing and detailed performance monitoring are the kinds of things which one does not need to master UNTIL the time comes, but it is necessary at the start to have a modicum of awareness of how these tools might help refine developments or how optimization might be achieved. As we moved to [possibly underpowered] edge platforms, this kind of competency becomes more valuable or likely essential.

