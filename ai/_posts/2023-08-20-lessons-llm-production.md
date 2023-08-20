---
layout:     post
title:      Brief lessons from using LLM APIs in production
comments:   true
description: >
    Lessons that can help you when using large language models (LLMs) in a software production environment

image: /
# noindex: true

categories: [ai]
# tags:       [science, technology]
---


One day, I will write a great nuanced post about using large language models in production. It will be better than all the great nuanced posts published so far about using large language models in production. Until then, here are some brief yet useful lessons learnt from building and operating LLM APIs in a production environment for the last 6 months.

Note: As hard as it may be for you to believe, the above introduction was written by a human. Or not. It’s hard to tell. ;)

Lesson 1: It’s not all about the chat window

By now, you must know. If you don’t, you sure should be glad that you are reading this. You probably don’t need to make ChatGPT for X. Maybe you do. Most probably, you don’t.

Chat can be great because it’s flexible. For a lot of use-cases, it’s not great because it’s too flexible. Your users don’t always want to stare at a canvas of infinite possibilities. Sometimes, they need help. If they want to get their work done, they definitely could use some help.

What interface do they need then? I don’t know. That’s for you to figure out by talking with them. I can only give out great lessons, not answers.

Note: Here’s what we have built at Looppanel. We don’t allow our users to talk with their interview transcripts. Not yet anyway. 
Instead, we provide them with meaningful interview notes tied to evidence (transcript text and timestamp) and their inputs (themes and questions). Hallucination isn’t an option when your job is to find out the truth.



Lesson 2: You don’t need to know everything

There’s too much happening all the time. I am not talking about global warming or the wars. I am talking about your Twitter feed and Arxiv. 

You tried but you are barely able to keep up are Andrej Karpathy and Jeremy Howard’s X feeds. That’s okay. First, try to figure out what you need to know to make whatever it is you need to make. Try to drink from this firehose and there’s a chance that you will drown.

Lesson 3: Tinker

If you are going to explore, try to be hands-on. Talk shit with ChatGPT or port a SOTA LLM in C. The world’s your oyster. You can learn a lot by tinkering in a field moving as fast as good-old AI is.

It took a while to figure out that asking an LLM to “think step by step” can make it work better. Maybe you would’ve done it had you tinkered with a model while being polite.

Lesson 4: Open source is your friend but APIs are not your enemy

Open source is great. Use them as much as you can and give back whenever possible. But if you are on a strict timeline or working out of a VC-funded garage, picking up an API before going through the Open LLM board may make more sense.

Once you have a validated use-case and method, it can be easier to fine-tune or go all-in on open source.

Note: I can be wrong with this one and starting with OSS may be the answer. Maybe I will find out as I tinker some more.

Lesson 5: Demos will take a weekend, production will keep you up on weekends

Sometimes, I wish it were as easy to make an LLM work in production as it is to make a mindblowing demo.  
Then again, where’s the fun in that? I can’t answer that because I was busy figuring out why our GPT-powered pipeline had inexplicably timed out again. :)

Test, test some more and then monitor. Implement some guardrails and checks when passing data to downstream tasks. Add a cache if that makes sense for your use-case.

Things can go wrong on a number of parameters (cost, latency, model drift) and there’s a lot to think about. Chip Huyen has an excellent post that I recommend you read in case you haven’t.


Lesson 0: Have fun and be responsible

If you have the privilege of working with the fascinating technology of LLMs, remember to have fun tinkering with it. Be curious and help others understand the technology. Be responsible in its usage and encourage others to do the same.


It’s both a joy and occasionally terrifying to witness the shift that’s currently underway. The world has changed recently due to the breakthroughs in AI technology. It will continue to change in ways we can’t imagine right now. I hope it’s all for the better eventually.




