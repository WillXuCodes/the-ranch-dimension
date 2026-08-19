---
description: Claude, summarize this article for me?
---

# AI - The Automation of Brain Rot

As the biggest topic in tech right now, AI and it's capability is one of the things everybody is exploring right now. Frustratingly, there's been a lot of blind trust put into AI systems and agentic workflows in the software engineering world. The Dunning-Kruger effect is now reinforced by "claudisms" reassuring devs who don't know how to debug with hallucinated "smoking guns", as well as pointing out scaffolding as "load bearing" code (I mean, the most permanent solution is a temporary one isn't it?).&#x20;

I've even heard someone compare using Claude as essential to programming as using an IDE pre-AI... while I want to believe this is a bad faith argument the implication here is that if a developer _isn't_ using AI to program, their methods are considered out of date.

Now I want to make it clear, I'm not in the camp of being completely anti AI. I'd consider myself jumping into the deep end of things, with most of my workload, daily reports, and work strategy shifting towards having some level of AI involvement. I even have a multi-agentic work chain with adversarial verification and other behaviors. As a result, one of the main challenges I face these days is preventing the type of "brain rot" that this article describes.

#### Chegg-GPT

Pre-AI, there was a website known as "Chegg". It was a paid crowd sourced homework answer site that provided answers to questions for a subscription fee. Many professors considered using Chegg on homework assignments as "cheating". This was mainly because seeing the answers directly meant that most time-strapped students would directly copy the answers without understanding the methodology behind them.

As chat-gpt and other AI providers rose in prominence late 2022, the stock dropped sharply and continued to drop in its post-covid decline.

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

While AI didn't have the same 1:1 functionality as Chegg, what AI provided was a superset of what Chegg had. It could answer any question (even if it wasn't crowd sourced) and had the knowledge of the entire internet behind it.&#x20;

If Chegg was considered cheating, how do we even begin to classify using AI tools to do homework? Super cheating?

When faced with adversity on an assignment, students not only gain the technical knowledge from the solution for the problem, but also the critical thinking, problem solving skills, and character development from solving the problem.&#x20;

**A students' first instinct when faced with adversity on an assignment shouldn't be to ask somebody or something (AI, TA, or Chegg) for help**.&#x20;

More directly in the programming world, AI tends to hallucinate and assert randomly until it finds the issue. This tends to be less accurately and more time consuming than going through a normal debugging cycle where the problematic area is reduced to something manageable before attempting a fix. Without going through adversity the "old fashioned" way, students deprive themselves of practice for these skills.

#### A Thought Experiment

Let's pretend it's the year 2018 (pre-AI). Peak tech boom and tech market, everybody graduates and gets a job. You're a senior developer who also **recently joined** the team who is mentoring a new grad, and the new grad is assigned a few "ladder tasks" (tasks designed to on-board somebody and get them feet wet with the code base). Unrealistically, your manager also tells you that helping this new grad is now your _only_ responsibility and to blindly support any directive that is sent your way.

So, right out of the gate this new grad asks you for a general summary of the code base. You oblige, and follow up questions feel more and more like he's wholesale reliant on you for code rather than looking at the functions themselves and the call flow. You start to make bigger generalizations about complex mechanisms because the questions that are being asked are being supplied from a perspective of somebody unfamiliar with the codebase. You can't really blame the mentee for that, as they're a new grad after all.&#x20;

The new grad decides to start executing on this tasking. With your only responsibility to help this new grad, they give you general instructions on where to put code. You finish the code and the task for them, with your deep understanding of the code base from processing all surrounding functions and how the different systems interact with each other. They take a cursory look over the code after you've finished, and conclude that all seems well with this.&#x20;

This cycle repeats for every task they're given, until they're given a more complicated task to implement a new feature. You watch helplessly as (while doomscrolling on their phone and waiting for you to finish) the new grad gives you vague, unclear instructions without architectural insight and over-generalized answers on how on your clarification questions. At the end, the code produced has many shortcuts, doesn't fit pre-existing conventions, and if tested on hardware, has a few bugs that don't show up until it's ran on actual hardware.

Instead of probing hardware, adding print statements, or opening a debugger to isolate the problematic code you're sent in with a pasted image of the new feature not working and to peripherally diagnose the issues and fix them. With your limited abilities to run the code since you don't have access to hardware, you desperately assert and try to fix different issues. At the end, after many hours of doomscrolling and waiting for you to finish, you finally just happen to hit the right parts of the code to make the feature work. The new grad has done nothing but continually paste things from the print statements and outputs you've been adding, but has done none of the work themselves of trying to figure out how you got to the conclusion you got to.&#x20;

A PR is finally opened for this feature, there are 100+ files changed from the vague requirements and debugging process. Another senior dev has you review the code separately since the 100 file change is deemed "too big to be manually reviewed". Without context for the rest of the codebase and how it's used (since you also recently joined the team), you make a few sweeping assertions which are also promptly fixed after you're requested to do so by the new grad.&#x20;

The PR merges, breaking tons of convention and the general software architecture. This leads to bugs and untracked behavior down the road.

#### Un-institutional Knowledge

While the example above is admittedly hyperbolic and unrealistic for a 2018 timeframe, this type of dev definitely exists not just at the new-grad level across industry in our new AI powered landscape. From this little thought exercise, we can see a few forms of institutional and fundamental knowledge being lost:

* Debugging skills, isolation of problematic code or hardware.
* Code architecture, known issues with hardware and software systems being buried by AI assertions.
* Code review skills and being able to properly leave feedback without the prose of AI.
* Baseline understanding and being able to dive into a codebase without the help of AI.

I don't think it'd be controversial to say that a new grad that acted like this (even with the super un-realistic senior engineer being allowed to hover overhead) would learn much throughout the process. The eventual development of somebody who even could always deliver AI powered features would be a dev who fundamentally can't architect software and draft requirements. Original author intent is lost somewhere along the way in an effort to deliver more features quicker, and somebody like this would most likely be PIP'd or fired in the long run.&#x20;

With this possibility in mind, another dimension and considerable thought needs to be put into how we can mentor junior devs without sacrificing the learning experience for performance.

After all... if low-context introductory tasking can be finished by AI all the time, why hire new grads? Why not just have multi-agentic AI chains automatically finish grunt work that can be done by senior developers kicking off AI chains?&#x20;

The future of software development becomes a small number of devs prompting a large number of agents to code features without any care for software architecture. The devs only know what they've prompted and none of the verification or implementation details. The code becomes a black box that nobody understands with confusing architecture.

The brain rot sets in as days are spent scrolling Instagram and Tik-Tok while the agents finish everybody's work. Why think at all when AI can do it for us?

#### Mentorship and Brain-Rot Prevention

(TODO)
