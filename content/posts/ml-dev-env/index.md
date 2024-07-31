---
title: 'ML dev env'
date: 2024-07-29T22:16:54-07:00
draft: true
author: "Monica Spisar"
authorLink: "https://monicaspisar.com"
description: 'ML dev env'
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

## Initial set up
I'm working on a 2023 M2 MacBook Pro; current OS is Sonoma 14.5. 

Initial components to install for a basic ML set up:
- terminal
- IDE
- Python version management
- Python
- PyTorch
- Jupyter notebook (optional)

## Terminal
[iTerm2](https://iterm2.com/).

## IDE
[VSCode](https://code.visualstudio.com/)
- I've been itching for an excuse to use vim but rumor has it that VSCode is 'better' for machine learning. Full disclosure: I don't yet know what 'better' means in this context but will update here if/when I find out.

## Python version management
[pyenv](https://github.com/pyenv/pyenv) + [pyenv-virtualenv](https://github.com/pyenv/pyenv-virtualenv)
- Working with Python inevitably means making a decision about which tool to use for version and package management. Some folks have strong opinions here: use venv as it's built in; use pyenv - lighter than conda; use poetry - version mgmt + package management + artifact packaging; etc. I recommend initially going with pyenv and consider integrating poetry into the workflow eventually.

## Python


### GPUs/TPUs
For more GPU-intensive work, the MacBook will be insufficient. One option is to use Google Colab pro and buy compute/GPU/TPU time as needed. A potential downside may be that Colab resource allotment is somewhat unpredictable. Other options include setting up a virtual machine on one of the cloud providers, sshing into that machine to do training runs, and renting the provider's dedicated hardware (GPUs/TPUs) on an as-needed basis or on a monthly/annual plan.

_Note for future me_:
- [When to go for (virtual) TPUs](https://www.reddit.com/r/MachineLearning/comments/19e8d1a/d_when_does_it_make_sense_to_train_on_tpu/)
