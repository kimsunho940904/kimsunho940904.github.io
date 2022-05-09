---
layout: post
title: HTTP 헤더 캐시와 조건부 요청
subtitle: 캐시와 조건부 요청
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

## # 캐시 기본 동작
### # 캐시가 없을 때
1. 요청을 해서 결과가 있으면 내려준다.
2. 결과를 내려줄 때 HTTP 헤더와 HTTP 바디의 용량을 합쳐서 내려준다.
3. 그러면서 이미지가 표시된다.

## # 캐시가 없을 때
1. 데이터가 변경되지 않아도 계속 네트워크를 통해서 데이터 다운로드 받아야 한다.
2. 인터넷 네트워크는 매우 느리고 비싸다.
3. 브라우저 로딩 속도가 느려진다.

### # 캐시 적용
1. cache-control = 캐시가 유효한 시간.
   1. cache-control: max-age=60 (60초 동안 캐시가 유효하다.)
2. 캐시를 저장하는 저장소에 이미지를 저장
3. 응답 결과를 캐시에 저장
4. 두번째 요청하면, 브라우저 캐시를 조회해서 가져온다.

## # 캐시 적용
1. 캐시 덕분에 캐시 가능 시간동안 네트워크를 사용하지 않아도 된다.
2. 비싼 네트워크 사용량을 줄일 수 있다.
3. 브라우저 로딩 속도가 매우 빠르다.


