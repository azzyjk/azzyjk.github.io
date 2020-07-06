---
layout: post
title: GitHub으로 나만의 블로그 만들기 7 - Google Analytics를 이용해 방문자 수 보기
author: JJW
categories: [Github, Google Analytics]
tags: [Blog, Jekyll, Google]
image: assets/images/picture/GithubBlog/GA_5.png
date: 2020-07-05 00:00:00
lastmod: 2020-07-06 01:31:00
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

Google Analytics를 이용해 블로그 방문자 수 보기

지난 글에서는 Disqus를 이용해 블로그에 댓글 기능을 추가했었다.
이번에는 블로그에 `Google Analytics`를 이용해 내 블로그 방문자수를 보도록 하자.

**이 글은 Google analytics를 지원하는 Jekyll theme를 기준으로 작성되었다.**  
**만약 Google analytics를 지원하지 않아서 모두 추가해야 한다면 다른 글을 보는 것을 추천한다.**

# Google Analytics

`Google Analytics`는 구글에서 무료로 제공하고 있는 웹분석 서비스다.

`Google Analytics`는 다양한 기능들을 가지고 있는데 이 중 하나가 실시간으로 내 페이지에 접속되어 있는 사용자 수를 볼 수 있습니다.

## Google Analytics 계정 가입

`Google Analytics`를 사용하기위해서는 먼저 구글 애널리틱스에 가입해야 합니다.

[`Google Analytics`](https://analytics.google.com/analytics/web/?authuser=0#provision/SignUp/)에 접속하면 아래와 같은 화면이 나오는데 계정 이름을 원하는대로 적고 아래 다음을 눌러줍니다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/GA_1.png">

그럼 아래보이는 창이 나오게 되는데 우리는 블로그를 방문하는 사용자를 볼 것이므로 웹을 선택하고 다음을 눌러준다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/GA_2.png">

그 다음 화면에서는 웹사이트 이름, 웹사이트 URL, 업종 카테고리, 보고 시간대를 입력하는 칸이 나오는데 모두 입력해주면 된다.

`웹사이트 이름`은 `Google Analytics에서 표시될 이름`을 적어준다.  
`웹사이트 URL`은 `블로그의 URL`을 적어준다.  
`업종 카테고리`는 `블로그에 가장 적절한 카테고리`를 선택한다.  
`보고 시간대`는 `해당 사용자에게 맞는 시간대`을 선택한다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/GA_3.png">

이후 만들기 버튼을 누르면 아래와 같이 추적 ID가 보일 것이다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/GA_4.png">

## \_config.yml 수정

이제 추적 ID에 있는 코드를 `_config.yml`에 추가해주면 된다.

블로그 폴더의 루트 경로에 있는 `_config.yml`파일을 연 후 다음 코드를 찾아준다.

```sh
google_analytics: 'UA-XXXXXXXXX-1'
```

이렇게 적혀있는 부분을 찾아준 뒤 코드를 자신이 받은 추적 ID로 바꿔준다.

이후 다시 [`Google Analytics`](https://analytics.google.com/analytics/web/)사이트에 접속하면 정보가 보이는 것을 확인할 수 있다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/GA_5.png">
