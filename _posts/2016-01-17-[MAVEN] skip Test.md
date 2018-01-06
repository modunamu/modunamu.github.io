---
layout: post
title:  "[MAVEN] skip Test"
categories: [maven]
tags: [maven, zookeeper]
description: Maven에서 단위 테스트를 생략하는 방법
---

메이븐 package 실행시 skip test

```
$ mvn package -Dmaven.test.skip=true
$ mvn package -DskipTests

$ mvn package spring-boot:repackage -DskipTests
$ mvn clean package -P dev spring-boot:repackage -DskipTests
$ mvn clean package -P prd spring-boot:repackage -DskipTests
```
