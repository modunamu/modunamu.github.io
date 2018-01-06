---
layout: post
title: "[MySql] console"
categories: [mysql]
tags: [mysql, console]
description: mysql
---

## 테이블
### 테이블 생성
```
create table [테이블명]
(id int, name varchar(20));
```

### 테이블명 수정
```
alter table [테이블명] rename [변경할테이블명];
ex) alter table asis_table rename tobe_table;
```

### 테이블 삭제
```
drop table [테이블명];
```

## 칼럼
### 칼럼 추가
```
alter table [테이블명] add [칼럼명] [타입] [옵션]; 
ex) alter table test_table add url varchar(255) not null; 
```

## 칼럼 타입 수정
```
alter table [테이블명] modify [칼럼명] varchar(14);
ex) alter table assets modify file_size int(11) not null default '0';
```

## 칼럼명 변경 및 타입 변경
```
alter table [테이블명] change [칼럼명] [변경할칼럼명] varchar(12);
ex) alter table test_table change uri s_3_url varchar(255);
```

## 칼럼 삭제
```
alter table [테이블명] drop [칼럼명];
```