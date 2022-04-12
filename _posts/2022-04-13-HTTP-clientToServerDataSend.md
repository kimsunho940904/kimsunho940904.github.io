---
layout: post
title: 클라이언트에서 서버로 데이터 전송
subtitle: 클라이언트에서 서버로 데이터 전송
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

## # 클라이언트에서 서버로 데이터 전송 2가지
- 쿼리 파라미터를 통한 데이터 전송
  - GET
  - 주로 정렬 필터(검색어)
- 메세지 바디를 통한 데이터 전송
  - POST, PUT, PATCH
  - 회원 가입, 상품 주문, 리소스 등록, 리소스 변경

## # 클라이언트에서 서버로 데이터 전송 4가지 상황
- 정적 데이터 조회
  - 이미지, 정적 텍스트 문서
  - 조회는 GET 사용
  - 정적 데이터는 일반적으로 쿼리 파라미터 없이 리소스 경로로 단순하게 조회 가능
    ![image](https://user-images.githubusercontent.com/63573287/163069841-45706626-33f1-4706-9ee9-499c381c79c3.png)
- 동적 데이터 조회
  - 주로 검색, 게시판 목록에서 정렬 필터(검색어)
  - 조회 조건을 줄여주는 필터, 조회 결과를 정렬하는 정렬 조건에 주로 사용
  - 조회는 GET 사용
  - GET은 쿼리 파라미터 사용해서 데이터를 전달
    ![image](https://user-images.githubusercontent.com/63573287/163069938-341f41fc-7ba5-4a75-967d-4b9e56d0b309.png)
- HTML Form을 통한 데이터 전송
  - 회원 가입, 상품 주문, 데이터 변경
  - Content-Type : application/x-www-form-urlencoded 사용
    - form의 내용을 메세지 바디를 통해서 전송(key=value, 쿼리 파라미터 형식)
    - 전송 데이터를 url encoding 처리
    - 예) abc김 -> abc%EA%B9%80
  - HTML Form은 GET 전송도 가능
  - Content-Type : multipart/form-data
    - 파일 업로드 같은 바이너리 데이터 전송시 사용
    - 다른 종류의 여러 파일과 폼의 내용 함께 전송 가능
  - HTML Form 전송은 GET, POST만 지원
      ![image](https://user-images.githubusercontent.com/63573287/163070121-060581eb-5084-4ba6-81c0-ed03c6c482e1.png)
      ![image](https://user-images.githubusercontent.com/63573287/163070414-47e335d4-dd32-4e64-8de9-7973e1bece35.png)
- HTTP API를 통한 데이터 전송
  - 회원 가입, 상품 주문, 데이터 변경
  - 서버 to 서버(백엔드 시스템 통신), 앱 클라이언트(아이폰, 안드로이드)
  - 웹클라이언트
    - HTML 에서 Form 전송 대신 자바 스크립트를 통한 통신에 사용(AJAX)
    - 예) React, Vue 같은 웹 클라이언트와 API 통신
  - POST, PUT, PATCH : 메세지 바디를 통해 데이터 전송
  - GET : 조회, 쿼리 파라미터로 데이터 전달
  - Content-Type : application/json을 주로 사용(사실상 표준)
    - TEXT, XML, JSON 등
        ![image](https://user-images.githubusercontent.com/63573287/163070821-d06cf208-981f-4dbc-b6ea-2aea8a8570e9.png)
  