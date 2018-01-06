---
layout: post
title: "[윈도우] elasticsearch 설치"
categories: [elasticsearch]
tags: [윈도우, elasticsearch, 설치, install]
description: 윈도우 elasticsearch 설치
---

### Java 환경변수(시스템변수)
```
JAVA_HOME : C:\Java\jdk1.8.0_65
Path : %JAVA_HOME%\bin;
```


### 다운로드
```
https://www.elastic.co/downloads/elasticsearch
```

### 압축풀기
```
c:\dev\elasticsearch
```

### 설치
```
C:\dev\elasticsearch-2.3.3\bin>service.bat install

Installing service      :  "elasticsearch-service-x64"
Using JAVA_HOME (64-bit):  "C:\Java\jdk1.8.0_65"
The service 'elasticsearch-service-x64' has been installed.

```

### elasticsearch 환경설정
```
C:\dev\elasticsearch-2.3.3\config\elasticsearch.yml

cluster.name: es_cluster
node.name: es_node

```


### 시작
```
C:\dev\elasticsearch-2.3.3\bin>service.bat start
The service 'elasticsearch-service-x64' has been started
```

### 종료
```
C:\dev\elasticsearch-2.3.3\bin>service.bat stop
The service 'elasticsearch-service-x64' has been stopped
```

### 서비스 확인(브라우져)
```
http://localhost:9200
{
  "name" : "Ikthalon",
  "cluster_name" : "elasticsearch",
  "version" : {
    "number" : "2.3.3",
    "build_hash" : "218bdf10790eef486ff2c41a3df5cfa32dadcfde",
    "build_timestamp" : "2016-05-17T15:40:04Z",
    "build_snapshot" : false,
    "lucene_version" : "5.5.0"
  },
  "tagline" : "You Know, for Search"
}
```