---
layout: post
title: HTTP 컨텐츠 협상
subtitle: HTTP 컨텐츠 협상
author: 김선호
categories: HTTP
banner:
video: https://vjs.zencdn.net/v/oceans.mp4
loop: true
volume: 0.8
start_at: 8.5
image: https://bit.ly/3xTmdUP
opacity: 0.618
background: "#000"
height: "100vh"
min_height: "38vh"
heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
subheading_style: "color: gold"
tags: HTTP
sidebar: []
---

## # 협상(컨텐츠 네고시에이션)
클라이언트가 선호하는 표현 요청
- Accept : 클라이언트가 선호하는 미디어 타입 전달
- Accept-Charset : 클라이언트가 선호하는 문자 인코딩
- Accept-Encoding : 클라이언트가 선호하는 압축 인코딩
- Accept-Language : 클라이언트가 선호하는 자연 언어
- 협상 헤더는 요청시에만 사용

## # 협상과 우선순위
- Quality Values(q) 값 사용
- 0 ~ 1, 클수록 높은 우선순위
- 생략하면 1
- Accept-Language : ko-KR,ko;q=0.9,en-US;q=0.8,en;q=0.7
  - ko-KR;q=1(q생략)
  - ko;q=0.9
  - en-US;q=0.8
  - en:q=0.7

## # 협상과 우선순위2
- 구체적인 것이 우선한다.
- Accept: text/*, text/plain, text/plain;format=flowed
1. text/plain;format=flowed
2. text/plain
3. text/*

## # 협상과 우선순위3
- 구체적인 것을 기준으로 미디어 타입을 맞춘다.
- Accept : text/*;q=0.3, text/html;q=0.7, text/html;level=1, text/html;level=2;q=0.4, */ *;q=0.5
- Media Type : text/html;level=1 / Quality : 1
- Media Type : text/html / Quality : 0.7
- Media Type : text/plain / Quality : 0.3
- Media Type : image/jpeg / Quality : 0.5
- Media Type : text/html;level=2 / Quality : 0.4
- Media Type : text/html;level=3 / Quality : 0.7