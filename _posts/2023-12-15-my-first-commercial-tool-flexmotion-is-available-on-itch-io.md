---
layout: post
title: My first commercial tool FlexMotion is available on Itch.io
subtitle: Please consider buying it~ 🥲
bigimg: /img/posts/flexmotion/flexmotion-widecover.jpg
share-img: /img/posts/flexmotion/flexmotion-socialmedia.jpg
tags: [tools, gamedev]
---

![FlexMotion logo](/img/posts/flexmotion/flexmotion-logo-light.svg){: width="25%" style="float: left; margin: 0 20px 0 0"}

It actually has been more than a week since its release on Itch.io. But I dreaded working on any website again after making one for **FlexMotion**. 🙃
It seems that web technologies take pleasure in making simple things more complicated than it should.

But this is an occasion to celebrate and not to complain, so here it is: 

## FlexMotion, my play-on-demand animation tool for Unity, is finally out! 🥳

It's available on [Itch.io](https://moartis.itch.io/flexmotion) and should be on the Unity Asset Store in January next year.

**FlexMotion** is the fruit of many iterations on a tool that allows me to play animation clips directly from scripts. This allows us to avoid using the Animator's state machines and to take back control over the animations. All this while preserving access to Mecanim functionalities. 

If you want to know more about what **FlexMotion** can do, check out its [website](https://flexmotion.moartis.dev)!

The development of this tool started two years ago. Back then I was working on a Survival Horror game that was planned to have many character states coupled to many different weapons. Like "running while being in a critical condition and holding a shotgun". Even with only two weapons in the prototype, the Mecanim's animator controller looked like a spider web and started to become hard to maintain and debug. 

![Typical animator controller](/img/posts/flexmotion/animator-controller.webp)

The solution was straightforward on paper, just let have a tool to play any animation at any time and smoothly transition between the two. 
The problem is that it's not possible to do with the Animator component without serious inefficient hacking (The very first iteration of the tool used that approach).
Using the old deprecated Animation component is also out of the question as it lacks many important features provided by Mecanim (like Humanoid rig support or root motion).

I finally ended up using the Unity Playables API (A system to manage and evaluate hierarchical tree structures) which is also what the Animatior is using internally. 
This allowed the tool to piggyback on the Animator features and be compatible with other animation packages like the powerful AnimationRigging tool.

It took me a while to get used to that new API and recover from its many beginner traps (like evaluating a playable graph manually breaks threading and its performance benefits) but it was a worthwhile effort. Since that last iteration, I've been using **FlexMotion** on many prototypes and it's now much easier to organize and test different sets of animations.

![Method Chaining](/img/posts/flexmotion/MethodChaining.jpg){: width="49%" style="float: left}
<!-- ![Time Callbacks](/img/posts/flexmotion/TimeCallbacks.jpg){: width="32%" style="float: center}  -->
![Easing-based transitions](/img/posts/flexmotion/EasingBasedTransitions.jpg){: width="49%" style="float: right} 

Considering that I have been struggling to release a commercial game for half a decade now, I'm releasing **FlexMotion** as a paid asset.
I don't think it will be successful, especially with the recent Unity blunder, but It's kind of a way for me to break that vicious circle of never finishing projects. 
Hopefully, it will break that self-inflicted curse for good. 😅

My next-steps for **FlexMotion** are: 
- Find a better workflow for pushing patches. I'm using the package manager format internally but the asset store is using the "old" .unitypackage format.
- Create a simpler sample. The Showcase scene is using too many tricks to be a clear first example.
- Make a video trailer that needs to be ready for the Unity store release. 

I also plan to release another tool early next year named **ClipSync**. It's an animation to event synchronization tool inspired by [DSAnimStudio](https://github.com/Meowmaritus/DSAnimStudio) and [Unreal Engine's Notifies](https://docs.unrealengine.com/5.0/en-US/animation-notifies-in-unreal-engine/). Here is a sneak peek:

![Typical animator controller](/img/posts/flexmotion/clipsync.jpg)

Thanks for reading and Happy winter holidays!
<br/>-Mathieu