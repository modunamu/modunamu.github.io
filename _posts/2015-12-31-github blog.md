---
layout: post
title: "[git] github으로 blog 하기"
categories: [git]
tags: [github, blog]
description: github으로 blog 하기 위해서 Jekyll 설치하는 방법을 간단히 설명 합니다.
comments: true
---

Github으로 블로그 하기.
=====
tistory에서 블로그를 하다가 github으로 옮기게 되었습니다. html 에디터 보다 mark up 방식이 간결하고 편해서 작성하기가 편합니다.
github을 사용하면 무료로 호스팅 가능하고 변경 이력까지 관리됩니다. 블로그 작성시 이미지나 동영상등을 많이 사용하지 않는다면 괜찮은 선택인거 같습니다.


## 준비하기
1. github 가입
블로그 호스팅을 [github](https://github.com)으로 하기 때문에 가입 필수 입니다.
가입 후 repository를 생성합니다. 생성시 Repository name은 '아이디.github.io'로 합니다.

2. ruby 설치하기
맥은 기본적으로 설치되어 있기 때문에 생략 합니다.
리눅스인 아래와 같이 설치합니다.
```
sudo apt-get install ruby-full
```


## 설치하기

1. Jekyll 설치
Jekyll은 Markdown 형식으로 작성된 문서를 html로 변환해 줍니다.
```
sudo gem install jekyll bundler
```

2. 테마 선택
심플한 테마여서 dbyll로 선택 했습니다.
```
git clone https://github.com/dbtek/dbyll.git myblog
```

3. install
클론한 디렉토리로 가서 필요한 파일을 설치합니다.
```
cd myblog
bundle install
```

4. 실행
아래와 같이 입력하여 블로그를 로컬호스트로 실행합니다.
```
bundle exec jekyll serve
```

## 블로깅 시작
[localhost](http://127.0.0.1:4000/)로 접속하여 확인합니다.
기본적으로 블로그 작성시 파일은 ./_posts 폴더에서 작성하며 파일이름은 yyyy-mm-dd_제목.md 로 시작하면 됩니다.


## 참고
* http://dbtek.github.io/dbyll/

