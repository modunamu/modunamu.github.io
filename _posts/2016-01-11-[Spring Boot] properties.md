---
layout: post
title:  "2016-01-11-[Spring Boot] application.properties"
categories: [Spring Boot]
tags: [spring boot]
description: application.properties and Value Annotation
---

application.properties
---
```
vendercode=12345
```

Test.class
---
```
public class Test {
	private static final Logger log = LoggerFactory.getLogger(test.class);

	@Value("${vendercode}")
  private String venderCode;
  
  public void sendOpenMsg() {
    System.out.println(venderCode) 
  }
}  
```
