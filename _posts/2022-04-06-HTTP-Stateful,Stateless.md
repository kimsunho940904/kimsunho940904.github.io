---
layout: post
title: Stateful, Stateless 차이
subtitle: Stateful, Stateless의 차이
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

## # 무상태 프로토콜(Stateless)
- 서버가 클라이언트의 상태를 보존하지 않는다.
- 장점 : 서버 확장성 높음(스케일 아웃)
- 단점 : 클라이언트가 추가 데이터 전송

## # 상태 유지(Stateful)
- 서버가 클라이언트의 이전상태를 보존하는 것.

## # Stateful, Stateless 차이
- 상태유지 : 중간에 다른 점원으로 바뀌면 안된다.(중간에 다른 점원으로 바뀔 때 상태 정보를 다른 점원에게 미리 알려주어야 한다.)
- 무상태 : 중간에 다른 점원으로 바뀌어도 된다.
  - 갑자기 고객이 증가해도 점원을 대거 투입할 수 있다.
  - 갑자기 클라이언트 요청이 증가해도 서버를 대거 투입할 수 있다.
- 무상태는 응답 서버를 쉽게 바꿀 수 있다. -> 무한한 서버 증설이 가능 

### # 상태 유지의 예 (Stateful)
- 고객 : 이 노트북 얼마인가요?
- 점원 : 100만원 입니다.
- 고객 : 2개 구매하겠습니다.
- 점원 : 200만원 입니다. 신용카드, 현금 중 어떤 걸로 구매하시겠어요?
- 고객 : 신용카드로 구매하겠습니다.
- 점원 : 200만원 결제 완료되었습니다.

### # 무상태의 예 (Stateful)
- 고객 : 이 노트북 얼마인가요?
- 점원 : 100만원 입니다.
- 고객 : 노트북 2개 구매하겠습니다.
- 점원 : 노트북 2개는 200만원 입니다. 신용카드, 현금 중 어떤 걸로 구매하시겠어요?
- 고객 : 노트북 2개를 신용카드로 구매하겠습니다.
- 점원 : 200만원 결제 완료되었습니다.

## # Stateless 실무 한계
- 모든 것을 무상태로 설계할 수 있는 경우도 있고 없는 경우도 있다.
- 무상태
  - 로그인이 필요 없는 단순한 서비스 소개 화면
- 상태 유지
  - 로그인
- 로그인한 사용자의 경우 로그인 했다는 상태를 서버에 유지
- 일반적으로 브라우저 쿠키와 서버 세션등을 사용해서 상태 유지
- 상태 유지는 최소한만 사용