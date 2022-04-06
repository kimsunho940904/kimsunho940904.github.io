---
layout: post
title: WAS, Web Server 차이
subtitle: WAS, Web Server 차이
author: 김선호
categories: Develop
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
tags: Develop
sidebar: []
---

## # 웹 서버 (Web Server)
- 사전적 정의 : 웹 브라우저 클라이언트로부터 HTTP 요청을 받아들이고 HTML 문서와 같은 웹 페이지를 반환하는 컴퓨터 프로그램
- 클라이언트가 웹 브라우저에서 어떠한 페이지 요청을 하면 웹 서버에서 그 요청을 받아 **정적 컨텐츠를 제공하는 서버**
  - 정적 컨텐츠 : 단순 HTML 문서, CSS, Javascript, 이미지, 파일 등 즉시 응답가능한 컨텐츠
- 웹 서버가 동적 컨텐츠를 요청 받으면 WAS에게 해당 요청을 넘겨주고, WAS에서 처리한 결과를 클라이언트에게 전달해주는 역할
- 대표적인 웹 서버 : Apache
![1](https://user-images.githubusercontent.com/63573287/161907618-cbe178b6-21b6-4a47-a6b2-f53c9976c273.PNG)

## # WAS
- 사전적 정의 : 인터넷 상에서 HTTP 프로토콜을 통해 사용자 컴퓨터나 장치에 어플리케이션을 수행해주는 미들웨어로, 주로 동적 서버 컨텐츠를 수행하는 것으로 웹서버와 구별이 되며, 주로 데이터베이스 서버와 같이 수행
- WAS는 **웹 서버**와 **웹 컨테이너**가 합쳐진 형태
- 웹서버 단독으로 처리할 수 없는 **데이터베이스 조회나 다양한 로직 처리가 필요한 동적 컨텐츠를 제공**
- WAS는 JSP, Servlet **구동환경을 제공**해주기 때문에 **웹 컨테이너** 혹은 **서블릿 컨테이너**라고도 불린다.
- 대표적인 WAS : Tomcat
![2](https://user-images.githubusercontent.com/63573287/161908179-b351fb0a-3578-47b9-98eb-99c4749d1177.PNG)
