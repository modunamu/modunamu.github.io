---
layout: post
title: "[gitlab] issue-git-merge"
categories: [git]
tags: [gitlab, merge]
description: 
---


## gitlab에서 issue 만든 후 'new branch' 생성 하여 issue 연동

## mac 에서 branch 체크 아웃
```
$ git pull origin 6-0-amt
From gitlab.com:modunamu/test
 * branch            6-0-amt    -> FETCH_HEAD
 * [new branch]      6-0-amt    -> origin/6-0-amt
Already up-to-date.

$ git checkout 6-0-amt
Branch 6-0-amt set up to track remote branch 6-0-amt from origin.
Switched to a new branch '6-0-amt'
```

## 개발 및 테스트 후 커밋
```
$ git push origin 6-0-amt
Counting objects: 11, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (9/9), done.
Writing objects: 100% (11/11), 845 bytes | 0 bytes/s, done.
Total 11 (delta 6), reused 0 (delta 0)

remote:
remote: Create merge request for 6-0-amt:
remote:
To git@gitlab.com:modunamu/test.git
   794764c..b6c748a  6-0-amt -> 6-0-amt
```

## gitlab 에서 compare 후 'create merge request'

## local 에서 개발 branch 삭제
```
$ git pull
$ git checkout master
$ git merge 6-0-amt
$ git branch -d 6-0-amt

```

[현재 브랜치 보기]
```
$ git branch
* master
```

[원격 브랜치 보기]
```
$ git branch -r
  origin/master
```

[모든 브랜치 보기]
```
$ git branch -a
* master
  remotes/origin/master
```

[브랜치 체크 아웃]
```
$ git checkout -t origin/7b0c0464
Branch 7b0c0464 set up to track remote branch 7b0c0464 from origin.
Switched to a new branch '7b0c0464'

$ git branch -a
* 7b0c0464
  master
  remotes/origin/7b0c0464
  remotes/origin/master
```

[branch push]
```
$ git push origin 7b0c0464

```

[branch master로 변경]
```
$ git checkout master
```

[branch 삭제]
```
$ git branch -d 7b0c0464
```





* https://blog.outsider.ne.kr/641
* https://git-scm.com/book/ko/v1/Git-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EB%B8%8C%EB%9E%9C%EC%B9%98%EC%99%80-Merge%EC%9D%98-%EA%B8%B0%EC%B4%88
