---
layout: post
title: GitHub으로 나만의 블로그 만들기 8 - Hits를 이용해 내 글의 조회수 표시하기
author: JJW
categories: [Github]
tags: [Blog, Jekyll, Hits]
image: assets/images/picture/GithubBlog/Hits_1.png
date: 2020-07-06 01:33:00
lastmod: 2020-07-06 01:40:00
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

Hits를 이용하여 내 글의 조회수를 표시하기

지난 글에서는 Google Analytics를 이용해 블로그 방문자 수를 확인했었다.  
이번에는 블로그에 `Hits`를 이용해 내 게시글의 조회수를 보도록 하자.

# Hits!

Jekyll로 블로그를 만들면 자체적인 백엔드가 없어 방문자 수와 조회 수 가 뜨지 않는다.

Google Analytics를 이용하면 블로그의 방문자 수는 볼 수 있지만 이 게시글을 몇명이 봤는지 다른 사용자들에게 표시할 수는 없다.

이때 Github Repository 방문자 수를 세기 위해 만들어진 [`Hits!`](http://hits.dwyl.io/)를 이용하여 조회수를 표시해보자.

## Hits!의 기본 사용법

`Hits!`의 사용법은 `.md`파일에 아래의 같이 코드를 추가해주면 됩니다.

```markdown
![HitCount](http://hits.dwyl.com/{username}/{project}.svg)
ex)
![HitCount](http://hits.dwyl.com/azzyjk/Test.svg)]
```

## 자동 생성을 위한 설정

위와 같이 코드를 매 글마다 입력하면 쉽게 사용할 수 있지만 그러기엔 귀찮기도 하고 오타가 날 수도 있다.

그러므로 레이아웃에 잇는 코드를 수정하여 글마다 자동으로 `Hits!` 배지가 생기도록 해보자.

게시글을 적을때 먼저 이런식으로 `layout:post`와 같이 선언을 했을 것이다.

```markdown
---
layout:post
---
```

이는 `_layout`폴더에 있는 `post.html`를 레이아웃으로 사용하겠다는 얘기이다.

그러므로 우리는 `_layout/post.html`을 수정해주면 게시글에 배지가 생기도록 할 수 있다.

먼저 게시글의 제목아래 추가하기 위해서 `post.html`에서 게시글의 시작부분을 찾아준다.

내가 사용하는 테마 경우에는 아래와 같이 주석으로 게시글 시작부분을 알려주어서 쉽게 제목 아래부분을 찾을 수 있었다.

```markdown
<!-- Post Content -->
```

만약 주석표시가 안되어있으면 F12를 눌러 `Chrome Dev Tools`을 통해 찾아주거나 직접 찾아준다.

이후 아래의 코드를 추가해줍니다.

```html
{% raw %}
<div style="text-align: center;">
  <a href="http://hits.dwyl.com/{{ site.url | remove_first: 'https://' | remove_first: 'http://' }}{{ page.url }}" target="_blank">
    <img src="http://hits.dwyl.com/{{ site.url | remove_first: 'https://' | remove_first: 'http://' }}{{ page.url }}.svg"/>
  </a>
</div>
{% endraw %}
```

그 후 확인해보면 `Hits!`배지가 생긴걸 확인할 수 있다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Hits_1.png">
