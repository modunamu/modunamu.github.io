---
layout: post
title: "[Jenkins] Publish over SSH"
categories: [jenkins]
tags: [jenkins, aws, ssh]
description: [jenkins Publish over SSH]
---



## Publish over SSH
### install
```
플러그인 설치 : Publish over SSH
```

### setting
젠킨스 > 시스템설정 > Publish over SSH > 추가
```
* SSH Server Name : test-aws
* Hostname : 127.0.0.1
* Username : ec2-user
* Use password authentication, or use a different key : 체크
* Key : -----BEGIN RSA PRIVATE KEY-----
* Port : 22
* Timeout (ms) : 300000
```

## 빌더 작업 추가
### Build
* Execute Shell

```
cd test-rest
mvn clean package spring-boot:repackage
```
* Send file or execute command over SSH

```
Source File : test-rest/target/*.jar
Remove prefix : test-rest/target
Remote Directory : test-rest
Exec Commant:
cd test-rest
./start.sh

```





