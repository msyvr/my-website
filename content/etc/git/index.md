---
title: 'Git wizardry'
date: 2024-07-23T12:08:06-07:00
draft: false
author: "Monica Spisar"
authorLink: "https://monicaspisar.com"
description: 'Resources: Git wizardry'
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

## Fringe
- [Obscure but useful Git incantations](https://legends2k.github.io/note/git_nuances/)

## The hard parts
- [Git, detached HEAD - Flavio Copes](https://flaviocopes.com/git-detached-head/)

## Some standard Git workflows

### Adding the current commit to an earlier commit where...

- target commit = most recent commit:
```bash
git commit --amend
```

- target commit < most recent commit:
```bash
git commit --fixup=<commit hash>
git rebase -i --autosquash main
```
(alternately...)
```bash
git commit --fixup :/<some-identifying-word-from-target-commit-message>
git rebase -i --autosquash main
```