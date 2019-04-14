---
layout: post
title:  "Introduction to Statistical Learning"
author: Suriya
categories: [ Machine Learning, General ]
tags: [Machine Learning, overview, general]
image: assets/images/2_1.jpg
description: "Introduction to Statistical learning course from Stanford open learning"
featured: true
hidden: false
---

_TL;DR Introducing basic ideas of Statistical learning, supervised, unsupervised etc._

Hi Folks,

Today is Tamil new year - wishing you all happiness and prosperity!!

In [Grab](https://www.linkedin.com/company/grabapp/), there is a push for #BetterEveryDay service - being better each day to serve the customers well. Taking inspiration from there, and in hope to make myself better each day, I am getting starting with the Stanford course on [Introduction to Statistical Learning](https://lagunita.stanford.edu/courses/HumanitiesSciences/StatLearning/Winter2016/about).

In the coming posts, I will share my learning and understanding from the video lectures of the course. Let's get started.

## Examples first

A few everyday scenarios where we come across Statistical Learning:
1. Spam Classification - _Gmail_
2. Handwritten digit recognition - _US Zipcode recognition_
3. Recommendation - _Amazon_


## But isn't it ML?

Hey, but this sounds like Machine Learning right? Where is the boundary between Statistical Learning and Machine Learning?
True. Both Statistical Learning and Machine Learning have a lot of overlap. But a key distinguishing factor is the context.

In Machine Learning, we are bothered with large scale processing and accuracy. But in Statistical Learning, our focus is more towards having an interpretable solution to help quantify precision and uncertainty.

### Types of Learning

As the name suggests, we have a learning task at hand. Given some set of attributes/features, we hope to "_learn_" from the data to perform a particular task. Let's get more concrete here.

*Context* - There is a kid in the playschool with some toys lying around. Say, we have a house-toy and a bicycle-toy.

*Task* - teach the kid to identify the two toys separately

We can do it in two ways:
1. Tell the kid, hey see this. This is a house, and that is a bicycle. Show multiple examples of house and bicycle on road etc and reinforce the knowledge. Over multiple examples, the kid will learn to distinguish between both
2. Give the kid both toys and ask him to feel the toy. Look at the attributes of the toy. Let him feel it. Over multiple trials, the kid will learn to differentiate the toy. He does not know what is a house or a bicycle, but can say hey the one that is square (having sharp edges) id different from the one that is round (based on the wheels)

If we have to give a _technical_ name for these methods, we have:

##### Supervised Learning

It is a learning task, where we have some set of features or attributes (like the toys) and a specific target (like how we show the kid, this is house, this is cycle and so on). Based on this inputs, we _learn_ to perform the task.

So, kind of supervised tasks? These tasks can divided into the following categories:
1. Classification
  * Spam Classification - given some attributes for the email (like common words etc), we can classify into spam or not
  * Digit recognition - given some attributes for digits 0-9, can we classify it into one of the 10 classes
2. Regression
 * House price prediction - Given some attributes of a house, like size, number of bedrooms, etc, can we predict the sale value for a house?
 * Churn prediction - Given attributes of a customer, say his weekly activity on website etc, can we predict the chances/probability of him quitting the platform?

Though it may look like Regression and Classification have similar outputs, we need to keep in mind the key difference between the both.. Classification task aims to put the example in one of the pre-defined classes. We can have 1000 classes, but that is ok. Our output space is constraint to the 1000-classes. But in case of Regression task, the output space is continuous (a.k.a infinite possibilities). The price of the house predicted can take many possible values.

##### Unsupervised Learning

It is a learning task, where we have some set of features or attributes from the data and we need to look for common features, attributes and similarities to _cluster_ the objects together. We may not know what the objects actually are, but we can say, _hey these objects belong together._

Let's look at a simple example - say you have a big shirt-manufacturing unit and people give custom dress size for you to stich and ship to them. Over thousands of such orders, you have different sizes, length, width etc for the dress. Based on that, we could infer meaningful clusters like **s, m, l, xl, xxl** dress sizes. This is because dress with short-length and width tend to share similar properties with "s" class and so on. However you may need domain knowledge to meaningfully infer and interpret the outputs.

One big use case for Unsupervised Learning is cost cutting. In the age of Big-Data today, it is super costly to generate labels for data. Infact, there are companies outsourcing resources to help annotate labels. By using unsupervised learning, we can infer semantic similarities between the groups of objects and use domain expertise to label them effectively.


## Ending Note

In this post, we briefly discuss Statistical Learning, learning tasks, supervised and unsupervised learning and examples/use cases for each of them.

This is meant to be a very general post, and will go more deeper into concepts, derivations and math of the things in the coming post. Stay tuned!

_Cheers,
Suriya_
