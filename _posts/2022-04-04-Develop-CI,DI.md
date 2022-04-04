---
layout: post
title: CI와DI
subtitle: Connectiong Information and Duplication Information
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

<h2>
CI(Connecting Information)
</h2>
<pre>
CI는 Connecting Information의 약자로 88byte로 된 정보이며,
서로 서비스를 연계하여 서로 다른 인터넷 서비스 간에도 동일한 사용자인지 구분을 가능하게 해주는 정보 입니다.
쉽게 생각하면, CI는 주민등록번호 같은 존재입니다.
인터넷 어떤 사이트에서 회원가입을 하여도 주민등록번호는 저라는 사실을 증명해 줄 수 있습니다.
</pre>

<h2>
DI(Duplication Information)
</h2>
<pre>
DI는 Duplication Information의 약자로 64byte로 된 정보이며,
기본적으로 DI는 중복가입체크를 하고 해당 정보를 통해 한 사람의 명의로 여러개의 게정을 만들어 악용하는 것을 방지 할 수 있는 정보입니다.
DI는 특정 서비스에서 나에게 식별 번호를 준다고 생각할 수 있습니다.
예를들면, 네이버에 가입할 경우, 네이버 번호라는 것을 준다고 가정하여,
아이디를 여러개 만들었을 때, 각자 계정 ID가 달라도 네이버 번호라는 식별 번호는 같기 때문에
이 네이버 번호를 통해 제가 저라는 것을 인증해 줄 수 있습니다.
</pre>

<h2>
CI와 DI의 차이점
</h2>
<ul>
    <li>A사이트와 B사이트의 각각 회원가입을 하였을 경우, 서로 다른 사이트 이지만 CI는 같다.</li>
        <ul>
            <li>A사이트 / ID : naverA / CI : 12345678</li>
            <li>B사이트 / ID : naverA / CI : 12345678</li>
        </ul>
    <li>반대로, A사이트에 회원가입을 여러번 하여 계정이 여러개일 경우, ID는 서로 다르겠지만, DI는 같다.</li>
        <ul>
            <li>ID : naverA / DI : 1234</li>
            <li>ID : naverB / DI : 1234</li>
        </ul>
</ul>

<h2>
정리
</h2>
CI는 인터넷 공간 어디서나 쓸 수 있는 주민등록번호와 같고, <br>
DI는 특정 서비스에서만 사용 가능한 네이버 번호로 비유할 수 있다.