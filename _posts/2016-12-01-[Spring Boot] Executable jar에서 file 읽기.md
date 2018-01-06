---
layout: post
title: "[Spring Boot] Executable jar에서 file 읽기"
categories: [Spring Boot]
tags: [spring boot]
description: Executable jar에서 resource에 추가한 file 읽어오기
---
<!-- 
Executable jar에서 file 읽기
=====
 -->
Spring Boot에서 추가한 파일을 읽어오는 방법


# 소스
```
	    try {
	    	
	        CsvSchema bootstrapSchema = CsvSchema.emptySchema().withHeader();
	        CsvMapper mapper = new CsvMapper();
	        ClassPathResource resource = new ClassPathResource( fileName );
	        InputStream in = resource.getInputStream();
	        
	        MappingIterator<T> readValues = mapper.readerFor(type).with(bootstrapSchema).readValues(in);
	        
	        return readValues.readAll();
	        
	    } catch (Exception e) {	    	
	        log.error("Error occurred while loading file " + fileName, e);
	        return Collections.emptyList();
	        
	    }
	    
	}
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

