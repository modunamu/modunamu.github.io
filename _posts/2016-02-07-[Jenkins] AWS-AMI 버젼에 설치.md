---
layout: post
title: "[Jenkins] AWS-AMI 버젼에 설치"
categories: [jenkins]
tags: [jenkins, aws, ami]
description: [jenkins AWS-AMI 버젼에 설치]
---

#[젠킨스를 AWS-AMI 버젼에 설치한 경우]
##1.리눅스 버젼 확인
```
$ cat /etc/*-release
```

##2.리파지토리 추가 / 키 등록
```
$ sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo
$ sudo rpm --import http://pkg.jenkins-ci.org/redhat/jenkins-ci.org.key
```

##3.설치
```
$ sudo yum install jenkins
```
##4.port 변경
```
$ cd /etc/sysconfig
$ sudo vi jenkins

JENKINS_PORT="8080" -> 7070
```

##5.타임존 변경
```
$ cd /etc/sysconfig
$ sudo vi jenkins
JENKINS_JAVA_OPTIONS="-Dorg.apache.commons.jelly.tags.fmt.timeZone=Asia/Seoul"
```

##6. 서비스 시작
```
$ service jenkins start
$ chkconfig jenkins on
$ service restart jenkins
```

##7. aws security group에 7070 등록
```
tcp 8080 anyware
```

##8.Unlock Jenkins
```
$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
* http://devopscube.com/install-configure-jenkins-2-0/

