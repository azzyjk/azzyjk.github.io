---
layout: post
title: 맥에서 SSH Key 생성하는 법
author: JJW
categories: [SSH]
tags: [Mac, SSH-keygen]
image: assets/images/picture/SSH/SSHKeyGen_1.png
date: 2020-07-07 20:00:00
lastmod: 2020-07-07 20:40:00
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

Mac OS에서 SSH Key 생성하는 방법

# SSH Key

`SSH Key`는 `Secure Shell Key`의 줄임말로 서버에 접속할 때 비밀번호 대신 key를 제출하여 로그인 할 수 있게 해준다.

## SSH Key가 사용되는 경우

- `보통 비밀번호보다 높은 수준의 보안을 필요`할 때
- `로그인 없이 자동으로 서버에 접속`할 때

## SSH Key 생성

터미널에 `ssh-keygen`을 입력해줍니다.

그럼 아래와 같이 저장할 키 이름을 입력하라고 합니다.

```sh
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/'사용자이름'/.ssh/id_rsa):
```

만약 이름을 정해주지 않으면 `enter`를 눌러 넘어가면 되는데 이 경우 키의 이름은 위에보이는 `id_rsa`가 됩니다.

그럼 아래와 같이 키에 설정할 암호를 묻는데 설정하지 않으려면 `enter`로 넘어가면 됩니다.

```sh
Enter passphrase (empty for no passphrase):
```

위에 입력한 것과 같은 암호를 입력하면 됩니다.

```sh
Enter same passphrase again:
```

위 과정을 모두 완료하면 아래와 같은 문구가 나오게 됩니다.

```sh
Your identification has been saved in /Users/'사용자이름'/.ssh/id_rsa.
Your public key has been saved in /Users/'사용자이름'/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:SUyLwENnLC+db3laNJjh8DJTftlXjrVdAsa1Qg3y+d4
The key's randomart image is:
+---[RSA 3072]----+
|   oo.o . ..==.  |
|    ++o+o. =..o.+|
|     =.B++ o+ .*+|
|    . B.*.= .oo.o|
|     . =S+ . ..  |
|        + o  . . |
|       . +    . E|
|        .        |
|                 |
+----[SHA256]-----+
```

이제 `~/.ssh` 경로로 들어가 공개키와 개인키가 잘 생성되었는지 확인하면 됩니다.

```sh
cd ~/.ssh
ls
```

제대로 생성되었으면 아래와 같이 나오게 됩니다.

```sh
id_rsa      id_rsa.pub
```

또는 직접 폴더에 들어가서 확인을 해도 좋습니다.

<img class="blogPict" src="/assets/images/picture/SSH/SSHKeyGen_1.png">

만약 이름을 설정해 주었다면 위와 같이 설정한 이름으로 나오게 됩니다.

## 요약

1. 터미널에서 `ssh-keygen` 입력
1. 이름 입력 칸에서 `enter` 입력
1. passphrase 묻는 칸에서 `enter`입력
1. 다시 passphrase 묻는 칸에서 `enter`입력
