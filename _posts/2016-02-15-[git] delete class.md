---
layout: post
title: "[git] delete class"
categories: [git]
tags: [git, delete]
description: 
---

### delete
```
$ find . -name "*.class" -exec git rm -f --cached {} \;
```

### commit
```
git add .
git commit -m 'delete class'
```
