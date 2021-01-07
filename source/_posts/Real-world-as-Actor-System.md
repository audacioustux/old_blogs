---
title: Real world as Actor System
thumbnail: /img/actor-system.png
date: 2021-01-08 04:24:50
categories:
- beam
- akka
- জ্ঞানবার্তা
tags:
- actor-model
- explain
---

#### One can partially model the real-world in an actor system.

Like, imagine you, me, everyone and everything are actors...
They **act** when they get a message in their **mailbox**...
Every actor runs in their process, doing their own business...
they mostly do three things in their lifetime, 
1. listens to messages, 
2. changes his own view & perspective of the world purely based on the messages received, 
3. do things that they feel right.
They may tell other actors to do something via messages or spawn more children actors and be a responsible parent. Not because they crave for a child, but to delegate their work to them... because the more the actors, the more resources they can utilize...
The individual actors have no idea about the real world, and they don't share any memory... if one dies, no one cares, except their parents...

Now imagine you are an actor and have a supervisor. Who supervises many other actors just like you;
but you are a faulty one. You don't know how to center a text vertically in CSS. You can do three things at this point:
1. Break down, and decide to leave your post,
2. Ask a search engine (also an actor) to find resources to learn how to do the task so you can process the message.
Optionally, by the time you take to learn the new skill, you could add the task to your mailbox again to do that in the future and keep doing other tasks.
But that means you can reach a point when you're in a livelock [1] situation... what if the search engine failed to find any resource? You're continuously reminding yourself about the task, not having enough sleep, and disrupting others needlessly... why not just leave your post?
3. Politely ask your supervisor by sending a message to terminate himself [0]

In computation, spawning each of these actors takes nanoseconds and takes less than a KB of memory. Millions of actors get scheduled on an arbitrary number of physical CPU cores. You can create a strong hierarchy out of this. You have full control of how they would behave, their traits before they are even born out of that specification.
Individually they have no significance. 
- Actors can migrate one node to another, 
- shout and listen to events/messages, 
- spawn as many children they want, 
- terminate them if they fail on their purpose and replace them with new ones in a matter of nanoseconds, 
- even self terminate and clean out any footprint has left, with no moral obligations.

Real-world is chaotic because we want to survive. Our mind is locked and protected by our aggressive behavior. We don't have an agreed protocol to communicate, a common goal to achieve, a messed up hierarchy, reluctant to gracefully migrate to a different place, and damn.! ain't we have too many globals to deal with? not a single source of truth.., no CRDT... oopsie 🙃

[0]: don't in real life
[1]: a condition in which two or more threads while not blocked cannot make further progress
