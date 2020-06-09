---
title: "Why you should always draw a picture"
date: 2020-06-08
tags: 
  - code
  - software
---
## Technical diagrams are a superpower, even just for discussions

Over the past couple of weeks I've been working on a tough cookie of a project. Because it's work-related, I can't go into too much detail, but at a high level the goal was to discover and characterize all the various formats HTTP requests can take at Square. 

This means internal and external, user and application, authed and unauthed - every flavor you can imagine, if the request ever travels over the HTTP layer, I have to know about it. 

This proved especially difficult because many of the systems in place at Square are built to abstract that kind of knowledge away from application and framework developers. So when I had questions about, for example, underlying implementations for RPC request handling, even service owners frequently didn't know the details. And, because some of these systems are legacy, terms have become overloaded, so even when people did have knowledge about some particular type of request, I found myself feeling a lack of confidence that I had truly ironed out the details.

Round and round I went, finding domain experts and asking follow-up questions to follow-up clarifications, until finally, someone I was chatting with said, "Hold on - give me twenty minutes so I can draw out a diagram."

When he was done, he had produced a relatively straightforward and none-too-detailed diagram of some of the subsystems we were discussing and their relationships. But this quick sketch made it possible for us to be totally clear about what, exactly, we were referring to, and as a result, I felt sure I had finally answered my questions. It was deeply satisfying.

I went back to folks I'd conducted tortuous textual conversations with and found that, while the diagram only grew slightly more detailed, my understandings grew far more so. It was like a magic tool and all I could think about later was, why hadn't I thought to draw something earlier?

Whiteboards are software staples for a reason. In the current WFH reality, it's something that I realize I totally took for granted. Even when we were still in the office every day, I'm sure I could have taken more advantage of them - and I'm certain that tools like https://app.diagrams.net/ are underutilized even more.

So, I'm writing this down as a reminder that, when you're having trouble defining the boundaries of a problem or even the semantics of your terms...draw a picture! Do it before it's obvious that you need to, and you'll come away with clearer understandings faster and with less, you know, torture. 

