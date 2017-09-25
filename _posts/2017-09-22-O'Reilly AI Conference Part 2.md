---
layout: post
title: "O'Reilly AI Conference - Part 2"
date: 2017-09-22
excerpt: "My experience at the O'Reilly AI Conference Part 2"
tags: [SF, aiconf, deep learning]
comments: true
---

## Prelude

[Part 1]({{ site.baseurl }}{% post_url O'Reilly-AI-Conference %})
Day 2 was the first full day of seminars. I attended the speed networking session in the morning as well. 
As a first time speed networker I found it a very unique experience like giving an elevator pitch.
For those who have never tried, you line up a two rows, everyone with a partner. First one person speaks for a minute then the other. 
Contacts are exchanged then you rotate to a different partner. Whilst I found it tiring to repeat myself over and over, I think it was definitely good practice a presenting yourself.

### Keynotes

As someone more interested in technical details and the intricacies of implementation, I didn't find the strategic focus of the keynotes that engaging.
Given the mix of business executives, team leads and practioners attending keeping it general did make sense thugh. The one interesting exception though was the keynote by Andrew Ng. He covered not just the practicalities of AI but also how his interpretation of what constitutes an internet company and what constitutes an AI company. 
In his mind, an internet company was not just about having a website but about empowering engineers and product managers to make decisions based on A/B testing with quick development cycles.
Likewise, his thoughts on Artificial Intelligence was that Machine Learning + an Internet company =/= an AI company.
An AI company in his mind would require strategic thinking about data acquisition, centralised data repositories to give artificial intelligence algorithms the data to perform and extensive automation. 
As a professor, Andrew didn't utilise any slides and instead lectured on whiteboards which the audience all rushed forward to photograph at the end of his keynote.

### Morning Lectures

#### Escaping the forest, falling into the net: Pinterest

The first talk was from the Pinterest data science team about their move away from utilising gradient boosting trees towards using neural nets for identifying interesting pins for users.
The journey that the team went through seemed quite typical, issues with different formats of inputs and required. An interesting note was that neural nets worked better with raw features.
Possibly this is due to the fact that the increased complexity of a neural net allows it to model non-linearities better. Other issues they came across were variations between the features that they had initially used to train their neural net versus the features that were fed into the algorithm once it was deployed.

Lately, I have been working a lot on logging and monitoring from a more traditional IT infrastructure and application development point of view and it seems like some of these issues that arose, variations between inputs used during development and in final production seems like something that can be picked up through logging and monitoring procedures. I am unsure of whether this would be more efficient than regular A/B testing though it could be an option. I might write a follow up post later on logging and monitoring for algorithms development. 

#### Backing off toward simplicity: Salesforce Research

Stephen Merity gave a highly polished and insightful talk on deep learning for text analysis. It was a two part talk with the first part being more about language models in general whilst the 2nd part focused on his efforts to build simple models that could still perform like state of the art models. 

In part 1, He advocates choosing simple models and only resorting to deep learning methods when there is a very clear reason why they should be used. Deep learning models are time consuming to train and very hard to debug. This I can definitely see, whllst there are methods to "peer" into deep learning models for computer vision these same methods do not give much insight into how deep learning models handle text. He also highlighted that much of our intuition into how deep learning works have been proven time and time again to be false and hence furrher reason that we should be careful in our application of these techniques and not be blinded by hype.

For part 2, the focus was on streamlining deep learning models by trying to build the best baseline models possible. I found this part a bit advanced for me as I am not up to date on developments in =deep learning for text but Stephen's explanations of why he did what he did and the end effects were still clearly explained in a way that was approachable to all. It also highlighted the importance of understanding the maths behind these algorithms so that you can identify where the performance bottlenecks are for these algorithms. 

I found this talk to be highly informative and clearly presented. It also highlighted to me that our collective understanding of deep learning is still not there which will become more and more of an issue as time goes on and the level of trust in these algorithms increases. Just look at the headlines generated by the Tesla autopilot crashes this year. Whilst I do not know the intricacies of the autopilot function, the fact that a computer crashed in a scenario that a human could have easily avoided raised much consternation. It also seemed to me that most current deep learning research focused on finding new and innovative ways to stitch together layers and neurons in neural nets whereas if we hold replicating the brain as our ultimate goal in the AI field, it naturally forms connections and structures. But lets just hold that thought for now.    

### Afternoon Lectures

#### Deep Learning with limited data: Cardiogram

This lecture covered methods for training on smaller datasets with an eye on applying it to medical imaging and diagnosis. New tidbits I learned were to read up more on one-shot learning, siamese networks and applications for autoencoders. The speakers tried to balance between theory and implementation . Time to read through some papers I think! 

#### Deep reinforcement learning: Uber

I was hoping that this lecture would discuss the ins and outs of deep reinforcement learning and some practical applications for it but it was more an academic overview of the area. It covered the theory behind agents, the nature of what a reward function and the concept of an environment. I felt it was basically a brief version of Andrej Karpathy's excellent post [Deep Reinforcement Learning: Pong from Pixels] {http://karpathy.github.io/2016/05/31/rl/}. 

## Conclusion

Overall a very busy day. It really reinforced in my mind the cutting edge nature of deep learning and reinforcement learning. To understand the latest state of the art requires keeping up with arxiv papers and journals. 