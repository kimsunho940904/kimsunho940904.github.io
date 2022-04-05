---
layout: post
title: web.xml 이란?
subtitle: web.xml의 역할
author: 김선호
categories: 스프링
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
tags: 스프링
sidebar: []
---

## # web.xml
- web.xml 에서 서블릿 매핑 되는 방법, 인증이 필요한 URL등의 정보를 확인
- Deployment Descriptor(배포 설명자) 로써 XML형식의 파일
- 모든 Web Application은 반드시 하나의 web.xml 파일을 가져야하며, 위치는 WEB-INF폴더 아래에 있다.
- web.xml파일의 설정들은 Web Application 시작시 메모리에 로딩된다.

## # 배포 설명자
- 애플리케이션의 클래스, 리소스, 구성 및 웹 서버가 이를 사용해서 웹 요청을 처리하는 방법을 기술하는 곳
- 애플리케이션에 대한 요청이 수신되면 배포 설명자(web.xml)를 사용하여 요청의 URL을 해당 요청을 처리해야 하는 코드에 매핑한다.

## # 예시
아래의 web.xml에서 URL 경로인 /welcome을 서블릿 클래스 servlets.Servlet에 매핑한다.

````
<web-app>
<!-- aliases 설정 -->
<servlet>
<servlet-name>welcome</servlet-name>
<servlet-class>servlets.Servlet</servlet-class>
</servlet>
<!-- 매핑 -->
<servlet-mapping>
<servlet-name>welcome</servlet-name>
<url-pattern>/welcome</url-pattern>
</servlet-mapping>
</web-app>
````

## # web.xml에 작성되는 내용
- ServletContext의 초기 변수
- 서블릿 및 jsp에 대한 정의 및 매핑
- MimeType 매핑
- Session의 대한 유효시간
- welcome file list
- 오류  핸들러

````
  <error-page>
  <error-code>500</error-code>
  <location>/errors/servererror.jsp</location>
  </error-page>
````

## # Spring MVC에서의 web.xml 역할
- DispatcherServlet
- ContextLoaderListener
- encodingFilter

## # DispatcherServlet
- Spring 컨테이러 생성 (컨트롤러의 라이프사이클 관리)
- 클라이언트의 요청을 처음으로 받는 클래스
- 클라이언트의 요청을 가로채서 컨트롤러에 보내는 역할

````
<servlet>
<servlet-name>addServlet</servlet-name>
<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
<!-- contextLoader가 해당 위치의 설정 파일을 읽어, 해당 파일을 dispatcherServlet로 만든다. -->
<init-param>
<param-name>contextConfigLocation</param-name>
<param-value>/WEB-INF/addServlet-servlet.xml</param-value>
</init-param>
<load-on-startup>1</load-on-startup>
</servlet>

<!-- /add로 시작하는 url 요청을 받아 addServlet에서 처리 -->
<servlet-mapping>
<servlet-name>addServlet</servlet-name>
<url-pattern>/add</url-pattern>
</servlet-mapping>
````
