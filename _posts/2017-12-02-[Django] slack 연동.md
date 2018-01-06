---
layout: post
title: "[Django] slack 연동"
categories: [Django]
tags: [django, slack]
description: Django에서 slack을 연동하는 방법 설명
---

<!-- 
Django 에서 Slack 연동
===== 
-->
Django에서 에러나 배치 잡 실행 후 결과를 slack으로 보낼 수 있습니다.
slacker를 사용하여 연동하는 방법을 간편히 살펴 봅니다.

<!-- more -->

## 설치
slacker는 파이썬 버젼의 slack api wrapper 함수로 api를 편리하게 사용할 수 있습니다.
pip로 slacker를 설치합니다.
```
pip install slacker==0.9.60
```

## slack에서 App을 만들고 권한을 부여합니다.

### 1. Create Slack App
App을 새로 만듭니다.
```
https://api.slack.com/
```

### 2. Bot User
Slack에서 사용할 Bot 생성합니다.
bot으로 메세지를 보내고 받을 수 있습니다.
```
Features > Bot Users
```

### 3. OAuth & Permissions
Bot에게 Slack API를 사용하기 위한 권한을 추가하고, Access Token을 발급 받습니다.
```
Features > OAuth & Permissions
```

## Django 및 파이썬에서 사용법
slack사이트에서 발급 받은 'Bot User OAuth Access Token'을 사용합니다.

### 환경변수 추가
토큰키는 OS 환경변수에 추가하여 사용 했습니다.
```
export SLACK_TOKEN=xoxb-02393847343-iV5jk0l59SydGLF1geTmm
```

### 예시
초보몽키님 설명 참고.
```
# -*- coding: utf-8 -*-

import os
from slacker import Slacker

slack = Slacker(os.environ.get('SLACK_TOKEN'))

def notify_get_order_book(title=None, message=None, channel='#reporting', username='err-bot', attachments=None):

    if attachments is None :
        attachments = [{
            "color": "#36a64f",
            "title": "{}".format(title),
            "title_link": "http://127.0.0.1:7000/error/list/",
            "fallback": "에러 알림",
            "text": "{}".format(message)
        }]

    slack.chat.post_message(channel=channel, username=username, attachments=attachments)
```



## 참고

1. 초보몽키님의 블로그(상세설명)
https://wayhome25.github.io/django/2017/09/03/django-slack-bot/

2. slacker
https://github.com/os/slacker

