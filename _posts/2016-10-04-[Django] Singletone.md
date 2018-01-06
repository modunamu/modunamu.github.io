---
layout: post
title: "[Django] Singleton으로 클래스 사용"
categories: [Django]
tags: [django]
description: Django에서 Singleton으로 클래스를 생성하고 사용하는 방법을 설명합니다.
---
<!-- 
Singleton으로 클래스 사용해 보자.
=====
 -->

class를 singleton으로 만들고 사용하는 방법을 설명합니다.
여러가지 다양한 방법이 있지만 metaclass로 만들어 사용합니다.

### SingletonType
SingletonType를 클래스로 생성합니다.
```
import os

class SingletonType(type):
    def __call__(cls, *args, **kwargs):
        try:
            return cls.__instance
        except AttributeError:
            cls.__instance = super(SingletonType, cls).__call__(*args, **kwargs)
            return cls.__instance
```

### 적용 방법
Singleton을 적용할 클래스를 만들고 metaclass를 추가합니다.
```
from weather import Weather

class WeatherCall(object):
    __metaclass__ = SingletonType
    _api = None

    def __init__(self):
        self._api = WeatherApi(token='xxxxxxxxxx')

    def get_api(self):
      return self._api
```

### 사용 방법
```
api = WeatherCall.__call__().get_api()
```

상세한 설명은 아래 블로그를 참고 하시면 됩니다.

### 참고
1. http://ourcstory.tistory.com/105