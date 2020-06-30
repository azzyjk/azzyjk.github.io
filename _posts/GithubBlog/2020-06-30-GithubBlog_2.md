---
layout: post
title: GitHub으로 나만의 블로그 만들기 - 2
author: JJW
categories: [Github]
tags: [Blog, jekyll]
image: images/picture/GithubBlog/Jekyll_1.png
beforetoc: 원하는 Jekyll Themes 다운로드하여 나만의 블로그 페이지 만들기
toc: true
---

# Jekyll

## Jekyll themes 다운

Github blog를 만들때 나는 Jekyll에서 이미 만들어진 테마를 이용하기로 하였다.  
이렇게하면 시간도 단축되고 보기도 이쁘다.  
[Jekyll 테마 다운로드](http://jekyllthemes.org/)

<img class="blogPict" src="/images/picture/GithubBlog/Jekyll_1.png">

해당 사이트에 들어가면 여러 테마들이 있는데 그 중 원하는 테마를 다운받으면 된다.  
나는 젤 앞에 보이는 `Memoirs Jekyll Theme`를 사용하였다.

<img class="blogPict" src="/images/picture/GithubBlog/Jekyll_2.png">

원하는 테마를 클릭 후 Download 해준다.

Download 후 압축을 풀면 아래와 같이 여러 파일들이 나오는데 이를 전에 clone해준 폴더에 넣어주면 된다.

<img class="blogPict" src="/images/picture/GithubBlog/Jekyll_3.png">

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

이후 해당 파일들을 Github 올려주기 위해 git으로 올려준다.

```javascript

cd 해당 폴더
git commit

```

```c
#include<stdio.h>

int main(){
    return 0;
}
```
