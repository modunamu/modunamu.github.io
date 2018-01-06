---
layout: post
title: "[MAVEN] 외부 JAR 추가"
categories: [MAVEN]
tags: [maven, jar]
description: Maven의 pom.xml에 외부 jar를 추가 합니다.
---
<!-- 
pom.xml에서 외부 JAR를 추가 하는 방법
=====
 -->

개발을 하다 보면 maven의 repository에 등록되지 않은 라이브러리나 모듈 호환성을 위해서 따로 개발하는 경우가 있습니다. 이런 경우 jar 로 만들어 프로젝트에 추가 합니다. maven을 사용하는 경우는 maven의 명명 규칙에 맞게 폴더를 생성하면 됩니다.


# 모듈
```
  <groupId>com.modu.api.openweather</groupId>
  <artifactId>openweathermap-java-sdk</artifactId>
  <version>0.1.0</version>
  <packaging>jar</packaging>
```

### repository
외부 jar 파일을 repository로 등록합니다. url 태그로 로컬 디렉토리의 경로를 지정합니다.
```
	<repositories>
		<repository >
		    <id >openweathermap-java-sdk</id >
		    <name >api</name >
		    <url >file://${project.basedir}/lib</url >
		</repository >
	</repositories>
```

### 파일 경로
파일 경로는 maven의 프로젝트 경로에서 디렉토리를 만들어 줍니다. 파일 패스는 '프로젝트root'/groupId/artifactId/version/파일 로 작성해야 maven에서 인식합니다.
```
프로젝트root/lib/com.modu.api.openweather/openweathermap-java-sdk/0.1.0/openweathermap-java-sdk-0.1.0.jar
```

### dependency 추가
```
		<dependency>
		    <groupId>com.modu.api.openweather</groupId>
		    <artifactId>openweathermap-java-sdk</artifactId>
		    <version>0.1.0</version>
		</dependency>
```

