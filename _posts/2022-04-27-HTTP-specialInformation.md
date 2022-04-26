---
layout: post
title: HTTP 특별한 정보
subtitle: HTTP 특별한 정보
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

## # 특별한 정보
- Host : 요청한 호스트 정보(도메인)
- Location : 페이지 리다이렉션
- Allow : 허용 가능한 HTTP 메서드
- Retry-After : 유저 에이전트가 다음 요청을 하기까지 기다려야 하는 시간

## # Host
요청한 호스트 정보(도메인)
- 요청에서 사용
- 필수
- 하나의 서버가 여러 도메인을 처리할 때 사용
- 하나의 IP 주소에 여러 도메인이 적용되어 있을 때

## # Location
페이지 리다이렉션
- 웹 브라우저는 3xx 응답의 결과에 Location 헤더가 있으면, Location 위치로 자동 이동(리다이렉트)
- 응답코드 3xx에서 설명
- 201 (Created) : Location 값은 요청에 의해 생성된 리소스 URI
- 3xx (Redirection) : Location 값은 요청을 자동으로 리다이렉션 하기 위한 대상 리소스를 가리킨다.

## # Allow
허용 가능한 HTTP 메서드
- 405 (Method Not Allowed) 에서 응답에 포함해야 함.
- Allow : GET, HEAD, PUT

## # Retry-After
유저 에이전트가 다음 요청을 하기까지 기다려야 하는 시간
- 503 (Service Unavailable) : 서비스가 언제까지 불능인지 알려줄 수 있음
- Retry-After : Fri, 31 Dec 1999 23:59:59 GMT (날짜 표기)
- Retry-After : 120 (초단위 표기)