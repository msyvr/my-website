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

### Fringe
- [Obscure but useful Git incantations](https://legends2k.github.io/note/git_nuances/)

---

### The hard parts
- [Git, detached HEAD - Flavio Copes](https://flaviocopes.com/git-detached-head/)

---

### Some standard Git workflows

Combining the current commit with an earlier commit where _target commit < most recent commit_:
```bash
git commit --fixup=<commit hash>
git rebase -i --autosquash main
```
(alternately, use an identifier from the target message)
```bash
git commit --fixup :/<some-identifying-text-from-target-commit-message>
```