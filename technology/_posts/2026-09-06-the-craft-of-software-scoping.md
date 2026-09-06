---
layout:     post
title:      The craft of software scoping
comments:   true
description: >
  AI has made software dramatically faster to build, but it hasn't removed the need for judgment. Five principles that helped my teams go from a vague problem statement to a precise solution, with limited resources and plenty of ambiguity.
categories: [technology]
---

As an engineer or a product lead, you have been asked:

* Can we do this?
* How hard is this?
* How long will this take?
* What is the best way to solve this?

These questions touch on different aspects of [risks](https://www.svpg.com/four-big-risks/) (value, usability, feasibility, viability) that come up when building any product. If you have been building software long enough, you realize the importance of these questions. Scoping is one way to answer them well.

AI has made software dramatically faster to build but that doesn't remove the need for judgment. If anything, this makes good scoping, i.e. deciding what and how to build, more important. Before getting into the principles for scoping well, let me clarify what I mean by the term.

## Scoping, not estimation

By scoping, I mean the craft of going from a technical problem statement or business requirement to a precise proposed solution. This is different from pure time estimation where you come up with a timeline number in days/weeks/months for a particular solution to a problem. Scoping includes elements of estimation but focuses more on the validity and context of the problem statement in addition to coming up with an eventual solution.

Much has been written about the [failure to estimate](https://world.hey.com/dhh/software-estimates-have-never-worked-and-never-will-a41a9c71) [software work](https://erikbern.com/2019/04/15/why-software-projects-take-longer-than-you-think-a-statistical-model.html). I agree with those opinions. This doesn't mean we should give up and never provide timelines. Instead, our goal should be to scope a problem well and often work our way backwards from a time budget instead of providing unreliable time estimates upfront.

## Scoping principles

Even though AI has made software development much faster, you still have limits. They can be in terms of tokens, mental bandwidth or infrastructure cost in addition to time. There is still no free lunch. In fact, as the cost of building falls, these constraints become more important.

Below, I am sharing pointers that helped me and my teams consistently deliver production software with limited resources and often with ambiguity.

* Understand the why
* Sometimes, saying no is the right thing
* Experience, don't just show or tell
* Address the unknown
* Start with a time budget, not the other way round

### 1. Understand the why

Everything happens for a reason. Every problem statement or request that comes your way has a why behind it. That doesn't mean the why may be justified or worth your team's resources and time. Even in cases where the problem statement warrants work, the understanding may be incomplete. As someone tasked with building a solution, you should get as good an understanding as possible.

Depending on the stage, culture and domain of your company, this can involve anything from asking a lot of questions and reading documents to directly engaging with a customer.

For example, you may be asked to build integrations with Google Drive to ingest PDF/CSV as data sources for your customers in a month. This sounds like a straightforward integration task.

But the real question is whether customers need a unified searchable repository or simply better access to their raw interview data. You should aim to understand:

* What building the feature will solve from a business point of view
* what triggered this requirement from an end user
* where the timeline originated.

The end goal can range from closing a couple of large enterprise deals to solving a repeated ask from customers dealing with a variety of data sources. Knowing the why will help you better define the scope of your solution.

Sometimes, you need to build with incomplete information. In those cases, your scope can include the need to gather more information without putting in a large amount of resources.

In most early stage startups, finding PMF is the single most important thing. To do that, sometimes you should just build that search feature. But your decision-making and implementation can be much better if you know why the search is needed at a particular date.

### 2. Sometimes, saying no is the right thing

Saying no is the simplest thing to do in theory. It may be the hardest point to practice well from this list. You can't just shoot down something because it is hard or agree because it is easy.

Once you understand why something needs to be built, the next question is whether it is worth building at all. Your decision should be based on relevant trade-offs: technical, business and/or cost to name a few.

Even if AI agents let you build a feature 10 times as easily, it may negatively affect an end-user's experience or increase your infrastructure cost. It can also waste all kinds of resources from your team that could've been put to better use elsewhere - tokens, focus, sales collateral, marketing budget.

For example, a feature may take an AI agent a few hours to build but require significant infrastructure work to satisfy the same enterprise customer's requirement around data residency.

There are many times when you should not hesitate or overthink. For example, at a pre-PMF startup, moving fast can give you a high alpha if you learn from a mistake. I am not talking about those situations as much because in my experience, builders are more prone to saying yes than no. 🙂

### 3. Experience, don't just show or tell

With AI agents, it has become ridiculously easy to build a minimal usable version of a small app or a feature. When building becomes this cheap, sitting in a crude version of the user's seat can be more valuable than discussing the idea abstractly. This can lead to better brainstorming, feasibility evaluations and more. There is no excuse to not take this approach now.

For example, a couple of years ago, instead of debating whether our users would want a natural language search, I built a crude version, put our own research data into it and asked our team to try it out. We were then able to build conviction, quickly iterate with internal feedback and finalize its scope in a few days.

<p style="text-align: center;">
  <img src="/assets/img/scoping-just-build-a-prototype.png" alt="Bell curve meme: the low and high ends both say &quot;Just build a prototype&quot; while the middle says &quot;Nooo you must first write a PRD, then make a design, then make tickets, then...&quot;" style="width: 100%; max-width: 368px;" />
</p>

### 4. Address the unknown

The previous point was about reducing uncertainty by simulating user experience. This one is about identifying the potential implementation details that you don't yet understand.

Many software projects get delayed because of uncertain aspects. This can include a new API, a marketplace listing process or a new framework. That is why simply breaking down a problem statement into smaller chunks is not enough. You need to identify and isolate the most uncertain parts, and systematically address them before anything else.

As a rule of thumb, third-party dependencies are almost never a hoot. Even if you plan to use an industry-standard tool, marketplace or API, you better familiarize yourself quickly. If there is an approval process involved, go take a look at forums and independent experiences, not just the official docs. (*Yes, I have been burnt in the past.*)

AI can now help you reduce the uncertainties quicker than manual research or building. For example, create deep research reports, build working prototypes or, if token limits allow, ask your agent to do whatever it takes (with a clearly specified goal of course). I recommend that you [RTFM](https://en.wikipedia.org/wiki/RTFM) but you can cover a lot of ground beforehand or in parallel.

### 5. Start with a time budget, not the other way round

We had started by talking about the failure of software estimation. That being said, you can't just wave your hand and work without any timelines.

If something is worth doing, you should decide how much time you are willing to spend on it. If you have collaborators or stakeholders, align on a time budget for a project. If you are working solo, practice [timeboxing](https://en.wikipedia.org/wiki/Timeboxing).

This need not be set in stone on day 1 either. As your understanding of the reasons, goals, and unknowns improve, you may improvise on either the scope or the timeline.

<p style="text-align: center;">
  <img src="/assets/img/xkcd-1425-tasks.png" alt="xkcd comic: a user asks for an app that checks whether a photo was taken in a national park (&quot;easy GIS lookup, a few hours&quot;) and whether the photo is of a bird (&quot;I'll need a research team and five years&quot;)" style="width: 100%; max-width: 221px;" />
  <br/>
  <em><a href="https://xkcd.com/1425/">xkcd #1425, "Tasks"</a></em>
</p>

## Wrapping up

My point of view on this topic has been shaped by my experiences at early-stage, fast-moving and growing startups with no appetite for bureaucracy. If you work at a large enough company, e.g. FAANG or a Fortune 500 enterprise, there will be additional considerations that I won't get into. You can look at [this blog](https://www.seangoedecke.com/how-i-estimate-work/) for some perspective.

However, considering the current AI-charged environment, I hope even large companies will continue to focus more on the craft of building software and less on the bureaucratic side.

AI hasn't made scoping obsolete. It has changed what good scoping looks like. When building and experimentation become cheaper, judgment becomes precious. This includes understanding why a problem matters, deciding what not to build, setting constraints, experiencing the solution and identifying uncertainty early.

You can build more than ever before. Good scoping helps you decide what to build and do it well.

### Resources

* [How to scope work](https://highgrowthengineering.substack.com/p/how-to-scope-work-)
* [How I estimate work](https://www.seangoedecke.com/how-i-estimate-work)
* [Software estimates have never worked and never will](https://world.hey.com/dhh/software-estimates-have-never-worked-and-never-will-a41a9c71)
* [Why software projects take longer than you think: a statistical model](https://erikbern.com/2019/04/15/why-software-projects-take-longer-than-you-think-a-statistical-model.html)
