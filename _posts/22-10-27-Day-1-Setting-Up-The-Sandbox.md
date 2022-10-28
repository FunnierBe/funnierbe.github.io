---
layout: post
title:  "Graph Compute, Day 1 -- Setting up A Learning Sandbox"
date:   2022-10-27 4:30:00
categories: 100Days
---


# 100 Days of learning about graph compute -- Day 1

At first, setting up anything like this involves TONS and then more TONS of sysadmin stuff. It is a great opportunity to revisit lots of things like dev workflow, dependencies, packages, installation processes and just generally understanding the precursors underlying those basic infrastructure skills ... we don't need to make a career of the sysadmin stuff, but we need to ensure that we stay *somewhat* competent in that area.

We just need to obtain a decent affordable learning sandbox; the more powerful the better, within limits -- it should not be some sort of budget breaker. We are NOT going to fall in geek love with our sandbox; the gaming rig we use is just a means to the end of being able to learn with a machine that offers some compute horsepower.

We will want to be able to take look at in performance monitoring and tracing as we actually do any analysis or try out any code that we develop. In order to learn, we need to push hard enough to the point where we break things, but we just need to know where the line is and why. That means having perfmon data on where the bottlenecks are.  Pushing the system helps us understand how computation happens on different machines and where things are get sticky or stuck. Yes, we could just use CoLab but we want to know what's happening under the hood beyond just what the Jupyter notebook processing indicators might indicate. 

[Kernel profiling](https://developer.nvidia.com/nsight-compute), tracing and detailed performance monitoring are the kinds of things which one does not need to master UNTIL the time comes, but it is necessary at the start to have a modicum of awareness of how these tools might help refine developments or how optimization might be achieved. As we moved to [possibly underpowered] edge platforms, this kind of competency becomes more valuable or likely essential.

To be clear, we ultimately will rely MOSTLY on rented high-performance GPU clusters and things like NVIDEA LaunchPad in order to really explore compute graphs ... and it would certainly be possible at first to rely ENTIRELY upon freebie resources like Google Colab or Paperspace Gradient or similar ... but a gaming PC with a GPU board actually allows us the chance to learn even more as developers about what  the recent fall in GPU prices makes things that were out of reach six months ago entirely affordable ... this especially applies to things like pre-built gaming rigs.  We are not going to fall in love with the gear; it's only a means to an end ... and we are naturally CHEAP by nature. 

In our particular case, we will work with a DELL Alienware Aurora R12 with a liquid-cooled i7-11700KF processor, 32GB DDR memory and a Geoforce RTX 3080 gpu card.  "Why DELL?" you might or should ask.  Those of us who have worked in IT in companies use DELL stuff for its consistency or replaceability, supportability arises out of uniformity.  Massive volumes of units have been sold ... which makes for great internet  bottomfeeder content, ie lots of people are familiar with and discuss their mods/optimizations on IDENTICAL apples-to-apples training labs].  To reiterate, the primary reason to use DELL is not that we buy the debatable DELL marketing hype -- rather, it is the undebatable VOLUME of DELL stuff driving the internet fora and YouTube with decent quality, painfully honest, personal content about on DELL systems from legit human beings, eg   https://youtube.com/playlist?list=PL2Ksi8qJcnFIFZ2hm3HbxQFtCdi57nzjY ... the not-entirely-bad DELL discards from people are always available on eBay for cheep ... if you can't find spare parts you need now, someone else will sell one for parts in the next week or so.  VOLUME matters.  Go with DELL to get the benefits of VOLUME.

Why Alienware Aurora?  Any explanation will necessarily sound like marketing speak from DELL ... except that there is actually an element of truth to DELL marketing speak because companies like DELL have to depend upon their reputation ... but mostly, the reason for the gaming rig flagship comes down to the kind of engineering and maintainability that comes from a HIGH VOLUME entity going hard after an extremely lucrative market niche of affluent customers, ie TEAMS of DELL engineers developed this system and then they took advantage of employee discounts to actually take the stuff home or give as gifts ... not just TEAMS independent entrepreneurs, but these systems come from capable, mature systems in the full CMMI sense that develop predictavle product ... it's the CMMI, not just the LARGE teams of thoroughly-vetted, specialized, professional engineers vying for a career-defining resume position with a favorable DELL success.  So ... YES ... it is also true that the components will be exhaustively value-added, value-engineered to ensure that they are as cheap as possible -- but this kind of stuff is going to be pretty much obsolete in five or certainly ten years anyway, right?

Why R12?  As a general rule, it's not just that all of the components in the system are new and improved [and maybe cheapened up, hopefully where it doesn't matter], the R12 is the Alienware Aurora team's first rodeo with this particular design approach ... there are improvements in the R11 over the R10, improvements in R12 over R11.  The R12 is not the R13 or R14 but it can be modified to accomplish the more expensive system.

For example, the R13 allowed customers to specify a 1000W power supply, but the R12 [under a service contract] also had access to after-sale DELL-factory-service-approved improvements like a 1000W power supply ... even though, you might not be able to put 1000W of heat into that case and now expect some problems -- more power does present options.  For example, it might be more necessary to remove the mechanical hard-drive and add with a BIGGER fan ...yes, that fan will be noiser, but nothing is as quiet as compute that has shut down. At least, a 1000W ensures that you actually can put a BIG FAN in that case.  

Why liquid-cooled?  As good as the R12 might be, air-flow is still going to be an inescapable design flaw with this design ... it will be necessary to use every trick in the book to keep this rascal cool ... dissipating heat is a REALLY BIG problem ... but when you know exactly what the problem is, you can work around IT, ie this project is FULL of little life lessons.

Why Intel i7-11700KF ... first of all, it's a chance a chance to get reacquainted with and really EXPLORE the Intel ecosystem and especially the Rocket Lake architecture https://en.wikipedia.org/wiki/Rocket_Lake -- which will be important to understand, particularly when we get into the tracing and performance monitoring stuff ... the VOLUME lesson, which applies to Intel [moreso than NVIDEA] matters here as well -- Intel is not perfect, but its VOLUMES mean that problems are well known ...  and when you know exactly what the problem is, you can work around it, ie this life lesson gets re-iterated so it must be an important one.

The i7-11700KF in our cheapo system is certainly not an entirely bad cpu ... yes, it's afforable so it has limitations, the 16 MB L3 cache, for example, can become a bottleneck ... BUT you are in control of the software, so gotta find ways to get AROUND those bottleneck OR it will be necessary to get a new cpu ... but i7-11700KF has 8 cores, runs 16 threads ... and has neato technologoes like the Intel® Gaussian & Neural Accelerator (GNA) ... an ultra-low power accelerator block designed to run audio and speed-centric AI workloads. The Intel® GNA is actually designed to run audio based neural networks at ultra-low power, while simultaneously relieving the CPU of this workload ... this kind of thing is nothing short of amazing, if only because this magic easter egg of a feature illustrates how HUGE of a roll software has now inside a hardware product.
 https://www.techreviewer.com/tech-specs/intel-11700kf-for-gaming/

https://ark.intel.com/content/www/us/en/ark/products/212048/intel-core-i711700kf-processor-16m-cache-up-to-5-00-ghz.html


Why 32 (2X16) GB DDR4 memory in two of the four slots? Why not just 16 or 4X16 for 64? Why not the full 128?

32 GB is probaby going to be enough for most tasks; if it isn't ... that might be the time to add 2 X 32 for 96 GB; and if that's still not enough replace the 2 X 16 with 32s.

Why the GeForce RTX 3080 gpu card?  

We cannot afford the DGX H100 SuperPod ... yet ...  https://www.nvidia.com/en-us/data-center/dgx-superpod/
