---
layout: post
title: "[MAC] telnet 설치하기"
categories: [mac]
tags: [mac, telnet]
description: Mac에서 homebrew로 telnet 설치하고 간단히 사용하는 방법을 알아 봅니다.
---
<!-- 
Mac에서 homebrew로 telnet 설치하기
=====
 -->

homebrew로 간단히 telnet 설치하고 사용하는 방법을 알아 봅니다.

## 설치하기
```
$ brew install telnet

```

## 설치되 telnet 정보 확인
```
$ brew info redis
Updating Homebrew...
==> Auto-updated Homebrew!
Updated 1 tap (homebrew/core).
==> Updated Formulae
amqp-cpp                 fn                       kubernetes-cli           libbitcoin-server        mypy                     translate-shell
boost                    fwup                     libbitcoin               librealsense             ocaml-num                urh
boost-mpi                global                   libbitcoin-blockchain    librsvg                  open-mpi                 weboob
boost-python             glog                     libbitcoin-database      libxkbcommon             pegtl                    ykman
coq                      imagemagick              libbitcoin-explorer      linkerd                  pgpool-ii
couchdb                  imagemagick@6            libbitcoin-node          mapnik                   svgcleaner

==> Downloading https://homebrew.bintray.com/bottles/telnet-54.50.1.high_sierra.bottle.tar.gz
######################################################################## 100.0%
==> Pouring telnet-54.50.1.high_sierra.bottle.tar.gz
🍺  /usr/local/Cellar/telnet/54.50.1: 4 files, 245.9KB
```

## 원격 접속
사용방법은 telnet 접속IP/도메인 접속포트
```
$ telnet thinkwave.synology.me 22 
```

