---
title: 'Ml Ak Llms Busy People'
date: 2024-07-28T21:53:40-07:00
draft: true
author: "Monica Spisar"
authorLink: "https://monicaspisar.com"
description: 'Ml Ak Llms Busy People'
images: 
- "/posts/.../....png"
tags: []
categories: []
resources:
- name: "foo"
  src: "foo.png"
math:
  enable: true
---

[Intro to Large Language Models - Karpathy (YouTube)](https://www.youtube.com/watch?v=zjkBMFhNj_g)

### Reading list
[Reading List For Andrej Karpathy’s “Intro to Large Language Models” Video \| Oxen\.ai](https://www.oxen.ai/blog/reading-list-for-andrej-karpathys-intro-to-large-language-models-video)

### Notes

- perspective: llm parameters represent a mix of the training data but not the training data itself (unless overfitting?)
  - that's why models seem to hallucinate: they're guessing at what the world is, but don't actually know/represent it
  - during training, optimizing parameters = better approximating the _known_ world as represented by the dataset
  - !but! it's an approximation, even for items from the training set (is this accurate? test it out!)

- observe parameter 'development' during training
  - how to efficiently track?

#### dumb idea?:

(example numbers)
- 250B parameters
- 40 iterations

1. chart parameter vs iteration for all parameters
2. look at moments of those charts
3. 'search' for parameters correlated in terms of chart shape for all moments
4. look at correlated parameters' generation functions

#### parameters as a compression of the training data

- does compression generally require a clear semantic definition of what's being compressed?
- if so, what's the clear semantic definition of '10 TB of internet data'? (is that what was used to train llama70B?)

I guess I'm asking: what is being modeled by the models? 
- eg: If you train a model on, say, a bunch of circuit designs and then ask it to design a circuit for a specific purpose that's non-trivial - is the expectation that it would succeed by replicating the most common patterns in circuits generally? or would it be possible only if the training set labelled what each circuit did?

#### !very much wip! definition of machine learning model? neural network?

A machine learning model consists of functions which mediate relationships between its architectural components to dynamically determine the transfer function of the model via training on test data, where the aim is to generate - from new inputs - outputs that align with the model's objectives.

That's a lot of words. Here's a concrete example: a library of i

In the case of neural networks, the architecture consists of layers of nodes: multilayer perceptrons. Deep neural networks have 3 or more layers: an input layer, output layer, and intermediate layer(s). 

The intermediate layers are the 'hidden' layers, with parameters that evolve during training. The initial parameter values are known, and their final values become part of the model definition. Their intermediate values update in each training epoch in response to the backpropagation algorithm, and depend on: 1. loss function, 2. step size, 3. layer-based compression function (there's a term for this that's escaping me atm!), and 4. training data set. The values themselves can, in principle, be probed and emitted for each epoch, but the semantics of the collective intermediate state is not well understood. 

Although their structure (number of layers (depth) and number of nodes at each layer (width)) is fixed/known, the exact relationships between the layers updates during model training. As a concrete example, let's say two nodes are initialized to linearly combine with weights of a and b; during training, a and b will evolve based on output evaluation, until some measure of model error has been minimized.

The function governing those updates is known, but the actual values assumed at each training iteration is computed per iteration. Those values are important in that they literally determine the model's output for a given new input. 

For a large enough number of weights/parameters and iterations, those intermediate values - the trajectory of values during training - is, in practice, 'unknown' in the sense of the semantic relationship between those values, their trajectories, and the training data. -  is  parameters 'weight' the influence of contributing nodes to the subsequent layer of the network.