---
layout: post
title: "[Spring Boot] @Scheduler"
categories: [Spring Boot]
tags: [spring boot]
description: Scheduler 어노테이션으로 cron 설정하기
---
<!-- 
Spring Boot에서 @Scheduler 어노테이션으로 cron 설정하기
===== 
-->


@Scheduled(cron = "0 1 1 * * ?")
* "0 0 * * * *" = 시간마다 정시에 실행
* "*/10 * * * * *" = 10초, 20초, 30초, 40초, 50초, 0초 에 실행
* "0 0 8-10 * * *" = 매일 8:00, 9:00, 10:00 에 실행
* "0 0/30 8-10 * * *" = 8:00, 8:30, 9:00, 9:30, 10:00, 10:30 에 실행
* "0 0 9-17 * * MON-FRI" = 월요일~금요일까지 9시:00 ~ 17:00 에 실행
* "0 0 0 25 12 ?" = 매년 12월 25일 정시에 실행

second, minute, hour, day of month, month, day(s) of week

(*) means match any

*/X means "every X"

? ("no specific value") 






https://stackoverflow.com/questions/26147044/spring-cron-expression-for-every-day-101am/37710207
