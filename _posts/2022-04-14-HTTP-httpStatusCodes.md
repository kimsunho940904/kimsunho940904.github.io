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
### 클라이언트가 보낸 요청의 처리 상태를 응답해서 알려주는 기능
- 1xx(Informational) : 요청이 수신되어 처리중
- 2xx(Successful) : 요청 정상 처리
- 3xx(Redirection) : 요청을 완료하려면 추가 행동이 필요
- 4xx(Client Error) : 클라이언트 오류, 잘못된 문법등으로 서버가 요청을 수행할 수 없음
- 5xx(Server Error) : 서버 오류, 서버가 정상 요청을 처리하지 못함

## # 1xx(Informational)
### 요청이 수신되어 처리중
- 거의 사용하지 않는다.

## # 2xx(Successful)
### # 클라이언트의 요청을 성공적으로 처리
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

