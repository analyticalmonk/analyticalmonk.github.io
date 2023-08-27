---
layout:     post
title:      Brief lessons from using LLM APIs in production
comments:   true
description: >
    Lessons that can help you when using large language models (LLMs) in a software production environment

image: /assets/thinker_pixel_art.png
# noindex: true

categories: [ai]
# tags:       [science, technology]
---


One day, I will write a nuanced post about using large language models in production. It will be better than all the nuanced posts published so far about using large language models in production. Until then, here are some brief lessons learnt from building and operating LLM APIs in a production environment for the last 6 months.

_Note: As hard as it may be for you to believe, the above introduction was written by a human. Or not. It’s [hard to tell](https://decrypt.co/149826/openai-quietly-shutters-its-ai-detection-tool)._

**Outline**
1. Chat isn’t always the answer
2. You don’t need to know everything
   a. It doesn’t hurt to know a bit more than you need
3. Tinker
4. Open source is your friend but APIs are not your enemy
5. Demos will take a weekend, production will keep you up on weekends

**Lesson 1: Chat isn’t always the answer**

By now, you must know. If you don’t, you sure should be glad that you are reading this. You probably don’t need to make ChatGPT for X. Maybe you do. Most probably, you don’t.

Chat can be great because it’s flexible. For a lot of use-cases, it’s not great because it’s too flexible. Your users don’t always want to stare at a canvas of infinite possibilities. Sometimes, they need help. If they want to get their professional work done, they definitely could use some help.

What interface do they need then? I don’t know. That’s for you to figure out by [talking with them](https://www.momtestbook.com?ref=akashtandon.in). I can only provide great lessons, not answers.

__Note: Here’s what we have built at [Looppanel](https://www.looppanel.com?ref=akashtandon.in). We don’t allow our users to talk with their interview transcripts. Not yet anyway.
Instead, we provide them with meaningful interview notes tied to evidence (transcript text and timestamp) and their inputs (themes and questions). [Hallucination](https://en.wikipedia.org/wiki/Hallucination_(artificial_intelligence)) isn’t an option when your job is to find out the truth.__

![Looppanel AI notes](/assets/img/ai_note_demo_screenshot.png)

**Lesson 2: You don’t need to know everything**

There’s too much happening all the time. I am not talking about the significant issues of global warming or geopolitics. I am referring to your X (previously Twitter) feed and [Arxiv](https://arxiv.org/list/cs.AI/recent).

You tried but are barely able to keep up. That’s okay. If you try too hard to drink from a firehose, there’s a chance that you will drown.

First, try to figure out what you need to know to make whatever it is you need to make.

**Lesson 2a: It doesn’t hurt to know a little extra**

It’s okay to not know what [RAG](https://www.promptingguide.ai/techniques/rag?ref=akashtandon.in) stands for and why [vector databases are the talk of VC town](https://www.cbinsights.com/research/generative-ai-infrastructure-vector-database/). However, if you have a rudimentary understanding of [embeddings](https://platform.openai.com/docs/guides/embeddings), that will be helpful if a potential business use-case presents itself.

Skim [Andrej Karpathy](https://twitter.com/karpathy/) and [Jeremy Howard](https://twitter.com/jeremyphoward)’s X feeds occasionally. Subscribe to a couple of newsletters or blogs even if you skim them once a week. Don’t try too hard to keep up but use your downtime to explore. If you are feeling adventurous, [try a MOOC](https://www.deeplearning.ai/short-courses/?ref=akashtandon.in).

**Lesson 3: Tinker**

If you want to explore, it’s better to be hands-on. [Talk shit with ChatGPT/Claude/Llama](https://www.reddit.com/r/ChatGPT/comments/15et6f2/well_i_got_what_i_asked_for/) or [port a SOTA LLM in C](https://github.com/ggerganov/llama.cpp). The world’s your oyster. You can learn a lot by tinkering in a field moving as fast as good-old AI is.

It took the experts a while to figure out that asking an LLM to “[think step by step](https://arxiv.org/abs/2205.11916)” can make it work better. Maybe you could’ve done it had you tinkered with a model (while being polite).

**Lesson 4: Open source is your friend but APIs are not your enemy**

Open source is great. Use them as much as you can and give back whenever possible. But if you are on a strict timeline or working out of a VC-funded garage, picking up an API before going through the [Open LLM board](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard?ref=akashtandon.in) may make more sense.

Once you have a validated use-case and method, it can be easier to fine-tune or go all-in on open source.

Note: I can be wrong with this one and starting with OSS may be the answer. I hope to find out more as I tinker with fine-tuning and smaller models.

**Lesson 5: Demos will take a weekend, production will keep you up on weekends**

Sometimes, I wish it were as easy to make an LLM work in production as it is to make a mindblowing demo.  
Then again, where’s the fun in that? I can’t convincingly answer because I was busy figuring out why our GPT-powered pipeline had inexplicably timed out again. :)

Test, test some more and then monitor. Implement some guardrails and checks when passing data to downstream tasks. Add a cache if that makes sense for your use-case.

Things can go wrong on multiple parameters (cost, latency, model drift) and there’s a lot to think about. Chip Huyen wrote about this in [Building LLM applications for production](https://huyenchip.com/2023/04/11/llm-engineering.html?ref=akashtandon.in) that I recommend you read in case you haven’t.

**(Bonus) Lesson 6: Have fun and be responsible**

If you have the privilege of working with the fascinating technology of LLMs, remember to have fun tinkering with it. Be curious and help others understand the technology. Be responsible in its usage and encourage others to do the same.

**In conclusion**

It’s both a joy and occasionally terrifying to witness the shift that’s currently underway. The world has changed recently due to the breakthroughs in AI technology. It will continue to change in ways we can’t imagine right now. Let’s gear up for the ride!








