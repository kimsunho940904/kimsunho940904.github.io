---
layout: post
title: HTTP 헤더
subtitle: HTTP 헤더
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

## # HTTP 헤더 용도
- HTTP 전송에 필요한 모든 부가정보
- 예) 메시지 바디의 내용, 메시지 바디의 크기, 압축, 인증, 요청 클라이언트, 서버 정보, 캐시 관리 정보 등
- 표준 헤더가 정말 많다.
- 필요시 임의의 헤더 추가 가능
  - helloworld: hihi

## # HTTP 헤더 분류(과거)
- General 헤더 : 메시지 전체에 적용되는 정보, 예)Connection : close
- Request 헤더 : 요청 정보, 예) User-agent : Mozilla/5.0 (Macintosh; ..)
- Response 헤더 : 응답 정보, 예) Server: Apache
- Entity 헤더 : 엔티티 바디 정보, 예) Content-Type: text/html, Content-Length: 3423

## # HTTP BODY(과거)
- 메시지 본문은 엔티티 본문을 전달하는데 사용
- 엔티티 본문은 요청이나 응답에서 전달할 실제 데이터
- 엔티티 헤더는 엔티티 본문의 데이터를 해석할 수 있는 정보 제공
  - 데이터 유형(html, json), 데이터 길이, 압축 정보 등등

## # HTTP BODY
- 메시지 본문(message body)을 통해 표현 데이터 전달
- 메시지 본문 = 페이로드(payload)
- 표현은 요청이나 응답에서 전달할 실제 데이터
- 표현 헤더는 표현 데이터를 해석할 수 있는 정보 제공
  - 데이터 유형(html, json),데이터 길이, 압축 정보 등등
- 참고 : 표현 헤더는 표현 메타데이터와 페이로드 메시지를 구분해야 하지만 생략