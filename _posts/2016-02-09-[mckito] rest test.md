---
layout: post
title: "[mockito] rest test"
categories: [mockito]
tags: [mockhito, junit, test, spring boot, rest]
description: 
---

## pom.xml
```
<dependency>
    <groupId>org.hamcrest</groupId>
    <artifactId>hamcrest-library</artifactId>
    <version>1.3</version>
    <scope>test</scope>
</dependency>

<dependency>
    <groupId>com.jayway.jsonpath</groupId>
    <artifactId>json-path</artifactId>
    <version>0.9.1</version>
    <scope>test</scope>
</dependency>
```

## NameRestControllerTest.java
```
import static org.hamcrest.Matchers.containsString;
import static org.mockito.Mockito.when;
import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.post;
import static org.springframework.test.web.servlet.result.MockMvcResultHandlers.print;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.status;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.jsonPath;

import org.junit.Before;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.mockito.InjectMocks;
import org.mockito.Mock;
import org.mockito.MockitoAnnotations;
import org.mockito.runners.MockitoJUnitRunner;
import org.springframework.http.MediaType;
import org.springframework.test.web.servlet.MockMvc;
import org.springframework.test.web.servlet.setup.MockMvcBuilders;
import org.springframework.web.util.UriComponentsBuilder;


import com.fasterxml.jackson.databind.ObjectMapper;
import com.apiservice.WithdrawMasterApiService;
import com.service.MsgService;
import com.si.TcpSendGateway;
import com.web.MsgDto;

@RunWith(MockitoJUnitRunner.class)
public class NameRestControllerTest {

	@Mock
	MsgService msgService;

	@Mock
	TcpSendGateway tcpSendGateway;

	@Mock
	WithdrawMasterApiService withdrawMasterApiService;

	@InjectMocks
	NameRestController nameRestController;

	MockMvc mockMvc;

	MsgDto msgDto;
	MsgDto rMsgDto;

	UriComponentsBuilder uriBuilder;

	@Before
	public void test() {
		MockitoAnnotations.initMocks(this);
		mockMvc = MockMvcBuilders.standaloneSetup(nameRestController).build();

		msgDto = new MsgDto();
		msgDto.setMsg("fdfdfdfdfdf");

		rMsgDto = new MsgDto();
		rMsgDto.setMsg("GOOD_NAME");
	}

	@Test
	public void testControllerEmptyBody() throws Exception {
		when(withdrawMasterApiService.processName(sendMsgDto)).thenReturn(recvMsgDto);

		mockMvc.perform(post("/api/name/secure")
						.content(new ObjectMapper().writeValueAsString(sendMsgDto))
						.contentType(MediaType.APPLICATION_JSON))
				.andExpect(status().isOk())
				.andDo(print())
				.andExpect(jsonPath("$.msg", containsString("GOOD_NAME")))				
				//.andReturn()
		;

	}
}
```