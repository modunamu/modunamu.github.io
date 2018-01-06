---
layout: post
title: "[윈도우] elasticsearch 플러그인"
categories: [elasticsearch]
tags: [윈도우, elasticsearch, 플러그인, install]
description: elasticsearch에서 사용할 플러그인 설치
---

## 모니터링
### HQ 모니터링 플러그인 설치
* http://localhost:9200/_plugin/hq/

```
C:\dev\elasticsearch-2.3.3\bin>plugin.bat install royrusso/elasticsearch-HQ
```

### HEAD 모니터링 플러그인 설치
* http://localhost:9200/_plugin/head/

```
C:\dev\elasticsearch-2.3.3\bin>plugin.bat install mobz/elasticsearch-head
C:\dev\elasticsearch-2.3.3\bin>plugin.bat install lukas-vlcek/bigdesk
```

## SQL
### Elasticsearch-SQL
* http://localhost:9200/_plugin/sql/
* https://github.com/NLPchina/elasticsearch-sql

```
C:\dev\elasticsearch-2.3.3\bin>plugin.bat install https://github.com/NLPchina/elasticsearch-sql/releases/download/2.3.3.0/elasticsearch-sql-2.3.3.0.zip
```

