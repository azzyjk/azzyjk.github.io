---
layout: post
title: Github Fork한 Repository 최신 상태로 업데이트하기
author: JJW
categories: [Git, Github]
tags: [Fork]
image: assets/images/picture/2020/Github/Fork/Fork.png
date: 2020-09-18 00:00:00
lastmod: 2020-09-18 00:00:00
sitemap:
  changefreq: daily
  priority: 1.0
beforetoc:
featured:
rating:
hidden:
toc: true
---

Fork한 Repository 최신 상태로 업데이트하기

# Github Fork

`Fork`는 다른사람의 Repository를 자신의 저장소로 복사하는 것이다.

`Fork`하는 방법은 다음 게시글을 참고하자.
[Github 원하는 Repository Fork하는 방법](https://azzyjk.github.io/Github_Fork/)

`Github`에서 오픈소스에 기여하거나 타인이 올린 코드에서 오류를 수정하여 올려주는 등 여러가지 이유로 특정 Repository를 `Fork`해야할 때가 있다.

그런데 다른사람의 Repository를 자신의 저장소로 복사한 후에 그 사람의 Repository의 변화가 생기면 나중에 `Pull Request`를 보냈을 때 문제가 발생할 수 있다.

이를 방지하기 위해 `Fork`된 Repository를 최신상태로 유지하는 방법을 설명해보겠다.

## 저장소 Github주소 추가하기

먼저 내가 Fork해온 Repository가 저장된 경로로 이동하여 아래의 명령어를 입력해준다.

```sh
git remote -v
```

그러면 다음과 같이 본인의 github repository 주소가 나오게 된다.

```sh
origin	https://github.com/azzyjk/KOR_mood.git (fetch)
origin	https://github.com/azzyjk/KOR_mood.git (push)
```

여기에 아래의 명령어를 통해 원본 저장소의 주소를 추가해준다.

```sh
git remote add upstream "Fork해온 Repository의 주소"
ex) git remote add upstream https://github.com/LuterGS/KOR_mood.git
```

이후 다시 `git remote -v`를 했을 때 아래와 같이 추가가 되있으면 성공한 것이다.

```sh
origin	https://github.com/azzyjk/KOR_mood.git (fetch)
origin	https://github.com/azzyjk/KOR_mood.git (push)
upstream	https://github.com/LuterGS/KOR_mood.git (fetch)
upstream	https://github.com/LuterGS/KOR_mood.git (push)
```

## Repository 동기화 하기

다시 해당 Repository가 저장된 경로로 이동하여 아래의 명령어를 입력해준다.

```sh
git fetch upstream
```

만약 변경된 내용이 있으면 아래와 같이 나오게 된다.

```sh
Updating 8523688..70da8ef
Fast-forward
 Dockerfile                               |   9 +-
 NeuralNet.py => ML1/NeuralNet1.py        |  53 +++++++----
 best_model.h5 => ML1/best_model.h5       | Bin
 tokenizer.pickle => ML1/tokenizer.pickle | Bin
 ML2/NeuralNet2.py                        | 146 +++++++++++++++++++++++++++++++
 ML2/tokenizer.pickle                     | Bin 0 -> 106850 bytes
 ML2/variables.data-00000-of-00001        | Bin 0 -> 6361855 bytes
 ML2/variables.index                      | Bin 0 -> 3210 bytes
 main.py                                  |  38 ++++++++
 9 files changed, 223 insertions(+), 23 deletions(-)
 rename NeuralNet.py => ML1/NeuralNet1.py (78%)
 rename best_model.h5 => ML1/best_model.h5 (100%)
 rename tokenizer.pickle => ML1/tokenizer.pickle (100%)
 create mode 100644 ML2/NeuralNet2.py
 create mode 100644 ML2/tokenizer.pickle
 create mode 100644 ML2/variables.data-00000-of-00001
 create mode 100644 ML2/variables.index
 create mode 100644 main.py
```

위 명령어를 통해 원본 Repository에 master branch에 있는 내용들이 본인의 PC에 upstream/master로 복사가 된다.

아래와 같이 `Github Desktop`에서 확인할 수 있다.

<img class="blogPict" src="/assets/images/picture/2020/Github/Fork/GithubDesktop_1.png">

이후 master에 가져온 내용을 합치기 위해 먼저 master로 이동해준다.

```sh
git checkout master
```

그리고 아래의 명령어를 통해 `merge`해준다.

```sh
git merge upstream/master
```

이후 `git push`를 하면 나의 Repository에 원본 Repository의 변경된 사항이 적용된다.
