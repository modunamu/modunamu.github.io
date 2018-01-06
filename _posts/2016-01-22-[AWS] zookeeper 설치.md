---
layout: post
title: "[AWS] zookeeper설치"
categories: [aws]
tags: [aws, zookeeper]
description: zookeeper
---



download
```
$ wget http://apache.mirror.cdnetworks.com/zookeeper/stable/zookeeper-3.4.8.tar.gz
```

파일이동, 압축해제
```
$ tar zxvf zookeeper-3.4.8.tar.gz
$ sudo mv zookeeper /usr/local/
```

설정 파일 생성(zoo.cfg)
```
$ cd /usr/local/zookeeper/config
$ cp zoo_sample.cfg zoo.cfg
$ vi zoo.cfg
dataDir=/usr/local/zookeeper/data

$ mkdir -p /usr/local/zookeeper/data
```

zookeeper 서버 시작/종료
```
$ /usr/local/zookeeper/bin/zkServer.sh start
$ /usr/local/zookeeper/bin/zkServer.sh ㄴ새ㅔ
```

zookeeper client
```
$ /usr/local/zookeeper/bin/zkCli.sh -server 127.0.0.1:2181
```