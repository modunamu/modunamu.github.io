---
layout: post
title: "[git] git flow"
categories: [git]
tags: [git, gitflow]
description: 
---

### install on MAC
```
brew install git-flow-avh
```

### initialize
```
git flow init -d
```

### branch 종류
* master : 최종 릴리즈한 안정화 버전
* develop : 다음 릴리즈를 위해 개발중인 최신 버전
* feature : 특정 기능 개발을 위한 branch
* release : 릴리즈 점검을 위한 branch
* hotfix : 긴급 버그 픽스를 위한 branch
* support : 버전 호환성 문제 처리를 위한 branch


### feature : 특화 기능 개발
```
git flow feature start <branch name>

git flow feature start logback
git flow feature finish logback
```

* http://danielkummer.github.io/git-flow-cheatsheet/index.ko_KR.html
* http://mobicon.tistory.com/280
* 

