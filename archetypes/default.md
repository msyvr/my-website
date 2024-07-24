---
title: '{{ replace .File.ContentBaseName "-" " " | title }}'
date: {{ .Date }}
draft: true
author: "Monica Spisar"
authorLink: "https://monicaspisar.com"
description: '{{ replace .File.ContentBaseName "-" " " | title }}'
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
