---
title: 'Neural networks'
date: 2024-07-24T18:31:26-07:00
draft: false
author: "Monica Spisar"
authorLink: "https://monicaspisar.com"
description: 'Resources: Neural networks'
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

## Training data

For supervised machine learning, the training data is labeled.

For a generative general-purpose language model, a typical training data set might be, say, 10TB of text scraped from the internet; the goal is for the training text to ~represent general knowledge.

A smaller set of domain-specific training data can be used to fine-tune a general purpose model previously trained on the larger, more general data set.

### Synthetic training data
[Machine Learning for Synthetic Data Generation: A Review](https://arxiv.org/abs/2302.04062)

[Cosmopedia\: how to create large\-scale synthetic data for pre\-training Large Language Models](https://huggingface.co/blog/cosmopedia)

## Architectures

### Convolutional neural nets
[CNN explainer - visualization, Georgia Tech](https://poloclub.github.io/cnn-explainer/)

[An Interactive Node-Link Visualization of Convolutional Neural Networks - Adam Harley](https://adamharley.com/nn_vis/)

### Transformers
[The Illustrated Transformer – Jay Alammar: Visualizing machine learning one concept at a time.](https://jalammar.github.io/illustrated-transformer/)

### Reinforcement learning
- main parameter set (base model from general info dataset, eg subset of internet)
- finetune: retrain model using much smaller domain-specific dataset
  - RLHF: alternately (and/or) have humans choose from options offered by the (finetuned?) model

## Fine tuning

### Domain-adaptive pre-training
[Continual Pre-training of Language Models](https://arxiv.org/abs/2302.03241)

## Optimization techniques

### Batch norm
[How does batch normalization help optimization? (pdf)](https://arxiv.org/pdf/1805.11604)

### Random initialization
[Randomly Initialized One-Layer Neural Networks Make Data Linearly Separable](https://arxiv.org/abs/2205.11716)

## Selecting model components
### Loss functions
- A model's loss function quantifies the difference between the model prediction and the known value; the result is used by the backpropagation algorithm to improve model parameters in subsequent training epochs.

- The function should be selected according to the purpose of the model, but a standard loss function is the mean squared error $ MSE = \sum_{i=1}^{D}(x_i-y_i)^2 $, where $ x_i $ is the prediction and $ y_i $ is the known value.

[Loss Functions and Metrics in Deep Learning](https://arxiv.org/abs/2307.02694)

[Choice of loss function matters: Inside the maths that drives AI](https://www.nature.com/articles/d41586-024-02185-z)

## Model selection, evaluation, benchmarking:
[GPT in Data Science (model selection)](https://arxiv.org/pdf/2311.11516)

[Evaluating Large Language Models Trained on Code](https://arxiv.org/abs/2107.03374)

[Benchmarking inference providers](https://www.braintrust.dev/docs/cookbook/recipes/ProviderBenchmark)

## Interpretability
[OthelloGPT learned a bag of heuristics — LessWrong](https://www.lesswrong.com/posts/gcpNuEZnxAPayaKBY/othellogpt-learned-a-bag-of-heuristics-1)

[(2015) Visualizing and understanding DNNs - Matt Zeiler, Clarifai](https://youtu.be/ghEmQSxT6tw)

## Etc
### LLM Prompting
[A Control Theory of LLM Prompting](https://arxiv.org/abs/2310.04444)

### Non-gradient methods
[Detailed answer to: Is it possible to train a neural network without backpropagation? - Stack Overflow](https://stats.stackexchange.com/a/235868)

---

## In practice: code!
### Karpathy: Micrograd
[karpathy/micrograd: A tiny scalar\-valued autograd engine and a neural net library on top of it with PyTorch-like API (github)](https://github.com/karpathy/micrograd)

[The spelled\-out intro to neural networks and backpropagation: building micrograd (YouTube)](https://www.youtube.com/watch?v=VMj-3S1tku0)

### Karpathy: Neural networks
[Neural networks: zero to hero](https://www.youtube.com/watch?v=VMj-3S1tku0&list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ), [Implement GPT2](https://www.youtube.com/watch?v=l8pRSuU81PU)

---

## Courses / course notes

[MIT 6.867 Machine Learning (grad)](https://github.com/peteflorence/MachineLearning6.867)