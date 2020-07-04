---
layout: post
title: GitHub으로 나만의 블로그 만들기 3 - jekyll bundler를 이용하여 블로그 수정하기
author: JJW
categories: [Github]
tags: [Blog, jekyll]
image: assets/images/picture/GithubBlog/Githubblog_2.png
date: 2020-07-02 12:00:00
lastmod: 2020-07-02 12:00:00
sitemap:
  changefreq: daily
  priority: 1.0
beforetoc:
featured:
rating:
hidden:
toc: true
---

jekyll bundler를 통해 블로그 수정하기

지난 글에서는 jekyll theme를 다운로드하여 적용해봤다.  
이번에는 local에서 변경사항을 실시간으로 보면서 수정하기 위해 jekyll bundler를 이용해보자.

# Jekyll

## jekyll bundler 설치

우선 실시간으로 페이지가 수정되는 것을 보려면 jekyll bundler가 필요하다.  
아래의 명령어를 통해 `jekyll bundler`를 설치한다.

```sh
gem install jekyll bundler
```

## jekyll bundler 실행

bundler설치가 끝났다면 local에서 웹페이지를 실행시켜보자.

```sh
cd (블로그 repository)
bundle exec jekyll serve --watch
```

해당 명령어를 실행하면 terminal에 아래와 같이 나오게 된다.

```sh
Configuration file: /Users//Desktop/Code/azzyjk.github.io/_config.yml
            Source: /Users//Desktop/Code/azzyjk.github.io
       Destination: /Users//Desktop/Code/azzyjk.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
       Jekyll Feed: Generating feed for posts
                    done in 0.649 seconds.
 Auto-regeneration: enabled for '/Users//Desktop/Code/azzyjk.github.io'
    Server address: http://127.0.0.1:4000/mediumish-theme-jekyll/
  Server running... press ctrl-c to stop.
```

## local에서 웹페이지 열기

이후 브라우저를 열어 `localhost:4000` 또는 `127.0.0.1:4000`을 입력해준다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Githubblog_2.png">

해당 페이지가 잘 뜨는것을 볼 수 있다.  
이제 실시간으로 local에서 페이지를 수정하여 새로고침하여 보고 수정이 완료되었을 때 Github에 commit해주면 된다.

[Github으로 나만의 블로그 만들기 - 1](../GithubBlog_1)  
[Github으로 나만의 블로그 만들기 - 2](../GithubBlog_2)
