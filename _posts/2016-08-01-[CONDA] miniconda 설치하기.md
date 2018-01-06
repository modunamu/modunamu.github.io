---
layout: post
title: "[CONDA] Mac에서 miniconda 설치하기"
categories: [CONDA]
tags: [conda]
description: miniconda를 설치하고 가상환경을 만들어 봅니다.
---
<!-- 
Mac에서 miniconda 설치하기
=====
 -->

Conda는 설치한 패키지의 의존성을 관리해 주는 툴로 데이터사이언스에서 자주 사용하는 numpy, pandas, scipy 등이 미리 설치되어 있습니다. Mac에서 사용하는 방법을 간단히 설명 합니다. miniconda는 Conda의 최소 설치버젼으로 Conda에 비해서 가벼워 자주 사용합니다.

# 설치하기

## 다운로드
미니콘다 홈페이지(https://conda.io/miniconda.html)에서 필요한 버젼으로 다운 받습니다.

## 설치
파일은 다운로드한 폴드에서 쉘을 실행하여 설치합니다.
```
bash Miniconda3-latest-MacOSX-x86_64.sh
```

## 경로 설정
bash 쉘을 사용하는 경우는 conda 설치 경로가 자동으로 추가되지만, 요즘 자주 사용하는 zsh를 사용하는 경우는 직접 추가 해야 합니다.

vi를 실행하여 다음과 같이 추가 합니다.
```
$ vi ~/.zshrc
export PATH=$HOME/miniconda3/bin:$PATH
```

경로 추가 후 'source ~/.zshrc'로 쉘에 추가한 설정을 반영 합니다.

# 가상환경 사용하기

## 가상 환경 만들기
conda create 로 가상환경을 만들며 --name으로 환경 이름을 지정합니다.
```
$ conda create --name testEnv
```

## 환경 실행
```
$ source activate testEnv
(testEnv) $
```

## 가상 환경 종료
```
$ source deactivate
```

## 가상 환경 삭제
```
$ conda env list
$ conda env remove -n tf
```
