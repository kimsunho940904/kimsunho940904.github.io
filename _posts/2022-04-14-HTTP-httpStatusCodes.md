---
layout: post
title: HTTP 상태 코드
subtitle: HTTP 상태 코드
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

## # 상태 코드
<p>클라이언트가 보낸 요청의 처리 상태를 응답해서 알려주는 기능</p>

- 1xx(Informational) : 요청이 수신되어 처리중
- 2xx(Successful) : 요청 정상 처리
- 3xx(Redirection) : 요청을 완료하려면 추가 행동이 필요
- 4xx(Client Error) : 클라이언트 오류, 잘못된 문법등으로 서버가 요청을 수행할 수 없음
- 5xx(Server Error) : 서버 오류, 서버가 정상 요청을 처리하지 못함

## # 1xx(Informational)
<p>요청이 수신되어 처리중</p>
- 거의 사용하지 않는다.

## # 2xx(Successful)
<p>클라이언트의 요청을 성공적으로 처리</p>

- 200 OK
- 201 Created(요청 성공해서 새로운 리소스가 생성됨)
  - 자원이 생성됬고, Location 생성 헤더가 있을 수 있겠다 라고 생각.
    - 주로 POST로 등록할 때 나옴.
- 202 Accepted(요청이 접수되었으나 처리가 완료되지 않았음)
  - 배치 처리 같은 곳에서 사용
  - 예) 요청 접수 후 1시간 뒤에 배치 프로세스가 요청을 처리함
- 204 No Content(서버가 요청을 성공적으로 수행했지만, 응답 페이로드 본문에 보낼 데이터가 없음)
  - 예) 웹 문서 편집기에서 save 버튼
  - save 버튼의 결과로 아무 내용이 없어도 된다.
  - save 버튼을 눌러도 같은 화면을 유지해야 한다.
  - 결과 내용이 없어도 204 메세지(2xx)만으로 성공을 인식할 수 있다.

## # 3xx(Redirection)
<p>요청을 완료하기 위해 유저 에이전트의 추가 조치 필요</p>

- 300 Multiple Choices
- 301 Moved Permanently
- 302 Found
- 303 See Other
- 304 Not Modified
- 307 Temporary Redirect
- 308 Permanent Redirect

## # 리다이렉션의 이해
- 웹 브라우저는 3xx 응답의 결과에 Location 헤더가 있으면, Location 위치로 자동 이동
  ![image](https://user-images.githubusercontent.com/63573287/163493276-a80cc0f8-ffa2-433a-bfdc-10a94c92b03e.png)

## # 리다이렉션의 이해(종류)
- 영구 리다이렉션 - 특정 리소스의 URI가 영구적으로 이동
  - 예) /members -> /users
  - 예) /event -> /new-event
- 일시 리다이렉션 - 일시적인 변경
  - 주문 완료 후 주문 내역 화면으로 이동
  - PRG : Post/Redirect/Get
- 특수 리다이렉션
  - 결과 대신 캐시를 사용

## # 영구 리다이렉션(301, 308)
- 리소스의 URI가 영구적으로 이동
- 원래의 URL을 사용X, 검색 엔진 등에서도 변경 인지
- 301 Moved Permanently
  - 리다이렉트시 요청 메서드가 GET으로 변하고, 본문이 제거될 수 있음(MAY)
    ![image](https://user-images.githubusercontent.com/63573287/163493610-a850f0f8-6000-4f35-83ed-b1d8a7d65309.png)
- 308 Permanent Redirect
  - 301과 기능이 같음
  - 리다이렉트시 요청 메서드와 본문 유지
    ![image](https://user-images.githubusercontent.com/63573287/163493714-20665407-879a-4946-a02b-1ede92211bbe.png)

## # 일시적인 리다이렉션(302, 307, 303)
- 리소스의 URI가 일시적으로 변경
- 따라서 검색 엔진 등에서 URL을 변경하면 안됨
- 302 Found
  - 리다이렉트시 요청 메서드가 GET으로 변하고, 본문이 제거될 수 있음(MAY)
- 307 Temporary Redirect
  - 302와 기능은 같음
  - 리다이렉트시 요청 메서드와 본문 유지(요청 메서드를 변경하면 안된다. MUST NOT)
- 303 See Other
  - 302와 기능은 같음
  - 리다이렉트시 요청 메서드가 GET으로 변경