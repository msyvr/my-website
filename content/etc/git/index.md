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
### Under the hood
[Julia Evans' blog](https://jvns.ca/categories/git/ "Git") is a great resource for understanding how Git works.

### Fringe
- [Obscure but useful Git incantations](https://legends2k.github.io/note/git_nuances/)

### The hard parts

- [How git cherry\-pick and revert use 3\-way merge](https://jvns.ca/blog/2023/11/10/how-cherry-pick-and-revert-work/)
- [Git, detached HEAD - Flavio Copes](https://flaviocopes.com/git-detached-head/)

### &#127895;

#### Combining the current commit with an earlier commit where _target commit < most recent commit_:
```bash
git commit --fixup=<commit hash>
git rebase -i --autosquash main
```
#### (alternately, use an identifier from the target message)
```bash
git commit --fixup :/<some-identifying-text-from-target-commit-message>
```