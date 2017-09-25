---
layout: post
title: "O'Reilly AI Conference - Part 1"
date: 2017-09-21
excerpt: "My experience at the O'Reilly AI Conference"
tags: [SF, aiconf, deep learning]
comments: true
---

## Prelude

[Part 2]{{ site.baseurl }}{% post_url O'Reilly-AI-Conference-Part-2 %}
As a Data Scientist, visiting Silicon Valley has always seemed like something I had to cross off the bucket list. 
What better way than to attend the O'Reilly AI Conference to see where the state of the art was at.
I signed up for the Monday tutorials as well and in this post I will cover some of my experienced with those.

### Session 1 - Probabilistic Programming

For the morning session I decided to go to the Probabilistic Programming session with Vikash Mansinghka.
With the increasing profile of Bayesian Methods, I have always wanted to learn more about the area.
Whilst I have been slowly working my way through the excellent book [Statistical Rethinking](https://www.amazon.com/Statistical-Rethinking-Bayesian-Examples-Chapman/dp/1482253445) I wanted to see where the cutting edge reesarch was.
This session turned out to mainly be a high level overview of [BayesDB](http://probcomp.org/bayesdb/) as a system for analysing raw, unprocessed data.

For the demo and the training they had setup a bunch of cloud hosted instances of BayesDB for each of the participants Unfortunately due to poor network bandwidth at the venue, Hilton Hotel Union Square, we were unable to proceed with the training.
I was personally able to access the server and followed some of the exercises in the Jupyter Notebooks. Probabilisitic search and the dependency analysis seems like quite a useful tool set. I'd definitely be keen to plug in some of the datasets that I have at work to see how BayesDB performs.
Using the CrossCat libraries, BayesDB looks to be a useful initial EDA tool to quickly identify interesting columns for further detailed exploration.
The language to query BayesDB and generate analysis from it is very SQL like.
The hardware requirements, 60GB RAM and 32 CPU Cores seem quite high though in this era of cloud computing isn't that big a barrier. At my current job where we are not yet allowed to utilise the cloud it is quite a bottleneck however. 

It will be interesting to compare the results from the probabilistic query engine versus the results from a standard correlation and pair plot.

### Session 2 - Building Reinforcement Learning Applications with Ray

Ray is a parallel computing package in python designed to help with parallel training of reinforcement learning agents. 
The process to make a standard python function ready for parallel is quite simple just requiring an extra decorator `@ray.remote` before the function definition.
Inside the main loop python loop there is more thought required though on when to trigger the distributed job through the `ray.get()` function to ensure that it is able to run in parallel efficiently.
That can be abit hard to work with at first requiring a bit of practice to get used to though not dissimilar to choosing when to run `.collect()` for Apache Spark routines.

I can see the logic around the packages design. The additonal decorator, the `.remote()` calls were probably chosen to make retrofitting code simple. What was not covered during the tutorials however were the setup processes and clustering requirements.
From my own experience setting up Hadoop clusters using the Hortonworks Data Platform the setup process can be bumpy due to issues with ports and firewalls. Also briefly discussed but not explored in detail was the shared memory tier of ray. 
When transitioning from working on a single server to working with a distributed system thought needs to be given to how data is persisted. Transferring data over a network is a very high latency job compared to just working in local RAM.
 
The ray tutorial covered all the basics but didn't get too in depth into training and designing of reinforcement learning agents, something that I will have to explore on my own.

## Conclusion

Overall both sessions were worth it, though given the time and need to appeal to a broad audience the material covered was more basic than I would have personally liked.
