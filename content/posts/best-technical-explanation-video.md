---
title: "Best Technical Explanation Video?"
date: 2023-03-10T10:36:14-05:00
draft: false
tags: ['docker', 'video', 'tutorial']
---

I came across the following video while doing research on how to use Docker securely esp. regarding mounting volumes as a non-root user.

Spoiler: it's complicated and there has been a number of explanations and discussions on this topic including [one from about 10 years go](https://github.com/moby/moby/issues/2259). Yep! 
<!--more-->

https://www.youtube.com/watch?v=jeTKgAEyhsA

I already knew the solution to my problem - [running Docker in Rootless mode](https://docs.docker.com/engine/security/rootless/).
But in this short ~33-minute video, Liz not only explains the problem but also the solution in a very clear and concise manner.
And how it is implemented in Docker by actually implementing it live!

The last one I remember someone explaining a technical topic in such a manner was [What the heck is the event loop anyway?](https://www.youtube.com/watch?v=8aGhZQkoFbQ) by Philip Roberts.