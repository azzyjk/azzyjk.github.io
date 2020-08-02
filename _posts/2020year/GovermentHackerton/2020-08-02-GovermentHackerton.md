---
layout: post
title: 2020 제3회 정부혁신제안 끝장개발대회 후기
author: JJW
categories: [끝장개발대회]
tags: [Goverment, Dev]
image: assets/images/picture/GovermentHackerton/GovermentHackerton.jpg
date: 2020-08-02 19:00:00
lastmod: 2020-08-02 19:00:00
sitemap:
  changefreq: daily
  priority: 1.0
beforetoc: 2019년에 진행한 군 장병 오픈소스개발 캠프에 대한 후기
featured: false
toc: true
---

2020년에 진행한 제3회 정부혁신제안 끝장개발대회에 대한 후기

# 끝장개발대회

먼저 끝장개발대회는 이전까지는 해커톤이라는 이름으로 진행되었다가 우리말로 바꾼 대회라고 한다.

말그대로 해커톤처럼 특정 주제를 가지고 정해진 시간동안 개발을 하면 되는 것이다.

## 개발과정

우리팀의 주제는 `미세먼지 생활수칙 준수를 위한 홈 IoT` 였고 나는 미세먼지 생활수칙을 지키지 않았거나 미세먼지가 심할경우 알림을 보내는 어플개발을 담당했다.

처음에는 local push notification을 구현하고 이후에 백엔드 개발자로 부터 JSON 타입을 받아 현재 미세먼지의 상태, 창문이 열려있는지를 받아와 상황에 맞게 사용자에게 알림을 주는 방식으로 만들었다.

## 후기

일단 좋은 결과를 받지는 못했지만 React Native로 앱 개발을 하면서 많은 부족함을 느끼며 공부해야할 부분을 알게되었다.

처음엔 함수를 특정조건일 때 실행시키는 걸 Render 부분에 넣기, 특정 변수를 다른 함수에서 조정하는 등 실수가 많았던 것 같다.

이번 대회를 통해 내가 부족한 점을 더 알게 되었고 해당 부분을 공부해서 보완된 코드를 만들어 볼 예정이다.

## 팁

이 대회는 정말 프로토 타입을 원하는 대회이다.

말그대로 원하는 기능을 모두 구현할 필요가 없으며 그냥 보여주는 방식으로만 만들어도 된다.

[미세먼지 생활수칙 준수를 위한 홈 IoT](https://github.com/azzyjk/GovermentHackerton)
