---
layout: post
title: GitHub으로 나만의 블로그 만들기 6 - Disqus를 이용하여 블로그에 댓글기능 추가하기
author: JJW
categories: [Github, Disqus]
tags: [Blog, Jekyll]
image: assets/images/picture/GithubBlog/Disqus_9.png
date: 2020-07-04 01:48:00
lastmod: 2020-07-06 00:40:00
sitemap:
  changefreq: daily
  priority: 1.0
beforetoc:
featured:
rating:
hidden:
comments: true
toc: true
---

Github blog에 disqus를 이용하여 댓글 기능 추가하기

지난 글 에서는 내 블로그가 Google에서 검색되도록 해보았다.  
이번에는 disqus를 이용하여 블로그에 댓글기능을 추가해보자.

**이 글은 Disqus를 지원하는 Jekyll theme를 기준으로 작성되었다.**  
**만약 Disqus를 지원하지 않아서 모두 추가해야 한다면 다른 글을 보는 것을 추천한다.**

# Disqus

`Disqus`는 페이스북, 트위터와 같은 SNS와 연동해서 댓글을 달 수 있게 해주는 소셜 댓글 서비스입니다.

이를 블로그에 적용시켜서 블로그에 댓글기능을 추가해봅시다.

## Disqus 회원가입

먼저 Disqus 회원가입이 필요합니다.

만약 이미 회원가입이 되어있다면 이 과정을 넘어가시면 됩니다.
[Disqus](https://disqus.com/)

## 사이트 추가

회원가입을 완료하면 계정이 생성되었다면서 무엇을 원하는지 클릭할 수 있는 창이 아래와 같이 나오게 됩니다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Disqus_1.png">

저희는 블로그에 댓글기능을 추가할 것이므로 아래 `I want to install Disqus on my site` 버튼을 눌러줍니다.

버튼을 누르면 아래와 같이 창이 나오게 되는데 여기서 `Website Name`과 `Category`정도만 설정해주고 Create Site를 눌러주면 된다.

여기서의 `Website Name`은 Disqus에서 관리하기 위한 이름이므로 알아보기 쉽게 원하는대로 적으면 된다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Disqus_2.png">

## 사이트 설정

이후 아래처럼 어떤 플랜을 이용할 것인지 물어보는 창이 나온다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Disqus_3.png">

우리는 페이지가 많지도 않고 간단하게 댓글 기능만 추가할 것이므로 젤 아래 `Basic`을 선택해준다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Disqus_4.png">

`Basic`을 선택하면 아래처럼 어떤 플랫폼을 사용하고 있는지 물어보는데 우리는 `Jekyll`을 사용중이므로 `Jekyll`을 선택해주도록 하자.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Disqus_5.png">

`Jekyll`을 선택하고 들어가면 간단한 설명이 나오는데 아래 `Configure`을 눌러 설정페이지로 넘어가준다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Disqus_6.png">

설정 페이지에가면 아래와 같은 창이 나오게 되는데 여기서 `Website URL`하나정도만 입력한 뒤 `Complete Setup`을 누르면 넘어가진다.

이때 주소 입력형식은 `https://`부터 입력을 해줘야 한다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Disqus_7.png">

설정이 완료되었다는 문구가 나오면 된다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Disqus_8.png">

이후 회원가입할 때 입력한 이메일로 가보면 인증 메일이 와있는데 해당 메일 인증까지하면 Disqus사이트에서 할 설정은 끝났다.

## \_config.yml 수정

`Mediumish`테마는 `_config.yml`에 들어가면 disqus라는 항목이 있는데 여기에 아까 입력한 웹사이트에 이름을 입력해주면 된다.

```sh
disqus: 'disqus에서 설정한 Website 이름'
```

댓글 기능이 활성화 된 것을 볼 수 있다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Disqus_9.png">

[Github Blog 1 - 블로그 생성을 위한 repository 생성](../GithubBlog_1)  
[Github Blog 2 - Jekyll themes를 이용해 블로그 페이지 꾸미기](../GithubBlog_2)  
[GitHub Blog 3 - jekyll bundler를 이용하여 블로그 수정하기](../GithubBlog_3)  
[GitHub Blog 4 - 원하는 Syntax Highlighter 적용하기](../GithubBlog_4)  
[GitHub Blog 5 - 구글에서 Github blog 보이도록 하기](../GithubBlog_5)
