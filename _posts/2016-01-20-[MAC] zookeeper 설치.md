---
layout: post
title: "[MAC] zookeeper 설치"
categories: [mac]
tags: [mac, zookeeper]
description: ZonedDateTime
---



## zookeeper 설치
```
$ brew install zookeeper
==> Downloading https://homebrew.bintray.com/bottles/zookeeper-3.4.8.el_capitan.bottle.tar.gz
######################################################################## 100.0%
==> Pouring zookeeper-3.4.8.el_capitan.bottle.tar.gz
==> Caveats
To have launchd start zookeeper now and restart at login:
  brew services start zookeeper
Or, if you don't want/need a background service you can just run:
  zkServer start
==> Summary
🍺  /usr/local/Cellar/zookeeper/3.4.8: 237 files, 17.6M
```

## 설치 경로
/usr/local/Cellar/zookeeper/

## 설정 파일
/usr/local/etc/zookeeper/zoo.cfg
