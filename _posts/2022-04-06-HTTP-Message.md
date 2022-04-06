---
layout: post
title: HTTP 메세지
subtitle: HTTP 메세지
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

## # 모든 것이 HTTP(HTTP 메세지에 모든 것을 전송)
- HTML, TEXT
- IMAGE, 음성, 영상, 파일
- JSON, XML
- 거의 모든 형태의 데이터 전송 가능
- 서버간에 데이터를 주고 받을 때도 대부분 HTTP 사용

## # HTTP 요청 메세지
GET/ search?q=hello&hl=ko HTTP/1.1 Host:www.google.com
![image](https://user-images.githubusercontent.com/63573287/162089470-5305c48c-418b-49b6-a9dc-d48054ade87e.png)

### # HTTP 요청 메세지(시작 라인)
- start-line = request-line / status-line
- request-line = method SP(공백) request-target SP HTTP-version CRLF(엔터)
- HTTP 메서드(GET : 조회)
- 요청 대상(/search?q=hello&hl=ko)
- HTTP Version

## # HTTP 응답 메세지
HTTP/1.1 200 OK <br>
Content-Length: 3424 <br>
````
<html>
<body>...<body>
</html>
````
![image](https://user-images.githubusercontent.com/63573287/162089547-0a5e962f-67fb-4555-bbf4-de1e19f6a002.png)

### # HTTP 요청 메세지(시작 라인)
- start-line = request-line / status-line
- status-line = HTTP-version SP status-code SP reason-phrase CRLF
- HTTP 버전
- HTTP 상태 코드 : 요청 성공, 실패를 나타냄
  - 200 : 성공
  - 400 : 클라이언트 요청 오류
  - 500 : 서버 내부 오류
- 이유 문구 : 사람이 이해할 수 있는 짧은 상태 코드 설명 글

## # HTTP 메세지 구조
![image](https://user-images.githubusercontent.com/63573287/162089591-a3e109e9-1a53-4281-a4ad-1afd75a3dfe4.png)

### # HTTP 헤더
- header-field = field-name":" OWS field-value OWS (OWS : 띄어쓰기 허용)
- field-name은 대소문자 구분 없음

### # HTTP 헤더 용도
- HTTP 전송에 필요한 모든 부가정보
- 예) 메세지 바디의 내용, 바디의 크기, 압축, 인증, 요청 클라이언트(브라우저) 정보, 서버 애플리케이션 정보, 캐시 관리 정보 등
- 필요시 임의의 헤더 추가 가능

### # HTTP 메세지 바디 용도
- 실제 전송할 데이터
- HTML 문서, 이미지, 영상, JSON 등등 byte로 표현할 수 있는 모든 데이터 전송 가능