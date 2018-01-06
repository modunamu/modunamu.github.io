---
layout: post
title: "[python] python 객체를 파일로 저장하고 읽기"
categories: [python]
tags: [python, pickle]
description: python에서 객체를 통째로 파일로 저장하고 읽어 오자.
---
<!-- 
python 객체를 파일로 저장하고 읽기
=====
 -->

종종 대량의 데이터를 파이썬 객제로 만들고 파일로 저장할 필요가 있다.
이런 경우 유용한 패키지가 pickle이다.


## dump(파일로 저장)
byte로 저장하기 때문에 'b', 파일 writing하므로 'w'
```
import pickle
print("Save Data to pickle...")
with open("large-data.pickle", "wb") as f:    
    pickle.dump(dataset, f)
```


## load(파일에서 로딩)
byte로 파일을 읽기 때문에 'b', 읽기만 하므로 'r'
```
import pickle
print("Load Data from pickle...")
with open("large-data.pickle", "rb") as f:    
    dataset = pickle.load(f)
```


