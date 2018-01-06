---
layout: post
title:  "[AWS] JAVA 1.8 설치"
categories: [aws]
tags: [aws]
description: aws에 Java 1.8 설치
---



```
$ sudo wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo

$ sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo

$ sudo yum install -y apache-maven

$ mvn --version

$ mvn compile
```
