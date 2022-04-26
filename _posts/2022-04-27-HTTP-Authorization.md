---
layout: post
title: HTTP 인증
subtitle: HTTP 인증
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

## # 인증
- Authorization : 클라이언트 인증 정보를 서버에 전달
- WWW-Authenticate : 리소스 접근시 필요한 인증 방법 정의

## # Authorization
클라이언트 인증 정보를 서버에 전달
- Authorization : Basic xxxxxxxxxxxxxxxxxxxxxxx

## # WWW-Authenticate
- 리소스 접근시 필요한 인증 방법 정의
- 401 Unauthorized 응답과 함께 사용
- WWW-Authenticate : Newauth realm = "apps", type=1, title="Login to \"apps\"",Basic realm="simple"