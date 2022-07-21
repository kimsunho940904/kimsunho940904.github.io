---
layout: post
title: 웹 서버, 웹 애플리케이션 서버
subtitle: Web Server, Web Application Server
author: 김선호
categories: HTTP 
banner:
video: https://vjs.zencdn.net/v/oceans.mp4
loop: true volume: 0.8 start_at: 8.5 image: https://bit.ly/3xTmdUP
opacity: 0.618 background: "#000"
height: "100vh"
min_height: "38vh"
heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
subheading_style: "color: gold"
tags: HTTP sidebar: []
---

## # 웹 서버(Web Server)

- HTTP 기반으로 동작
- 정적 리소스 제공, 기타 부가기능
- 정적파일 HTML, CSS, JS, 이미지, 영상
- 예)NGINX, APACHE

## # 웹 애플리케이션 서버(WAS - Web Application Server)

- HTTP 기반으로 동작
- 웹 서버 기능 포함(정적 리소스 제공 가능)
- 프로그램 코드를 실행해서 애플리케이션 로직 수행
    - 동적 HTML, HTTP API(JSON)
    - 서블릿, JSP, 스프링 MVC
- 예) 톰캣(Tomcat) Jetty, Undertow

## # 웹 서버, 웹 애플리케이션 서버(WAS)의 차이

- 웹 서버는 정적 리소스 파일, WAS는 애플리케이션 로직
    - 웹 서버도 프로그램을 실행하는 기능을 포함하기도 한다.
    - 웹 애플리케이션 서버도 웹 서버의 기능을 제공함
- 자바는 서블릿 컨네이터 기능을 제공하면 WAS
    - 서블릿 없이 자바코드르 실행하는 서버 프레임워크도 있다.
- WAS는 애플리케이션 코드를 실행하는데 더 특화



