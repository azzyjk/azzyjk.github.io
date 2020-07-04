---
layout: post
title: GitHub으로 나만의 블로그 만들기 1 - 블로그 생성을 위한 repository 생성
author: JJW
categories: [Github]
tags: [Blog, Jekyll]
image: assets/images/picture/GithubBlog/Githubblog_1.png
date: 2020-06-29 12:00:00
lastmod: 2020-06-29 12:00:00
sitemap:
  changefreq: daily
  priority: 1.0
beforetoc:
featured:
rating:
hidden:
toc: true
---

Github 블로그를 위한 repository 생성

# Blog를 만들게 된 계기

먼저 나는 개발한 것들을 Github에 올리면서 내가 개발하면서 얻은 지식들을 해당 repository에 README.md파일로 정리하고있었다.

하지만 그러다보니 같은 언어를 사용해도 "이건 나중에 보고싶은데?"하는 것들은 해당 repo를 찾아가야 했고 그럴바에 블로그를 만드는것이 낫지 않을까 라고 생각을 하게되었다.

# Github

## repository 생성

Github blog를 만들기전에 먼저 repository를 생성해주어야 한다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Github_1.png">

위와 같이 repository name을 `[본인의 id].github.io`로 해서 생성해주면 된다.

## repository clone

<img class="blogPict" src="/assets/images/picture/GithubBlog/Github_2.png">

그 다음 해당 repository로 들어가 clone 버튼을 누른 후 해당 사이트를 복사해 준다.

이후 Terminal 창에서 `git clone [복사한 주소]` 를 통해 해당 repository를 가져온다.

아래와 같이 폴더가 생긴걸 확인 할 수 있다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Github_3.png">

다음에서는 테마를 다운받고 Github에 올리는 것과 테스트하는법에 대해 적어보겠습니다.
