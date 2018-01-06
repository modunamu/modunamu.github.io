---
layout: post
title: "2[윈도우] elasticsearch  Kibana 설치"
categories: [elasticsearch]
tags: [윈도우, elasticsearch, Kibna, 플러그인, install]
description: elasticsearch에서 사용할 플러그인 설치
---


### Kibana 다운로드
```
https://www.elastic.co/products/kibana
```

### Kibana 압축해제(엘라스틱\plugins)
```
C:\dev\elasticsearch-2.3.3\plugins\kibana-4.5.1-windows
```

### Kibana 환경설정
* http://localhost:5601/

```
C:\dev\elasticsearch-2.3.3\plugins\kibana\config\elasticsearch.yml

elasticsearch.url: "http://localhost:9200"
```

### Sense
* http://localhost:5601/


## Sense
* http://localhost:5601/

```
C:\dev\kibana-4.5.1-windows\bin>kibana plugin --install elastic/sense
```


