---
description: Software Development Schedules, and AI
---

# The Artificial Man Month

### The Open Source Tarpit

_All programmers are optimists. Perhaps this modern sorcery especially attracts those who believe in happy endings and fairy godmothers. - Mythical Man Month Page 14_

Around 4 years ago, I embarked on a journey in the pre AI software landscape of a new version of the [PROS ](https://pros.cs.purdue.edu/)kernel in an effort to future proof the system and break down tech debt before I left the project for a proper (paying) job. This project was known as "PROS 4" and was behind schedule due to the constant replanning, COVID restrictions, and other external factors. On the other hand, this allowed for more than a year of background planning as PROS 3 was continued to be developed along with new features for our end user developer experience.

At the time, I had roughly 10 developers as one monolithic, tight knit team of high performing programmers. This was started at the beginning of the Purdue school year, and the high level plan was to use "new hires" (freshmen coming to Purdue) to use high level planning documents that had been written and finally finalized after a 1.5 year churn while legacy systems were still supported. After all, the project had gained a lot of attention for students competing in the VEX robotics competition leading to some students knowing about Purdue purely from PROS and the BLRS Wiki. As a result, I wasn't too concerned about finding these students or making a really large recuitment push.

When the time came, we had around 30 students show up to our project's first training meeting. What could go wrong from a sudden influx of new hires for a project in dire need of catching up to schedule?

### Artificial Men

Despite being a treasure trove of many interesting software engineering (and also a snapshot of a different era of a fledgling software development field), systems design, and project management ideas, the main concept the ["Mythical Man Month" by Frederick P. Brooks Jr](https://web.eecs.umich.edu/~weimerw/2018-481/readings/mythical-man-month.pdf) is cited for is the idea software development shouldn't be treated like a production line, and instead a highly orchestrated network of workers that need to cross communicate. Its central thesis states that attempting to add more and more people slows down software development as communication overhead, training and getting new developers up to speed, and management overhead in trying to coordinate large groups slows short development in the short term.&#x20;

More concisely put:

> Hence, the man-month as a unit> &#x20;for measuring the size of a job is a dangerous and deceptive myth. It implies that men and months are interchangeable.
>
> > Page 17, Mythical Man Month

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

However, as we enter the age of AI (artificial men), maybe we should revisit this thesis and what it means for the "optimal" team setup? Maybe the limitations that drive the central thesis aren't valid if being able to spin up artificial manpower out of thin air that communicate perfectly is now a possibility?

**How much does throwing more AI en masse actually speed up software development when it's already behind schedule?**

### Curbing the Woes of the Craft

_A book, then,&#x20;or a computer, or a program comes into existence first as an ideal construct, built outside time and space, but complete in the mind&#x20;of the author. - Page 15_

In a section earlier on in the book, Brooks describes the woes of software development as:

1. **The necessity for code to be written "perfectly" for computers.**
2. Dependence upon potentially poorly written, documented, or buggy pieces of software or hardware for a full system to work.
3. Dependence on previously poorly written pieces of software that can't or shouldn't be changed.
4. Designing grand concepts is fun, debugging isn't.
5. Debugging isn't a linearly progressing task, with more hidden bugs taking exponentially more time to root out.
6. A product becomes obsolete by the time it releases conceptually or performance wise.\*

\*As valid as woe 6 is, unlike the other woes good software engineering or project management can't effect this as much so I'm going to pretend it doesn't exist.

A generally agreeable idea in AI driven software development is that the more "boring" or "tedious" parts of software development are now streamlined by having AI brute force its way through such problems or tasks. The main thing that this addresses is the first woe (bolded), where AI tends not to make simple syntactical issues or [more common absent minded mistype for a certain feature.](https://github.com/purduesigbots/pros/pull/403/files) Think of the last time you've seen AI make a genuine compilation error by missing a semicolon or simple language feature?

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

However, all the other woes are still present, and in fact can be both increased or decreased by how effective AI is being used.&#x20;

Generally speaking, effective AI reducing typos and syntactical issues speeds up code development by:

* Preventing bugs like the ones listed above from happening in the first place (woe 4).
* Reducing time for discovery and investigation of software not directly owned by the development team (woe 2).
* Limited AI assistance in debugging (woe 4 and 5).

On the other hand, ineffective AI use can slow down code development by:

* Poorly documented and written pieces of software from brute forced code written by AI (woe 2).
* Terrible software architecture at the expense of getting things working quicker (woe 3).
* Overdependence on AI debugging, leading to hallucinating and prolonging debugging cycles (woes 4 and 5).

Let's dig deep into these effects of AI on software development, and how they might slow things down and how to mitigate them.

### Guess and Check

Any competent developer understands that debugging methodology in any software environment boils down to isolating the root cause by reducing the search area. However, most (vanilla) AI models don't debug this way and instead rely on "guess and check", or asserting a hypothesis and verifying if the fix worked or having a developer manually test. In the latter case where a developer has to manually test (which is quite common in computer engineering or embedded development) this slows down development quite a bit as every missed guess is more time spent waiting for AI to finish and manually testing.&#x20;

So what is the (prescriptively) "correct" way to use AI when debugging? It mainly boils down to:

1. Generating otherwise tedious debugging code to aid in finding bugs as part of the isolation process.
2. Proactively having AI search through a codebase for potential bugs.
3. Having AI parse large data sets after capturing logs or other data, and either manually or automatically having it plot a chart to prove this use.
4. Writing unit tests with conditions and test routines that are manually reviewed.

I've seen quite a bit of time burned by developers attempting the guess and check method. Not only in industry, but especially during interviews when I give a "bug hunt" style question. This style of debugging even when done without AI tends to be a lot slower than the human version, as humans at least have the context and original author intend for the code being debugged.

With the volatility of debugging in mind, test and debug tends to be the hardest time to account for. This is reinforced with the idea that half the time in a software development cycle should go towards testing, and the initial execution given only half the time that the planning does:

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

While the motivating factor for this type of schedule planning is to present a relatively accurate budget for higher level product management to use, it's also a proactive way to prevent a slip in schedule.

As much as AI might marginally help with the test and debugging process, it 100% can't do the debugging process and there will always be a human in the loop in some form. How an AI debugs is only a reflection of the methodology in which the developer would use without it, and many newer developers post-AI are missing the experience and general methodology for debugging.

### Clone and Own

Speaking of original author intent, AI can't be 100% understand this and upstream requirements until (it can read our minds). At a high level, LLMs are inherently pattern recognition models that regurgitate pre-existing design patterns and code without as much context for the requirements or needs of the developer. In a day and age where the production of code is cheap, the software architecture is the limiting factor for reducing cost of change for each subsequent feature, not the speed in which the code is written itself.

Some may assert, that with AI maintained codebases software architecture should matter even _less_ than in hand-coded ones. If code is cheap to produce, what's the harm in creating a system in which changing the world to add new features is the norm? Why not clone and own entire codebases and forego modularity?

Software development teams aren't closed ecosystems with a clean or even static set of requirements. Requirements change, code needs to be traced and debugged, and human readability is still a factor when it comes to auditing actual changes. Cost of change (or number of lines per change) should be relatively low to help improve code readability in the long run as well.

Even in a best case situation where AI can debug or generate code quickly, having large sprawling codebases with antipatterns produces more and more unmaintainable code that will eventually slow down the best token burning furnaces available. More and more additional context needs to be ingested to make small changes, in a similar manner to if code was going to be changed manually.

Inevitably even after a product matures, new features will be requested and tech debt will have to be addressed. Half working features can't stay half working afterall.

```
A program doesn't stop changing when it is delivered for customer
use {...} these changes include added functions. Usually they are visible to the
user.
- Mythical Man Month Pages 120-121
```

This then re-emphasizes the importance and almost unpredictable nature of testing, as new features integrated and old bugs fixed require another round of validation to make sure regression isn't occurring. If regressions and bugs are found while testing, this will lead to more debugging which something AI doesn't speed up by a substantial amount. This further reinforces the idea that simply throwing AI at a software program behind schedule doesn't speed up.

So what is the mitigation? Sure it's easy to say that software architecture should be nailed down from the start, but reality is more nuanced than that. My general philosophy is that:<br>

1. Try to design good software architecture from the start.
2. If you can't, make architecture decisions that are "tree shakable" and can be backed out later.
3. For 1 and 2, development under pressure makes large changes hard. Gradual replacement or slow integration of a larger change or architecture is preferrable in these cases to prevent regressions or breaking features.

As with most effective AI usage, these tenets also apply to hand maintained code as well. No AI will understand potential customer needs and the scalability programs better than the developer unless they spend an enormous amount of time loading and maintaining context for AI models to ingest, burning money in the form of tokens and time in the form of having AI process and human hands maintain such context.

### Escaping the Open Source Tarpit

Back on PROS 4, my project management skills at least allowed me to properly run sprints, keep the project from scope creeping, and identify future tech debt to be scoped post-release. Development was scoped out in a reasonable way with the assumption that it was going to be my core 10 developers with some extra help in executing and testing new features and refactors.

However with 30 members total (a third of the new hire freshmen had been attrited during training, which is normal as people drop interest for different reasons), I had to rapidly institute another level of management leaving my most knowledgeable and fastest developers as tech leads mentoring new grads rather than executing on tasking.

Development slowed down to a crawl, and became a textbook case of the mythical man month as each sprint saw more tickets being dragged from sprint to sprint and more bug tickets being opened each sprint fixing features from previous sprints. This teaching pipeline also effected existing product development, as the balance of trying to support legacy systems and the new one created 2 products to support.

One day, I was pulled aside by the kernel lead (incredibly competent developer who I miss working with greatly). He introduced me to the concept of the mythical man month, and it immediately clicked. At this point, there wasn't really any going back after onboarding that many developers.

\
At the end of the year, the PROS 4 beta released, and the real PROS 4 release occurred roughly a year later. Further debugging and tech debt reduction continued for another year until the product matured to the point where it reached maintenance mode. The entire development cycle took longer than even the revised schedule, with the final schedule looking like:

* 1.5 years for software planning
* 1 year for software development (1/6th of the time)
* 1 year for beta testing (1/4th of the time)
* \~1 year for post-release bugfixes and testing (1/4th of the time)

Even with proper repartitioning of tasks and systems design done ahead of time, the training and ramp-up of newer developers still caused a slip in schedule. The on-boarding of newer developers should not be underestimated unless a robust "ladder tasking" system is put into place to allow developers to climb into their roles quicker than conventional methods.

Years down the road, I've thought about how AI would've been able to speed up or prevent this process. I've come to the conclusion that while various aspects (mainly the initial development and creation of the code) may have been less tedious and faster, the bulk of the time spent testing and debugging was still a very manual process that AI could've helped marginally but not substantially.&#x20;

Even if AI would've onboarded those junior developers a lot quicker, debugging still isn't a process that would've been improved by involving more developers. Adding 6 more developers onto a team of 2 developers debugging the same problem isn't going to solve the problem faster the same way the "bearing of a child takes nine months, no matter how many women are assigned" (Page 17).  &#x20;

### Conclusion

Generally speaking the expectations of what AI can do for software development schedules is incredibly high. However, we must curb our expectations given the fact that while AI makes certain aspects of software development easier, the most unpredictable portions of test and debugging aren't substantially improved with the introduction of AI. **The main causes of schedule slippage are still at large.** The "1/6th" in Brook's model for predicting software schedules might be reduced greatly, but everything else stays almost the same but are marginally improved.

```
The tar pit of software engineering will continue to be sticky for
a long time to come. One can expect the human race to continue
attempting systems just within or just beyond our reach; and
software systems are perhaps the most intricate and complex of
man's handiworks. The management of this complex craft will demand 
our best use of new languages and systems, our best
adaptation of proven engineering management methods, liberal doses of common sense, 
and a God-given humility to recognize our fallibility and limitations.

- Mythical Man Month - Epilogue, Page 177
```

While the dream of software development is to write as little code as possible while fulfilling all requirements, the "death" of the software engineering field is an asymptote only leads to what some are terming "cyberpsychosis". Debugging, software architecture, and requirements scoping are still very human processes that are enhanced but not fully replaced by AI.

While Brook's law states:&#x20;

```
Adding manpower to a late software project makes it later.
```

I'd like to assert that:

```
Adding artificial manpower to a badly planned software makes it even worse.
```

Brook's law still stands even with artificial man months.

Teamwork and interpersonal challenges aside, **the hard part of software engineering was never writing the code itself, but rather the systems design, systems architecture, and ownership of knowledge for the software system.**
