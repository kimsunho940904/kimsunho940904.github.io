---
layout: post
title: HTTP 쿠키
subtitle: HTTP 쿠키
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

## # 쿠키
- Set-Cookie : 서버에서 클라이언트로 쿠키 전달(응답)
- Cookie : 클라이언트가 서버에서 받은 쿠기를 저장하고, HTTP 요청시 서버로 전달

## # Stateless
- HTTP는 무상태 프로토콜이다.
- 클라이언트가 서버가 요청과 응답을 주고 받으면 연결이 끊어진다.
- 클라이언트가 다시 요청하면 서버는 이전 요청을 기억하지 못한다.
- 클라이언트와 서버는 서로 상태를 유지하지 않는다.

## # 쿠키 전달 방식
1. 웹브라우저가 post로 로그인(user=홍길동) 이라고 보내면,
2. 서버는 Set-Cookie : user=홍길동 으로 쿠키에 말아버림.
3. 웹 브라우저 내부에 쿠키저장소에 user=홍길동을 저장

<hr>

![image](https://user-images.githubusercontent.com/63573287/165646661-cd309afb-0d53-4c20-82c0-abbeffc379a1.png)


<hr>

![image](https://user-images.githubusercontent.com/63573287/165646714-2a9c41bb-9046-4f9d-8f39-a42419650822.png)

## # 쿠키
- 예) set-cookie: sessionId=acdb1234; expires=Sat,26-Dec-2020 00:00:00 GMT; path=/; domain=.google.com;Secure
- 사용처
  - 사용자 로그인 세션 관리
  - 광고 정보 트래킹
- 쿠키 정보는 항상 서버에 전송됨
  - 네트워크 트래픽 추가 유발
  - 최소한의 정보만 사용(세션 id, 인증 토큰)
  - 서버에 전송하지 않고, 웹 브라우저 내부에 데이터를 저장하고 싶으면 웹 스토리지 (localStorage, sessionStorage) 참고
- 주의
  - 보안에 민감한 데이터는 저장하면 안된다.(주민번호, 신용카드 번호 등등)