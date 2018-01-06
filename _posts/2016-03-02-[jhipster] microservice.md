---
layout: post
title: "[jhipster] microservice"
categories: [jhipster]
tags: [jhipster, microservice]
description: microservice
---

### docker
```
$ docker-machine ls
$ docker-machine start default
$ docker-machine env default
$ eval $(docker-machine env default)
```

### 폴더 만들기
```
$ mkdir foo-service bar-service gateway docker
```

### registery
* http://127.0.0.1:8761
```
$ docker run -p 8761:8761 jhipster/jhipster-registry

$ mvn package docker:build

$ ./mvnw
$ ./mvnw -Pprod package
```

### microservice 생성
```
$ yo jhipster
$ yo jhipster:import-jdl yourJdlFile.jh
```

### 도커 컴파일
```
$ mvn package -Pprod docker:build
```

### docker-compose
```
$ cd docker
$ yo jhipster:docker-compose
$ docker-compose up -d
```

### start service
```
$ docker-compose -f jhipster-registry.yml start
$ docker-compose -f gateway.yml start
$ docker-compose -f foo-service.yml start
```

* https://github.com/PierreBesson/jhipster-microservices-docker/blob/master/README.md
* http://stytex.de/blog/2016/03/25/jhipster3-microservice-tutorial/
