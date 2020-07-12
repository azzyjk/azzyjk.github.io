---
layout: post
title: Oracle Cloud Free Tier 이용하기
author: JJW
categories: [Cloud, Oracle]
tags: [Server]
image: assets/images/picture/Oracle/Oracle_2.png
date: 2020-07-11 09:10:00
lastmod: 2020-07-11 09:10:00
sitemap:
  changefreq: daily
  priority: 1.0
beforetoc:
featured:
rating:
comments: true
hidden:
toc: true
---

Oracle Cloud Free Tier 이용하기

# Oracle Cloud

`Oracle Cloud`란 Oracle에서 호스팅하여 이너넷을 통해 사용자에게 인프라를 제공해주는 서비스입니다.
같은 동종의 업계로는 `AWS`와 `Naver Cloud`등이 있습니다.

## Oracle Cloud Free Tier란

`Oracle Cloud Free Tier`란 크게 두가지로 나눌 수 있습니다.

- Oracle Cloud Free Trial
- Oracle Cloud Always Free

`Oracle Cloud Free Trial`은 Oracle Cloud 계정을 생성하면 30일 동안 300달라에 해당되는 클라우드 자원을 무료로 이용할 수 있는 서비스입니다.

`Oracle Cloud Always Free`는 특정 클라우드 서비스를 기간과 비용에 제약 없이 사용할 수 있는 서비스 입니다.

이 중 저희가 이용해볼 서비스는 `Oracle Cloud Always Free`로 서버를 생성해 놓은뒤 개발할때 이용하면 유용할 것입니다.

## Oracle Cloud 가입하기

`Oracle Cloud Free Tier`를 이용하기 위해 [Oracle Cloud](https://www.oracle.com/kr/cloud/free/)페이지에 접속 후 가입해줍니다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_16.png">

`무료로 시작하기`를 누른 후 가입을 진행해주시면 됩니다.

## VM 인스턴스 생성

회원가입을 한 뒤 `Oracle Cloud`에 로그인 해줍니다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_1.png">

그럼 위와 같은 화면이 나오게 되는데 `VM 인스턴스 생성` 탭으로 이동해준다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_2.png">

그럼 위와 같이 컴퓨트 인스턴스 생성이라는 창이 나오게 된다.

이곳에서 이름, 이미지 또는 운영체제, SSH 키를 추가하고 생성하면 된다.

이름은 자신이 알 수 있을 이름을 지어주면 된다.

이미지는 이미지 변경을 눌러주면 아래와 같이 나오게 된다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_3.png">

원하는 이미지를 클릭 후 아래 이미지 선택버튼을 눌러주면 된다.

나는 20년 7월 기준 가장 최신인 Ubuntu 20.04(LTS) 버전을 선택했다.

이 후 아래로 내려가면 다음과 같은 화면을 볼 수 있는데

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_4.png">

본인의 SSH키 즉 `id_rsa.pub` 파일을 추가해주거나 `cat ~/.ssh/id_rsa.pub`을 했을때 나온 문자를 붙여주면 된다.  
만약 SSH키가 없다면 아래의 글을 통해 생성해준다.

[SSH Key 생성하기(MAC os 기준)](https://azzyjk.github.io/SSHKeyGen_Mac/)

이후 생성을 눌렀을 때 아래와 같이 인스턴스 세부정보 화면이 나온다면 생성에 성공한 것이다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_5.png">

## 서버에 접속하기

인스턴스가 생성되었고 `실행 중`이라면 이제 서버에 접속할 수 있다.

서버에 접속하는 법을 알아보자

### 명령어를 통해 접속하기

이 화면에서 조금 기다리다 보면 아래와 같이 `프로비전 중`에서 `실행 중`으로 변경된다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_17.png">

`실행 중`일때 인스턴스 액세스 부분을 보면 `공용 IP 주소`와 `사용자 이름`이 나오게 된다.

이를 이용해 아래의 명령어를 터미널에 입력하여 접속한다.

```sh
ssh -i '사용자의 개인키' '사용자이름'@'공용 IP 주소'
ex) ssh -i ~/.ssh/id_rsa test@127.0.0.1
```

그럼 아마 처음 접속했으면 아래와 같이 나올 것이다.

```sh
ssh -i ~/.ssh/id_rsa '사용자이름'@'공용 IP 주소'
The authenticity of host ''공용 IP 주소' ('공용 IP 주소')' can't be established.
ECDSA key fingerprint is SHA256:-------------------------------------.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

여기서 `yes`를 입력하면 한번 접속이 끊기면서 아래의 알림이 나올 것이다.

```sh
Connection closed by '공용 IP 주소' port 22
```

다시한번 `ssh -i '사용자의 개인키' '사용자이름'@'공용 IP 주소'`를 입력해준다.  
그러면 아래와 같이 서버에 접속하는 것을 확인 할 수 있다.

<img class="blogPict" src="/assets/images/picture/Oracle/Server_1.png">

### 콘솔 접속 복사 이용하기

만약 위에 방법으로 접속이 안되었다면 사이트에 있는 `직렬 콘솔 접속 복사`를 이용하는 방법도 있다.

먼저 `컴퓨트` - `인스턴스`에 들어가보자.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_6.png">

그럼 아래와 같이 자신이 생성된 인스턴스들이 보인다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_18.png">

이중 접속을 원하는 인스턴스로 들어가준다.  
접속하여 좌측 하단을 보면 아래와 같이 `리소스` - `콘솔 접속`이 있는데 들어가준다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_7.png">

`콘솔 접속`에 들어가면 아래와 같이 `콘솔 접속 생성`이라는 버튼이 있는데 눌러준다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_8.png">

그럼 아래와 같은 창이 나오게 되는데 위에서 인스턴스를 생성할 때 넣어준 자신의 공개키 즉, `id_rsa.pub`를 넣은 후 `콘솔 접속 생성`을 눌러준다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_9.png">

이후 기다리면 아래와 같이 상태가 활성이 된다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_11.png">

이제 구획 부분에 있는 버튼을 눌러주면 아래와 같이 `Linux/Mac용 직렬 콘솔 접속 복사` 버튼이 있는데 클릭해준 후 터미널에 붙여 넣어준다.

<img class="blogPict" src="/assets/images/picture/Oracle/Oracle_10.png">

아래와 같이 서버에 접속 된 걸 확인할 수 있다.

<img class="blogPict" src="/assets/images/picture/Oracle/Server_1.png">
