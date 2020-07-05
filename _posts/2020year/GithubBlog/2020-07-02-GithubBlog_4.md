---
layout: post
title: GitHub으로 나만의 블로그 만들기 4 - 원하는 Syntax Highlighter 적용하기
author: JJW
categories: [Github, Jekyll]
tags: [Blog, Jekyll, Syntax Highlighter]
image: assets/images/picture/GithubBlog/SyntaxHL_1.png
date: 2020-07-02 01:00:00
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

내 Blog의 Syntax Highlighter 변경하기

지난 글에서는 local에서 변경사항을 실시간으로 보면서 수정하기 위해 jekyll bundler를 이용해보았다.
이번에는 내 블로그에 적용되는 `syntax highlighter`를 변경해보도록 하자.

# Syntax Highter

Jekyll themes를 이용해 블로그를 만들었으면 아마 대부분 기본 Syntax Highlighter가 들어있을 것이다.

나의 테마는 [`Mediumish`](https://jekyllthemes.io/theme/mediumish)인데 기본 Syntax Highlighter가 아래와 같이 배경이 하얀색이고 코드 표시가 색으로 안나타서 코드를 표시해도 보기 힘들었다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/SyntaxHL_2.png">

그래서 Syntax Highlighter를 변경하기로 하였다.

## Rouge

`Rouge`는 pure Ruby syntax highlighter로 100개 이상의 언어들을 지원합니다.

### rouge 설치

`Rouge`를 설치하기 위해서 아래의 명령어를 입력해줍니다.

```sh
gem install rouge
```

설치가 되었다면 아래와 같이 나옵니다.

```sh
gem install rouge
Successfully installed rouge-3.20.0
Parsing documentation for rouge-3.20.0
Done installing documentation for rouge after 3 seconds
1 gem installed
```

### 원하는 테마 선택

rouge는 여러가지 스타일을 가지고 있습니다.

이중 하나를 선택하기전에 어떤 스타일이 있는지 확인해봅시다.

```sh
rougify help style
```

명령어를 치면 아래와 같이 나오는데 젤 아래 부분에 `available themes`이 사용할 수 있는 테마들 입니다.

```sh
usage: rougify style [<theme-name>] [<options>]

Print CSS styles for the given theme.  Extra options are
passed to the theme. To select a mode (light/dark) for the
theme, append '.light' or '.dark' to the <theme-name>
respectively. Theme defaults to thankful_eyes.

options:
  --scope     	(default: .highlight) a css selector to scope by
  --tex       	(default: false) render as TeX
  --tex-prefix	(default: RG) a command prefix for TeX
              	implies --tex if specified

available themes:
  base16, base16.dark, base16.light, base16.monokai, base16.monokai.dark, base16.monokai.light, base16.solarized, base16.solarized.dark, base16.solarized.light, bw, colorful, github, gruvbox, gruvbox.dark, gruvbox.light, igorpro, magritte, molokai, monokai, monokai.sublime, pastie, thankful_eyes, tulip
```

저는 이중에서 `monokai.sublime`을 선택했습니다.

### 선택한 테마 생성

이후 선택한 테마를 `.css` 파일로 생성해야 합니다.

아래의 명령어를 입력해줍니다.

```sh
cd '블로그 폴더 경로'
rougify style '선택한 테마'
ex) rougify style monokai.sublime
```

그러면 `style.css`라는 파일이 생성된 것을 볼 수 있습니다.

여기서 부터는 두가지 경우가 있는데 자신이 판단하여 자신에게 맞는 것을 따라하셔야 합니다.

#### Syntax Highlighter를 새로 등록

대부분 이 방법으로 해결이 되는데 Syntax Highlighter가 없어서 아예 새로 만들고 등록하는 방법입니다.

`jekyll theme`를 사용했으면 `assets/css`라는 폴더가 있는데 아까만든 `style.css`파일을 옮겨줍니다.

그 후 이 css파일을 html파일에 등록해주어야 하는데 `_layouts`폴더에 있는 `default.html`에 등록해주면 됩니다.

`_layouts/default.html`파일을 열어보시면 아래와 같이 css가 등록된 부분이 있습니다.

```css
    <link href="{{ site.baseurl }}/assets/css/screen.css" rel="stylesheet" />
```

이 부분을 찾아서 아래와 같이 추가해줍니다.

```css
    <link href="{{ site.baseurl }}/assets/css/screen.css" rel="stylesheet" />
    <link href="{{ site.baseurl }}/assets/css/syntax.css" rel="stylesheet" />
```

##### 요약

1. `style.css`파일을 `assets/css`폴더로 옮기기
1. `_layouts/default.html`파일에 `style.css` 등록

### Syntax Highlighter를 변경

이 경우는 Syntax Highlighter가 이미 있거나 사용하는 테마가 다른 파일로부터 Highlighter를 가져오는 경우입니다.

제 테마인 `Mediumish`은 기본 Syntax Highlighter가 내장되어 있고 그 파일은 `_sass/_syntax.scss`에 있습니다.

이 파일 내용을 아까 만든 `syntax.css`안에 내용으로 교체해주면 됩니다.

##### 요약

1. 적용되어 있는 Syntax Highlither 파일 찾기
1. 안에 내용을 아까 만든 `style.css`로 바꾸기

## \_config.yml 수정

이제 마지막 단계로 `_config.yml`파일을 수정해야 합니다.

`_config.yml`파일에 아래 내용을 추가해줍니다.

```sh
markdown: kramdown
kramdown:
  input: GFM
  syntax_highlighter: rouge
```

그럼 아래와 같이 적용된 것을 볼 수 있습니다.

<img class="blogPict" src="/assets/images/picture/GithubBlog/SyntaxHL_3.png">

# Reference

[Rouge-Ruby Github](https://github.com/rouge-ruby/rouge)

[Github Blog 1 - 블로그 생성을 위한 repository 생성](../GithubBlog_1)  
[Github Blog 2 - Jekyll themes를 이용해 블로그 페이지 꾸미기](../GithubBlog_2)  
[GitHub Blog 3 - jekyll bundler를 이용하여 블로그 수정하기](../GithubBlog_3)
