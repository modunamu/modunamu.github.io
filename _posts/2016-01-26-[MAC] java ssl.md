---
layout: post
title: "[MAC] java ssl"
categories: [mac]
tags: [mac, java, ssl]
description: 
---

## Japa path
```
$ cd /Library/Java/JavaVirtualMachines/jdk1.8.0_74.jdk/Contents/Home/bin
```
## keytool
```
$ sudo keytool -genkey -alias [키저장소별칭] -keyalg RSA -keystore [키저장할파일이름]
예) $ sudo keytool -genkey -alias gluwa-allim-store -keyalg RSA -keystore gluwa-allim-store.jks

$ keytool -list -v -keystore spring-withdraw.jks
```

## 인증서 추출
```
$ sudo keytool -export -alias [만들었던저장소별칭] -keystore [저장소이름] -rfc -file [추출할인증서파일이름]

예) $ sudo keytool -export -alias gluwa-allim-store -keystore gluwa-allim-store.jks -rfc -file gluwa-allim-store.cer
예) $ sudo cat spring-withdraw.cer
```

## trust store
```
$ keytool -import -alias [저장소별칭] -file [인증서] -keystore [trust저장소로만들파일이름]
예) $ keytool -import -alias gluwa-allim-store -file gluwa-allim-store.cer -keystore gluwa-allim-trust-store.jks
```