---
layout: post
title: Anaconda 가상환경에서 Tensorflow 실행하기
author: JJW
categories: [Anaconda, Tensorflow]
tags: [Python]
image: assets/images/picture/JupyterNotebook/Notebook_4.png
date: 2020-07-10 02:15:00
lastmod: 2020-07-10 02:15:00
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

Anaconda로 생성한 가상환경에서 Tensorflow 실행해보기

지난 글에서는 `Anaconda`로 생성한 가상환걍에서 `Tensorflow`를 설치해보았다.  
이번에는 설치한 `Tensorflow`를 실행시켜 보자

# Tensorflow 실행하기

## Anaconda 가상환경으로 변경하기

먼저 만들어져 있는 Anaconda 가상환경으로 변경을 해야한다.

만약 Anaconda 가상환경이 없다면 아래 글을 참조해 만들어 주자.  
[`Anaconda 설치 및 가상환경 만들기`](https://azzyjk.github.io/Anaconda_1/)

`(base)`에서 가상환경으로 변경해주기 위해 아래 코드를 입력해주자.

```sh
conda activate `가상환경 이름`
ex) conda activate pyenv37
```

## Jupyter notebook

`Jupyter notebook`은 `Python`, `Markdown`등 여러 언어를 통한 실행 환경을 지원한다.

우리는 `Tensorflow`를 위한 코드를 보기 편하게 작성하기 위해 `Jupyter notebook`을 설치하도록 하자.

### Jupyter notebook 설치

`Anaconda`로 만든 가상환경으로 변경된 상태에서 아래의 명령어를 입력해준다.

```sh
conda install jupyter notebook
```

그럼 설치를 진행할 것인지 묻는 알림이 아래와 같이 뜨는데 `enter`를 눌러 넘어가준다.

```sh
Proceed ([y]/n)?
```

기다리면 패키지들이 자동으로 설치가 되고 설치가 완료되면 아래의 알림이 나오게 된다.

```sh
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
```

### Jupyter notebook 실행

터미널에 다음과 같은 명령어를 입력해 `Jupyter notebook`을 실행시켜준다.

```sh
jupyter notebook
```

그럼 아래와 같이 `Jupyter notebook`이 실행된 창이 나오게 된다.

<img class="blogPict" src="/assets/images/picture/JupyterNotebook/Notebook_1.png">

이제 코드를 생성할 경로로 들어간 뒤 우측 상단에 있는 `New` - `Python 3`를 선택
해준다.

<img class="blogPict" src="/assets/images/picture/JupyterNotebook/Notebook_2.png">

그럼 아래와 같은 창이 열리게 되는데 이제 이곳에 코드를 입력해주면 된다.

<img class="blogPict" src="/assets/images/picture/JupyterNotebook/Notebook_3.png">

## Tensorflow 실행해보기

이제 `Jupyter notebook`까지 실행했으니 간단한 `Tensorflow`예제를 실행해봅시다.

아래의 코드를 입력해 `Tensorflow`를 import하여 `Hello, Tensorflow!`를 출력해봅시다.

```python
import tensorflow as tf
msg = tf.constant('Hello, TensorFlow!')
tf.print(msg)
```

그럼 "Hello, Tensorflow!"라고 출력되는 것을 확인할 수 있습니다.

<img class="blogPict" src="/assets/images/picture/JupyterNotebook/Notebook_4.png">

[Anaconda 1 - 설치 및 가상환경 만들기](../Anaconda_1)  
[Anaconda 2 - Tensorflow 설치하기](../Anaconda_2)
