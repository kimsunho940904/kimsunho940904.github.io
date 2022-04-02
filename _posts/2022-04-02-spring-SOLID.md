---
layout: post title: 좋은 객체 지향 설계의 5가지 원칙(SOLID)
subtitle: 좋은 객체 지향 설계의 5가지 원칙(SOLID)
author: 김선호 categories: 스프링 banner:
video: https://vjs.zencdn.net/v/oceans.mp4
loop: true volume: 0.8 start_at: 8.5 image: https://bit.ly/3xTmdUP
opacity: 0.618 background: "#000"
height: "100vh"
min_height: "38vh"
heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
subheading_style: "color: gold"
tags: 스프링 sidebar: []
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