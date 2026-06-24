---
layout:     post
title:      Debugging in the age of agents
comments:   true
description: >
  Coding agents can hand you a confident, detailed, and wrong debugging explanation backed by persuasive evidence. Why the craft of debugging - building hypotheses, gathering evidence, and knowing a system's invariants - matters more than ever.
categories: [ai]
---

A junior engineer once asked me how I had pinpointed possible causes for a bug introduced by code changes I hadn’t worked on. I was surprised by this question at first and didn’t immediately have a great answer. The best I could come up with was that this ability was developed with practice, pattern recognition and awareness of involved systems.

The question feels more important to me now as coding agents have taken off. It is tempting to treat debugging as a tedious software development task that will be automated. But software engineers who have spent time in production trenches can recall not only frustration caused by bugs but also the feeling of exhilaration after successfully debugging and fixing a tricky issue.

![Greg Brockman tweet on the satisfaction of isolating and fixing a hard bug after a week of work](/assets/img/debugging-agents-tweet-1.png)

![Greg Brockman tweet: "sometimes there is no way to debug besides staring at the code until you become enlightened"](/assets/img/debugging-agents-tweet-2.png)

Effective debugging is a mix of hypothesis construction, evidence gathering and rigorous examination. Sometimes the answer can be handed to you on a platter by your observability stack, logs or an agent, but often it requires a mix of intuition and skillful decision making.

I love coding agents and I'm bullish on AI for knowledge work. But there is a particular type of failure I have run into over the last few months when debugging a reasonably large pre-LLM codebase. An agent can produce a confident, detailed, and wrong explanation. This wrong answer can be accompanied with rigorous-looking and persuasive evidence.

For example, recently a coding agent attributed a failure I was investigating to a relatively recent code change even though the relevant behavior predated the diff. Another time, the agent’s proposed explanation could not have occurred because of the application’s schema.

The defense against such agent-side failures is the same discipline good engineers already apply. When something looks like a regression, questions worth asking are:

* Was this regression actually introduced by the code/change being looked into, or does it have a different origin?  
* Is this code path even triggered in the scenario I'm worried about?  
* Does the data model permit the failure being described?

Many confident-but-wrong findings collapse the moment you force them through such questions. Otherwise, an agent can happily attribute long-standing behavior to a new diff, or invent a failure mode the data model doesn't allow.  
Scaffolding around agents can help: a structured review process, good context retrieval, schema information, targeted searches to validate assumptions. But scaffolding only narrows the gap between the possible and correct explanation. For now, that gap often needs a human in the loop.

This lesson matters even more for those new to software development. Agents can confidently develop theories and at times lose confidence about their own results in the face of questioning as well.  If developers rely heavily on agents without developing enough muscle for understanding code and failure modes, they may [not be](https://larsfaye.com/articles/agentic-coding-is-a-trap) [prepared](https://mariozechner.at/posts/2026-03-25-thoughts-on-slowing-the-fuck-down) to judge an agent’s output in critical situations.

So how does one get better at debugging? I don’t think there is a repetitive formula but here are some pointers that can help.

* First, develop a habit of starting from the symptom and working backwards. Articulate the failure. Identify the starting point and recent changes. Track parts of the system that may be responsible.  
* Second, make your hypotheses explicit. Don’t just say “maybe it’s the cache” or “maybe the query is wrong.” Write down what would have to be true for that explanation to work, and then look for evidence that confirms or falsifies it.  
* Third, learn the invariants of the systems you work on. Which fields are always present? Which jobs are idempotent? Which paths are impossible? Which services are eventually consistent? A surprising amount of debugging comes down to knowing which possible explanations cannot actually happen.  
* Finally, when using agents, don’t only ask them for answers. Ask them to show their debugging path. Ask about the assumptions being made, and evidence supporting any claim. You are responsible for verification of the agent's hypothesis as well.

Yes, you should have test suites, observability and great contextual retrieval pipelines for agents. But production codebases, old or new, aren’t perfect. They have their quirks, technical debt and aren’t being overhauled overnight.  
That is why the craft of debugging remains important. As someone building software, you should actively nurture it.

*Thanks to [Ashutosh](https://www.linkedin.com/in/mittalashutosh/) and [Raghav](https://x.com/raghavio) for reading the draft of this.* 
