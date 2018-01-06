---
layout: post
title: "zookeeper console."
categories: [aws]
tags: [aws, zookeeper, cli]
description: zookeeper
---



create
```
[zkshell: 1] create /zk_test my_data
Created /zk_test
```

delete
```
[zk: localhost:2181(CONNECTED) 43] delete /zk_test/register
```

get
```
[zk: localhost:2181(CONNECTED) 19] get /zk_test
test data
cZxid = 0x4
ctime = Wed May 18 23:58:22 KST 2016
mZxid = 0x4
mtime = Wed May 18 23:58:22 KST 2016
pZxid = 0x6
cversion = 2
dataVersion = 0
aclVersion = 0
ephemeralOwner = 0x0
dataLength = 9
numChildren = 2
```

set
```
[zk: localhost:2181(CONNECTED) 4] set /zk_test apple333
cZxid = 0x4
ctime = Wed May 18 23:58:22 KST 2016
mZxid = 0x18
mtime = Thu May 19 15:41:45 KST 2016
pZxid = 0x6
cversion = 2
dataVersion = 7
aclVersion = 0
ephemeralOwner = 0x0
dataLength = 8
numChildren = 2

[zk: localhost:2181(CONNECTED) 5] get /zk_test
apple333
cZxid = 0x4
ctime = Wed May 18 23:58:22 KST 2016
mZxid = 0x18
mtime = Thu May 19 15:41:45 KST 2016
pZxid = 0x6
cversion = 2
dataVersion = 7
aclVersion = 0
ephemeralOwner = 0x0
dataLength = 8
numChildren = 2
```


ls
```
[zk: localhost:2181(CONNECTED) 21] ls /
[zookeeper, zk_test]
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