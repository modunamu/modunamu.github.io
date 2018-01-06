---
layout: post
title: "[MAC] zookeeper start, stop"
categories: [mac]
tags: [mac, zookeeper]
description: zookeeper
---



## zkeeper start
```
zkServer start
ZooKeeper JMX enabled by default
Using config: /usr/local/etc/zookeeper/zoo.cfg
Starting zookeeper ... STARTED
```


## zkeeper stop
```
$ zkServer stop
ZooKeeper JMX enabled by default
Using config: /usr/local/etc/zookeeper/zoo.cfg
Stopping zookeeper ... no zookeeper to stop (could not find file /usr/local/var/run/zookeeper/data/zookeeper_server.pid)
```