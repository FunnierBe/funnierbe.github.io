---
layout: post
title:  "100 Days of Graph Compute"
date:   2022-10-28 4:30:00
categories: 100Days
---


# 100 Days of learning about graph compute

*GPU/TPU/IPU, Paperspace, Lambda, VAST.ai, Colab, Kaggle ... and a bit of leveling up old school IT, sysadmin and C++ skills as well as trying to keep up with what's happening in containers, Jupyter notebooks, Python, PyTorch*

.

Of course, we have some experience with Jupyter, Python programming, Docker containers, setting up JupyterHub, using AWS or GCP or Azure ... we have also played with Google CoLab and Paperspace Gradient -- we know that the array of offerings in the rentable GPU space from VAST.ai and others is growing faster than anyone can keep up with ... the point of learning is not to keep up with change; the point of learning is to be able to appreciate and enjoy the new opportunities that change presents RATHER than complaining or ever imagining that the range of alternatives is not FAR SUPERIOR to what the alternatives were last year, five years ago or a couple of decades ago.  

We learn DEEPLY in order to constantly exhibit gratitude that comes from the certain knowledge we are blessed to live in fabulously superlative times which are continuously becoming more fabulously superlative ... we learn DEEP learning in order to use and appreciate the learning environment we live in.  

1)  

## The #100Days Plan 

1) We will want to do dive into [computational graphs](https://jdhao.github.io/2017/11/12/pytorch-computation-graph/) ... doing that that requires a lot of set up and installation and understarding of basic skills ... a first, we will just want to look at Obtaining an affordable learning sandbox.  To be clear, we will need to rely MOSTLY on rented GPU clusters and things like NVIDEA LaunchPad in order to really explore compute graphs ... and it would certainly be possible at first to rely ENTIRELY upon freebie resources like Google Colab or Paperspace Gradient or similar ... but a gaming PC with a GPU board actually allows us the chance to learn even more as developers about what performance monitoring and tracing and understanding how the computation is happening -- there's a lot going on behind the scenes or under the hood beyond just the Jupyter notebook processing indicators ... the recent fall in GPU prices makes things that were out of reach six months ago entirely affordable ... this applies to pre-built gaming rigs.  Since we are CHEAP by nature ... in our particular case, we will work with a DELL Alienware Aurora R12 with a liquid-cooled i7-11700KF processor, 32GB DDR memory and a Geoforce RTX 3080 gpu card.  

Why DELL?  Those of us who have worked in IT in companies use DELL stuff for its consistency, supportability and massive volumes of units sold [which makes for great internet  bottomfeeder content, ie lots of people are familiar with and discuss their mods/optimizations on IDENTICAL apples-to-apples training labs]...the primary reason to use DELL is not DELL, but instead it is the VOLUME of dell stuff driving the internet fora and YouTube with HIGH QUALITY, painfully honest, personal content about on DELL systems from legit human beings, eg   https://youtube.com/playlist?list=PL2Ksi8qJcnFIFZ2hm3HbxQFtCdi57nzjY ... the not-entirely-bad DELL discards from people are always available on eBay for cheep ... if you can't find spare parts you need now, someone else will sell one for parts in the next week or so.  VOLUME matters.  Go with DELL to get the benefits of VOLUME.

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



2) The general objective of this deep dive is about LEARNING, learning how to learn about something that can make one more productive ... generally, we know that it is important to learn more about exercise and fitness in the use of things that one counts on everyday ... in this specific deep dive, we are interested in the process of learning about how we level up our skills in science and math to better USE deep learning.  

Active learning is fundamentally an exercise in the continuous improvement of diligent dogfooding -- it involves doing hands-on things directly, thinking in new compute paradigms as we upgrade our C++ skills, becoming familiar with new libraries, really using perfmon and debugging tools effectively and generally getting it absolutely right at each step compounds our ability to learn at the next steps that we cannot even currently foresee.  We will need to sharpen our skills in learning in new ways; it's a matter of developing the mental discipline to improve the ways that we teach ourselves to build the tools that we will use to build better tools to learn.

We want to use deep learning and computational horsepower to aid our learning about other things like computational chemistry and simulation, AI for computer-aided imaging at nanoscale and natural language processing for smarter ways to curate and annotate datagraphs of knowledge ... it's mostly about the discipline of continually learning.

In order to help ourselves learn, we will want to develop the content in some form of a collaborative online workspace ... that means Github Codespaces or GitPod.io or VScode.dev or some other browser-accessible, standard collaborative workspace that anyone with internet access can use  ... well, almost anyone ... this might involve training people somewhat or requesting that they [take their own deep dive into social Codespaces](https://docs.github.com/en/codespaces/getting-started/deep-dive) as a precondition or prerequisite for collaboration.

3) 

4)

5)

6)

7)

8)

9)

10)

11)

12)

13)

14)

15)

16)

17)

18)

19)

20) Social media and social coding are about generating interactions and sharing ideas ... it's tough to say exactly where is the best place to find people, but you won't find people in your imagination or by just continuing to listen to the same people that you have listened to ... you will need to find your own ways to meet people ... it's like kindergarten; get out there and play with those kids ... and BE KIND!

21)

22)

23)

24)

25)

26)

27)

28)

29)

30)

31)

32)

33)

34)

35)

36)

37)

38)

39)

40) You will want to track your podcast with analytics or various observable metrics that offer chances to experiment or test a bit as you optimize your reception and deal with the various objections and aggravations. 

41)

42)

43)

44)

45)

46)

47)

48)

49)

50)

51)

52)

53)

54)

55)

56)

57)

58)

59)

60) Advertising, monetization, patronage ... this is not really about making money -- it's really about whether you have some sort of project that will ever be self-sustaining ... following 20 days in this milestone are mainly about reaching out to others for shared support

61)

62)

63)

64)

65)

66)

67)

68)

69)

70)

71)

72)

73)

74)

75)

76)

77)

78)

79)

80) This milestone is about the final push toward wrapping thing thing up ... after the 100 days are done, it's either a matter of doing something new and going forward with something that might disrupt the existing ecosystem or deciding that the best approach is to put your shoulder to an existing wheel and build upon what has been been built ... the best course is generally going to be the latter, but there are a LOT of existing wheels and you should be extremely careful and quite discriminating in terms of deciding which is the best one. The process of learning something should have introduced you to the people in the world who are the very best at what can be achieved. If you genuinely don't believe these people are capable of realizing the best vision of what is possible, you disrupt ... but the best option is likely going to be continued collaboration and evangelization for success.

81)

82)

83)

84)

85)

86)

87)

88)

89)

90)

91)

92)

93)

94)

95)

96)

97)

98)

99) Ninety-nine? Comedic ending, sub conclusion

100) Maxwell Smart ... Now Go OUT THERE and Be Serious 
