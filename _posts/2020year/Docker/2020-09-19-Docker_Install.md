---
layout: post
title: Docker 설치하기
author: JJW
categories: [Docker]
tags: [Docker]
image: assets/images/picture/2020/Docker/Docker.png
date: 2020-09-19 00:00:00
lastmod: 2020-09-19 00:00:00
sitemap:
  changefreq: daily
  priority: 1.0
beforetoc:
featured:
rating:
hidden:
toc: true
---

Docker 설치하기

# Docker

`Docker`란 한마디로 말하면 `컨테이너 기반의 가상화 플랫폼`이다.

이 말이 이해가 잘 안되는데 아래의 그림을 보면 이해가 잘 될 것이다.

<img class="blogPict" src="/assets/images/picture/2020/Docker/Docker_1.png">

왼쪽이 `Docker`를 사용할 때이고 오른쪽이 `VM`을 사용했을 때 이다.

`Docker`를 사용했을 때는 `Docker`가 위에 컨테이너들을 관리해주지만, `VM`을 사용햇을때는 OS위에 OS를 다시 설치하는 구조로 되어있다.

이렇게 `VM`은 운영체제위에 운영체제를 설치하다보니 느려질 수 밖에없고 그에비해 `Docker`는 빠르게 실행이 가능하다.

## Docker 사용 이유

나는 아직 학부생이라 잘은 모르겠지만 사용하면서 편하다고 느낀점만 소개해보겠다.

1. 시스템 배포시 동일한 환경 유지 가능
   > 엄청 큰 장점인 것 같다.
   > 딥러닝을 할 때 `Anaconda`를 이용해서 모듈들의 버전을 맞춰서 진행하는 것 처럼,
   > `Docker`를 이용하여 본인이 개발해서 성공적으로 실행시킨 환경을 그대로 배포한다면
   > 실패할 일이 없기 때문이다.
2. `Dockerfile`, `Docker Hub`을 통한 배포
   > `Docker`는 `Dockerfile`, `Docker Hub`를 통해 `Docker image`를 배포하여 사용자에게 동등한 환경을 배포할 수 있다.
   > 이는 어떤 서비스를 완성했을 때 `Dockerfile`을 작성만 잘 해놓는다면, 사용자는 단지 `Dockerfile`을 다운받아 `Docker image`로 만들어 컨테이너로 바로 실행할 수 있다.
   > 또한, `Github`과 비슷한 `Docker Hub`에 `Docker image`를 업로드를 해놓는다면, 사용자가 원할 때 다운받아 바로 컨테이너로 실행시킬 수 있다.

## Dokcer 설치방법

### Linux에서 설치 방법

Linux에서는 아래의 명렁어를 통해 쉽게 설치할 수 있다.

```sh
curl -fsSL https://get.docker.com/ | sudo sh
```

명령어를 입력하면 아래와 같이 뜨면서 설치가 진행된다.

```sh
# Executing docker install script, commit: 26ff363bcf3b3f5a00498ac43694bf1c7d9ce16c
+ sh -c apt-get update -qq >/dev/null
+ sh -c DEBIAN_FRONTEND=noninteractive apt-get install -y -qq apt-transport-https ca-certificates curl >/dev/null
+ sh -c curl -fsSL "https://download.docker.com/linux/ubuntu/gpg" | apt-key add -qq - >/dev/null
Warning: apt-key output should not be parsed (stdout is not a terminal)
+ sh -c echo "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" > /etc/apt/sources.list.d/docker.list
+ sh -c apt-get update -qq >/dev/null
+ [ -n  ]
+ sh -c apt-get install -y -qq --no-install-recommends docker-ce >/dev/null
+ sh -c docker version
Client: Docker Engine - Community
 Version:           19.03.13
 API version:       1.40
 Go version:        go1.13.15
 Git commit:        4484c46d9d
 Built:             Wed Sep 16 17:02:52 2020
 OS/Arch:           linux/amd64
 Experimental:      false
...

```

이후 설치가 끝났으면 아래의 명령어로 확인을 한다.

```sh
docker --version
```

아래와 같이 버전이 나온다면 설치가 성공한 것이다.

```sh
Docker version 19.03.13, build 4484c46d9d
```

### Window혹은 Mac에서 설치하는 방법

Window혹은 Mac에서 설치할 때는 공식 홈페이지에 있는 `Docker Desktop`을 설치하면 된다.

[Mac용 Docker Desktop 설치하기](https://docs.docker.com/docker-for-mac/install/)
[Window용 Docker Desktop 설치하기](https://docs.docker.com/docker-for-windows/install/)
