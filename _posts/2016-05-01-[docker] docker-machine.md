---
layout: post
title: "[docker] docker-machine"
categories: [docker]
tags: [docker, docker-machine]
description: 
---

### create
```
$ docker-machine create --driver virtualbox dev
```

### start
```
$ docker-machine start dev
```

### env
```
$ docker-machine env dev
$ eval $(docker-machine env dev)
```

### 접속 정보
```
$ docker-machine config dev
```

### ps
```
docker ps -a
docker rm 596281c5ab28
```

### remove
```
docker-machine stop dev
eval $(docker-machine env -u)
docker-machine rm dev
```

### log
```
docker logs 74221398eb95
```


* http://blog.saltfactory.net/docker/running-docker-on-mac-using-with-docker-machine.html



docker run -d -p 8761:8761 jhipster/jhipster-registry


docker run -d -p 8761:8761 jhipster/jhipster-registry
docker run -d -p 8080:8080 gateway

docker-compose -f jhipster-registry.yml start
docker-compose -f gateway.yml start