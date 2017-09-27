---
layout: post
title: "O'Reilly AI Conference - Part 3"
date: 2017-09-27
excerpt: "My experience at the O'Reilly AI Conference"
tags: [SF, aiconf, deep learning]
comments: true
---

## Prelude

As the final day of the O'Reilly AI conference dawned, I took some time to reflect on the not just AIConf but also Data Science as a field in general. On one hand it feels like there is too much to learn and never enough time. On the other hand, I feel like this is one of the most amazing fields to be in right now. Yet unlike previous revolutions, the internet has made it easy for anyone to follow on with the latest research, hone their skills and contribute back to the community. Truly interesting times to live in.  

### Keynotes

The final day's keynotes continued the theme from previous days theme of covering practical applications of AI in a more strategic sense. Along this theme, Steve Jurvetson's talk on accelerating AI with custom hardware that might ultimately be deployed on edge devices everywhere was something that I had never considered before. One of the bigger barriers to the development of AI systems has been the level of compute and the volume of data required to train these algorithms. Whilst a lot of work is being done on accelerating the software and designing more efficient algorithms, custom hardware could also be key.

Juxtaposed against this visionary discussion was the high mathematical talk by Michael Jordan on Saddle Points. At it's heart, all the algorithms hyped to finally deliver us general AI are curve fitting algorithms that try to find the global optimum value in a search space. Local minima are a problem as it means the algorithm could get stuck and not find the best solution for a particular search space. On the topic of optimising values, the keynotes were topped off by an inspiring call to arms by Tim O'Reilly the founder of O'Reilly media.

Ultimately, AI systems optimise for whatever we set, at least for now, he asked that as technologists we consider not just maximising for profit or raw economic efficiencies and also consider the human impacts of what the systems being developed have and include the human factors into reward functions that we seek or intelligent systems to optimise.

## Morning Sessions

### Self-supervised visual learning and synthesis

This was an intermediate level discussion of developing computer vision neural networks on limited data highlighting research that Professor Efros from the UC Berkeley AI research lab. One of the issues with productionising neural networks for computer vision is the difficulty in acquiring the required samples to make this work. Whilst open datasets now make building algorithms for common objects relatively easy this barrier to entry can be a show stopper for specialised applications in medical and industrial areas. I guess that ties back to Andrew Ng's keynote yesterday when he saw centralised data repositories to stop what is currently some of the highest cost employees in an organisation from spending all their time acquiring data and strategic data acquisition as key parts of being an "AI company".

Where Professor Efros' research fits in this is that he has focused on developing computer vision neural networks without having giant labeled sets of data. The intuition behind this is that we should train networks to identify concepts and not details. For example a toddler after learning to identify cats will identify cats regardless of colour or size or pose but a simple neural network has a much higher change of getting confused. 

Some of the techniques he covered included; breaking an image into chunks and getting the network to predict the missing chunk; taking an image, converting it into black and white then teaching a network to colourise the black and white image; training a network to generate building facades from crude block diagrams and using Conditional Generative Adversarial Neural networks to turn line drawings into full images. A lot of the session focused on this last technique though mostly from a demonstration point of view. Generative Adversarial Neural networks are the topic of a seminal paper by Ian Goodfellow now a top researcher at Google Brain. I won't go into the details here but might do a further post on them later.

Whilst the research covered in the talk was quite interesting, I am not fully sure yet of their practical implications. In theory the neural networks that Professor Efros gave an overview of were able to do quite interesting things the biggest product from it so far is an app that transforms a line drawing into a cat. In theory it means that the neural net has a higher level understanding of the material that it trained on so perhaps there is potential to use the resulting weight matrices to enhance a neural net that identify objects in a camera feed or perhaps it gives a way to more easily train neural networks on small datasets. Watch this space I guess!

### Adversarial Machine Learning

In my overview of the previous talk, I did mention Generative Adversarial Neural networks (GAN). This one was fully dedicated to this topic and explained the principals from the ground up. Generative Adversarial Neural networks. For the details of what a GAN is see this [talk]{https://www.youtube.com/watch?v=HN9NRhm9waY} from Ian Goodfellow himself or [this]{https://www.oreilly.com/learning/generative-adversarial-networks-for-beginners} for a more accessible overview of GANs. 

GANs have been a very important development in the unsupervised learning space but the complexities in architecting and training them make it hard to experiment and work with them without access to large GPU compute arrays. 

## Afternoon Sessions

### High-performance computing opportunities in deep learning

This was a technical talk on building systems to train deep learning networks. As a sidenote I found a  longer version of this talk [here]{https://insidehpc.com/2016/10/hpc-deep-learning-2/} though the state of the art will have moved on since this recording is from a year ago. In the cutdown version, the speaker focused on [DeepBench]{https://github.com/baidu-research/DeepBench} to help identify the best hardware for building deep learning training systems.

I guess key takeaway from this talk was that it requires either a solid investment in hardware or full freedom for data science teams to work on the cloud in order to leverage deep learning technologies. Even then, to iterate quickly requires infrastructure & platform engineers to work closely with data scientists to unlock scalability. 

### All the linear algebra you need for AI

AI isn't mystical, it is just math! It is worth remembering this point and this talk was all about the math behind deep learning. Whilst packages like keras in python make deep learning more accessible, I still think an understanding of the maths behind it is highly desirable as ultimately the run time of algorithms is one of the big blockers in terms of commercialising neural networks and a good understanding of the maths will allow developers to identify which aspects of the code may require optimisation.

The full content of this talke is also available from the fast.ai [github]{https://github.com/fastai/fastai/blob/master/tutorials/linalg_pytorch.ipynb}.

### Reinforcement Learning Overview

This was a high level overview of reinforcement learning by Melanie Warrick from Google. Unlike the previous Uber talk on the same subject that I attended, this was a lot more accessible for the average attendee. I found the slidedesk used [here]{https://speakerdeck.com/nyghtowl/reinforcement-learning}. 

It was a very good example of how to eloquently explain the latest developments in reinforcement learning. Again, however, it reinforced in my mind the complexities involved in developing viable reinforcement learning solutions. Likewise, Andrew Ng commented in his keynote that reinforcement learning whilst very promising currently doesn't hold a lot of immediate business value. 

Reinforcement Learning (RL) is about creating bots, termed agents in the field, that learn to play games. A "game" can be something functional like a robot learning to walk or playing a computer game to get a high score. To put it in a human perspective, toddlers learn over time by randomly moving their limbs and watching adults how to walk. RL tries to match this but in order for the algorithms to work, we need to define a "reward" for it. For say chess, it can be winning a game but how do we define a reward for walking? The easiest way is to task the agent (bot) with the task of getting from A to B but then some really strange walks or crawls or rolls will ensue. So we could redefine the reward as get from A to B using the least amount of energy. It is not clear yet, how we would define and refine these reward functions for practical RL algorithms. 

The second problem with RL is that the action space for the agent needs to be defined. For a physical robot, it can be defined as movements in the actuators but not all problems that we would like an agent to solve are physical. For Deepmind's seminal work on Atari games, the search space is simple. For pong it can move up or down. For the starcraft api, which Deepmind just released, the search space of possible actions is in the hundreds. For an agent to be able to develop valid starraft strategies by randomly trying different combinations of hundreds of possible actions will take a phenominal amount of compute power. 

Reinforcement Learning definitely holds a lot of promise and is the closest that we have come in terms of matching the way that individuals learn thus far. There is still a lot of fundamental research required before it becomes useful more widely in business though. 

### Personalizing ecommerce for two billion people on Facebook

For the final talk, I opted to go to a Facebook one on scaling data science. Facebook is one of the few places that has access to really big datasets and the acumen to develop production systems to leverage this. 

The service that this talk focused on was their service that allows users to buy and see items of interest through their facebook account. At it's heart, There is a recommendation system that prioritises search results to display to users. Given the scale of the recommendations being served the approach is quite different however. They tend to take samples of the data for building their models instead of using the full set and though they have the usual case of ~99% no sale, the can just undersample the no purchase records as ~1% of billions is still a lot!

What I found most interesting was that Data Science at Facebook was viewed as an analysis function. Machine Learning developers were then expected to rewrite the data science routines in C++ for final production. That definitely makes sense where production performance is the key though may not apply for most other organisations. 

Since the O'Reilly AI Conference I had the chance to go to a talk by Randy Shoup from StitchFix who has worked at eBay and Google. He made the good point that although everyone feels like they need to emulate the tech giants, their systems setups and processes are designed precisely to deal with the scale at which they operate. For most organisations copying those is a lot of extra unnecessary complexity.

## Conclusion

It was a great three days at the O'Reilly AI Conference. There were a good mix of technical talks and also more strategic level talks. It was really stimulating to hear Andrew Ng and Steve Jurvetson's thoughts on the strategic direction of AI and where the industry is headed. I look forward to experimenting with some of the packages: Ray, BayesDB that I learned about and also reading more about some of the neural network architectures I read about. 