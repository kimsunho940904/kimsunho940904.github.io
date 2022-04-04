---
layout: post
title: HTTP로 요청 했지만, HTTPS로 돌아오는 현상
subtitle: http -> https
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


이 부분이 있으면, http -> https로 redirect 된다.

```
web.xml
    <security-constraint>
    <web-resource-collection>
        <web-resource-name>SSL Forward</web-resource-name>
        <url-pattern>/*</url-pattern>
    </web-resource-collection>

    <user-data-constraint>
        <transport-guarantee>CONFIDENTIAL</transport-guarantee>
    </user-data-constraint>
	</security-constraint>
```