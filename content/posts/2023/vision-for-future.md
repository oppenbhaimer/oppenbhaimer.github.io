---
title: "A Vision for the Future"
date: 2023-12-20T19:51:56+05:30
categories:
- LLM
tags:
- LLM
- Machine Learning
slug: "vision-for-future"
---

![](/posts/2023/res/bots_landscape.jpg "Image Credits: Dall-E 3")

The future is interesting.

With LLMs getting smaller and easier to finetune, in the short term we're
headed towards a multitude of task-specific LLMs rather than one monolithic
Super-AGI. Training data will become more of a focus, and since we're at the
point where LLMs are good enough to clean/generate synthetic data for training,
this scrape/train/deploy loop will keep getting smaller and faster, with human
intervention mostly getting replaced by AI. My personal experiments on
constructing and annotating a small dataset using only open-source LLMs confirm
this. A small model, PEFT/LoRA tuned on a few thousand examples is much better 
at a task than current super-AGI models can hope to be.

But back on topic, because I see this scrape/train/deploy loop getting smaller,
I believe that the next set of contributions will involve engineering this loop,
and making the production line to get these LLMs out in the wild. This would 
enable open-source LLMs to catch up to closed-source monoliths. A few places 
are also working on Crowdsourcing compute. Scaling these models across 
crowdsourced compute has it's own set of problems to solve: distributed
training and inference on nodes which are not available a 100% of the time.
Edge inference is another thing: Nobody wants to connect to a server or API 
endpoint, even if it's convenient. The FSF equivalent in ML is owning your 
weights, and having enough compute to run them. While the latter is not
possible for everyone, trying to make this a reality is another interesting
problem.

This is a manifesto of sorts, I guess. Future research directions in systems 
should focus on constructing this self-learning pipeline. This is more of an 
engineering effort than a research effort (though I won't mind publishing to 
arXiv. Peer review sucks now). And while I might look back and cringe at this 
corny piece of writing, it sets a noble goal, and a novel problem to work
on over the next year.

Here's to building the future!
