---
layout: post
title: "[git] Gitlab - ssh"
categories: [git]
tags: [git, ssh]
description: 
---

### SSH keys
```
cat ~/.ssh/id_rsa.pub
ssh-keygen -t rsa -C "testemail@gmail.com"
```

### gitlab 등록
* https://gitlab.com/profile/keys

### git 설정
```
$ git remote rm origin
$ git remote add origin git@gitlab.com:gitlabid/test-project.git
```

