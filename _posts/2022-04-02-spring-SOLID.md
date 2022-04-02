---
layout: post 
title: 좋은 객체 지향 설계의 5가지 원칙(SOLID)
subtitle: 좋은 객체 지향 설계의 5가지 원칙(SOLID)
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

<h2>
SOLID
</h2>
<ul>
<li>SRP : 단일 책임 원칙(single responsibility principle)</li>
<li>OCP : 개방-폐쇄 원칙(Open/closed principle)</li>
<li>LSP : 리스코프 치환 원칙(Liskov substitution principle)</li>
<li>ISP : 인터페이스 분리 원칙(Interface segregation principle)</li>
<li>DIP : 의존관계 역전 원칙(Dependency inversion principle)</li>
</ul>


<h3>
SRP 단일 책임 원칙
</h3>
<ul>
<li>한 클래스는 하나의 책임만 가져야 한다.</li>
<li>하나의 책임이라는 것은 모호하다.</li>
<ul>
<li>클 수 있고, 작을 수 있다.</li>
<li>문맥과 상황에 따라 다르다.</li>
</ul>
<li>중요한 기준은 변경이다. 변경이 있을 때 파급 효과가 적으면 단일 책임 원칙을 잘 따른 것</li>
<li>예) UI 변경, 객체의 생성과 사용을 분리</li>
</ul>

<h3>
OCP 개방-폐쇄 원칙
</h3>
<ul>
<li>소프트웨어 요소는 확장에는 열려 있으나 변경에는 닫혀 있어야 한다.</li>
<li>다형성을 활용하면 지킬 수 있다.</li>
<li>인터페이스를 구현한 새로운 클래스를 하나 만들어서 새로운 기능을 구현</li>
</ul>

<h3>
LSP 리스코프 치환 원칙
</h3>
<ul>
<li>프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 한다.</li>
<li>다형성에서 하위 클래스는 인터페이스 규약을 다 지켜야 한다는 것, 다형성을 지원하기 위한 원칙, 인터페이스를 구현한 구현체는 믿고 사용하려면, 이 원칙이 필요하다.</li>
<li>단순히 컴파일에 성공하는 것을 넘어서는 이야기</li>
<li>예) 자동차 인터페이스의 엑셀은 앞으로 가라는 기능, 뒤로 가게 구현하면 LSP 위반, 느리더라도 앞으로 가야함.</li>
</ul>