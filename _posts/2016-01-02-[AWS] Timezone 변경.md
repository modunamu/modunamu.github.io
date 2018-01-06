---
layout: post
title:  "[AWS] Timezone 변경"
categories: [aws]
tags: [aws]
description: AMI배포판의 timezone을 localtime(서울)로 변경하는 방법 입니다.
---

AWS에서 AMI timezone 변경하기
=====
기본적으로 설치되는 AMI는 timezone이 utc로 설정되어 있습니다.
한국에서만 서비스 한다면 timezone을 한국으로 변경 합니다.

### date 확인
```
$ date
Fri Jan  2 06:41:49 UTC 2016
```

### lcoaltime 확인 
```
$ sudo date
Fri Jan  2 06:42:01 UTC 2016
 
$ sudo cat /etc/localtime
TZif2UTCTZif2UTC
UTC0
```

### 설정된 utc 로컬타임 삭제
``` 
$ sudo rm /etc/localtime
```

### 서울로 localtime 심볼링 링크
``` 
$ sudo ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime
```

### 변경된 date 확인
``` 
$ date
Fri Jan 2 21:44:45 KST 2016
 
$ sudo date
Fri Jan 2 21:45:34 KST 2016
```
