---
layout: post
title: "[Django] Admin 화면 구성"
categories: [Django]
tags: [django, admin]
description: Model를 사용하여 간단히 관리자 화면을 만듭니다.
---
<!-- 
Django에서 Admin 화면 구성 하기
=====
 -->

Django의 장점 중 하나가 쉽게 Admin(관리자) 화면을 만들 수 있습니다.
Model을 상속 받아서 속성 몇개만 지정하는것 만으로도 사용할만한 관리자 화면이 구성됩니다.


# 기본(admin.py)
```
from django.contrib import admin
from .models import Order

class OrderAdmin(admin.ModelAdmin):
    model = Order
    # search_fields = ('ymd',)
    list_per_page = 60
    ordering = ('-timestamp', )
    list_filter = ('ymd', 'name',)
    list_display = ('ymd', 'name', \
                    'etc1', 'etc2', 'etc3', 'etc4', 'etc5')
    pass
```

### model = Order
관리자를 구성할 Model을 지정합니다.

### search_fields = ('ymd',)
검색을 활성화 할 필드를 지정합니다.

### list_per_page = 60
페이징 사이즈를 지정합니다. 60이면 60 row가 나옵니다.
전체 사이즈가 60 이하면 페이징이 생성되지 않습니다.

### ordering = ('-timestamp', )
데이터의 정렬 조건을 필드로 지정합니다. 필드명만 붙이면 오름차순이고 '-'를 붙이면 내림차순 입니다.

### list_filter = ('ymd', 'name')
필터 조건으로 사용할 필드를 정합니다.

### list_display = ('ymd', 'name', \
그리드에 보여줄 필드를 입력 합니다.

# 등록

```
admin.site.register(OrderBook, OrderBookAdmin)
```