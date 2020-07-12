---
layout: post
title: Github에 자신의 SSH Key 등록하기
author: JJW
categories: [SSH, Github]
tags: [Mac]
image: assets/images/picture/SSH/Github_2.png
date: 2020-07-11 19:22:00
lastmod: 2020-07-11 19:22:00
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

Github에 자신의 SSH Key를 등록해서 편하게 사용하기

# Github에 SSH Key 등록하기

`Github`에 자신의 `SSH Key`를 등록할 경우 터미널에서 `git`을 사용해 자신의 repository를 가져올 때나 커멋할 때 로그인을 하지 않고 이용할 수 있게 된다.

## 공개키 복사하기

Github에 공개키를 등록하기 전에 자신의 공개키를 먼저 복사해주도록 하자.

`SSH Key`가 없다면 아래의 사이트에서 생성하는 법을 보고 생성하자.  
[`SSH Key 생성하는 법(Mac OS)`](https://azzyjk.github.io/SSHKeyGen_Mac/)

아래의 명령어를 입력해 자신의 공개키를 출력해준 뒤 복사해준다.

```sh
cat ~/.ssh/id_rsa.pub
```

## Github 설정에서 등록

먼저 `Github`에 들어가 우측 상단에 자신의 아이콘을 누르고 `Setting`에 들어가준다.

<img class="blogPict" src="/assets/images/picture/SSH/Github_1.png">

`Setting`에 들어가면 좌측에 `SSH and GPG keys`라는 항목이 있는데 클릭해준다.  
그 후 `New SSH Key`를 눌러준다.

<img class="blogPict" src="/assets/images/picture/SSH/Github_2.png">

그럼 아래와 같이 Key를 추가하는 창이 나오게되는데 `Title`에는 프로젝트 이름이나 자신이 알아보기 쉬운 이름을 적고 `Key`에는 아까 복사한 `Key 값`을 넣어주면 된다.

<img class="blogPict" src="/assets/images/picture/SSH/Github_3.png">

## Repository clone 해보기

이제 `Github`에 키를 등록했으면 repository를 `clone`하여 테스트해보자.

먼저 `Github`에 들어가 `clone`하기 원하는 repository로 들어가주자.

그럼 우측에 `Clone or download`라는 버튼이 있는데 클릭하면 `Clone with HTTPS`라고 되어있고 사이트 주소가 나와잇을 것이다.

우측에 Use SSH를 눌러 `Clone with SSH`로 변경 해준뒤 해당 주소를 복사해준다.

<img class="blogPict" src="/assets/images/picture/SSH/Github_4.png">

이제 터미널로 돌아가 아래의 코드를 입력해준다.

```sh
git clone '복사한 주소'
ex) git clone git@github.com:azzyjk/COVID.git
```

그 다음 폴더를 확인해보면 해당 파일이 `clone`된 것을 확인할 수 있다.

<img class="blogPict" src="/assets/images/picture/SSH/GithubClone_1.png">
