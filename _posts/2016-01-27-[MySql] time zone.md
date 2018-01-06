---
layout: post
title: "[MySql] time zone"
categories: [mysql]
tags: [mysql]
description: mysql
---

## Time zone
### 현재 time zone 확인
```
mysql> select @@system_time_zone;
+--------------------+
| @@system_time_zone |
+--------------------+
| UTC                |
+--------------------+
1 row in set (0.06 sec)
```

### time zone 변경
```
mysql> set time_zone = 'Asia/Seoul';
Query OK, 0 rows affected (0.14 sec)
```

### 변경 확인
```
mysql> select now() from dual;                                                                                                                                               
+---------------------+
| now()               |
+---------------------+
| 2016-09-06 04:59:07 |
+---------------------+
1 row in set (0.07 sec)
```

* http://bryan.wiki/8