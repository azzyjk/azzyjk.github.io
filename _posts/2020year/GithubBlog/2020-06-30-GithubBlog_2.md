---
layout: post
title: GitHub으로 나만의 블로그 만들기 2 - Jekyll themes를 이용해 블로그 페이지 꾸미기
author: JJW
categories: [Github, Jekyll]
tags: [Blog, Jekyll]
image: assets/images/picture/GithubBlog/Jekyll_1.png
date: 2020-06-30 12:00:00
lastmod: 2020-07-05 12:00:00
sitemap:
  changefreq: daily
  priority: 1.0
beforetoc:
featured:
rating:
hidden:
toc: true
---

원하는 Jekyll Themes를 다운로드하여 블로그 페이지 꾸미기

지난 글에서는 github에서 repository를 만들어 자신만의 페이지를 만들어 보았다.  
이번에는 jekyll theme를 이용해 해당 페이지를 이쁘게 꾸며보자.

# Ruby

Jekyll theme를 이용하기전에 먼저 Ruby가 설치 되어 있어야한다.

아래 주소로 들어가 루비를 설치해주자.  
[Ruby](https://rubygems.org/pages/download)

설치 후 터미널에서 `ruby --version`을 압룍햤을때 버전이 나오면 설치가 된 것이다.

# Jekyll

## Jekyll themes 다운

Github blog를 만들때 나는 Jekyll에서 이미 만들어진 테마를 이용하기로 하였다.  
이렇게하면 시간도 단축되고 보기도 이쁘다.  
[Jekyll 테마 다운로드](http://jekyllthemes.org/)

<img class="blogPict" src="/assets/images/picture/GithubBlog/Jekyll_1.png">

해당 사이트에 들어가면 여러 테마들이 있는데 그 중 원하는 테마를 다운받으면 된다.

나는 젤 앞에 보이는 ~~Memoirs Jekyll Theme~~를 사용하였다.

(현재 나의 테마는 [`Mediumish`](https://jekyllthemes.io/theme/mediumish)로 `Memoirs` 테마는 내가 원하는대로 syntax highlighter를 변경할 수 없는것으로 보여 변경했다.)

테마를 고를때 팀으로는 아래와 같이 Feature를 보면 어떤 기능이 지원되는지 나오는데 자신에게 필요한 기능이 모두 있는지 확인하고 하는 것을 추천한다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Jekyll_4.png">

원하는 테마를 클릭 후 Download 해준다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Jekyll_2.png">

## 폴더에 테마 옮기기

Download 후 압축을 풀면 아래와 같이 여러 파일들이 나오는데 이를 전에 clone해준 폴더에 넣어주면 된다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Jekyll_3.png">

## bundler 설치 및 실행

이 상태로 Github에 올리면 안되고 필요한 파일들을 다운받아 주어야 한다.  
먼저 아래 명령어을 통해 `bundler`를 설치해준다.

```sh
gem install bundler
```

이후 `bundle install`을 통해 필요한 파일들을 다운 받아주어야 한다.

```sh
cd '블로그 폴더 경로'
bundle install
```

위 명령어를 입력하면 Gemfile에 따라 필요한 파일들이 설치가 된다.

## config.yml 수정

이후 `_config.yml` 파일에서 `url`부분을 수정해준다.

```sh
url: 'https://해당 repository 이름' ex) 'https://azzyjk.github.io'
```

# Github

## .gitignore 생성하기

이후 해당 파일들을 Github으로 올리기 전에 올리지 않아도 되는 파일들을 `.gitignore`에 넣어주도록 한다.  
만약 `.gitignore`파일이 없다면 직접 만든후 안에 내용을 넣어주면 된다.

```sh
.DS_Store

# Jekyll 이 생성한 메타 데이터 무시
_site/
.sass-cache/
.jekyll-cache/
.jekyll-metadata

# Bundler 가 생성한 폴더 무시
.bundle/
vendor/bundle
```

## commit 하기

이후 해당 파일들을 Github 올려주기 위해 commit해준다.

```sh
git add ./
git commit -m "commit comment"
git push
```

이후 `azzyjk.github.io`와 같이 `해당 repository 이름`으로 접속하면 사이트가 뜨는 것을 볼 수 있다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/Githubblog_1.png">

[GitHub Blog 1 - 블로그 생성을 위한 repository 생성](../GithubBlog_1)
