---
layout: post
title: HTTP 헤더 캐시와 조건부 요청
subtitle: 캐시와 조건부 요청
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

## # 캐시 기본 동작
### # 캐시가 없을 때
1. 요청을 해서 결과가 있으면 내려준다.
2. 결과를 내려줄 때 HTTP 헤더와 HTTP 바디의 용량을 합쳐서 내려준다.
3. 그러면서 이미지가 표시된다.

## # 캐시가 없을 때
1. 데이터가 변경되지 않아도 계속 네트워크를 통해서 데이터 다운로드 받아야 한다.
2. 인터넷 네트워크는 매우 느리고 비싸다.
3. 브라우저 로딩 속도가 느려진다.

### # 캐시 적용
1. cache-control = 캐시가 유효한 시간.
   1. cache-control: max-age=60 (60초 동안 캐시가 유효하다.)
2. 캐시를 저장하는 저장소에 이미지를 저장
3. 응답 결과를 캐시에 저장
4. 두번째 요청하면, 브라우저 캐시를 조회해서 가져온다.

## # 캐시 적용
1. 캐시 덕분에 캐시 가능 시간동안 네트워크를 사용하지 않아도 된다.
2. 비싼 네트워크 사용량을 줄일 수 있다.
3. 브라우저 로딩 속도가 매우 빠르다.

## # 캐시 시간 초과
- 캐시 유효 시간이 초과해서 서버에 다시 요청하면 다음 두 가지 상황이 나타난다.
  - 서버에서 기존 데이터를 변경함
  - 서버에서 기존 데이터를 변경하지 않음

## # 캐시 시간 초과
- 캐시 만료후에도 서버에서 데이터를 변경하지 않음
- 생각해보면 데이터를 전송하는 대신에 저장해 두었던 캐시를 재사용 할 수 있다.
- 단 클라이언트의 데이터와 서버의 데이터가 같다는 사실을 확인할 수 있는 방법 필요

## # 검증 헤더 추가
- Last-Modified : 날짜
- 응답 결과를 캐시에 저장하는데, Last-Modified 값을 기록하고 있는다.
- 시간이 지나서 캐시에서 날라가지만, Last-Modified가 있으면, 웹브라우저에서 서버에 요청을 보낼 때, 
- if-modified-since : 날짜 해서 서버에 요청을 보낸다.
- 서버에선 if-modified-since와 Last-Modified 가 같으면, 서버에서 304 Not Modified를 내보낸다.
- HTTP 헤더만 전송하면서, 캐시를 다시 세팅해서, 브라우저에서 다시 사용

## # 검증 헤더와 조건부 요청 정리
- 캐시 유효 시간이 초과해도, 서버의 데이터가 갱신되지 않으면
- 304 Not Modified + 헤더 메타 정보만 응답 (바디 X)
- 클라이언트는 서버가 보낸 응답 헤더 정보로 캐시의 메타 정보를 갱신
- 클라이언트는 캐시에 저장되어 있는 데이터 재활용
- 결과적으로 네트워크 다운로드가 발생하지만, 용량이 적은 헤더 정보만 다운로드
- 매우 실용적

## # 검증 헤더와 조건부 요청
- 검증 헤더
  - 캐시 데이터와 서버 데이터가 같은지 검증하는 데이터
  - Last-Modified, ETag
- 조건부 요청 헤더
  - 검증 헤더로 조건에 따른 분기
  - If-Modified-Since : Last-Modified 사용
  - If-None-Match : ETag 사용
  - 조건이 만족하면 200 OK
  - 조건이 만족하지 않으면 304 Not Modified

## # 검증 헤더와 조건부 요청 예시
- If-Modified-Since : 이후에 데이터가 수정되었으면 ? 
  - 데이터 미변경 예시
    - 캐시 : 2020년 11월 10일 10:00:00 vs 서버 : 2020년 11월 10일 10:00:00
    - 304 Not Modified, 헤더 데이터만 전송 (BODY 미포함)
    - 전송 용량 0.1M(헤더 0.1M, 바디 1.0M)
  - 데이터 변경 예시
    - 캐시 : 2020년 11월 10일 10:00:00 vs 서버 : 2020년 11월 10일 11:00:00
    - 200 OK, 모든 데이터 전송 (BODY 포함)
    - 전송 용량 1.1M(헤더 0.1M, 바디 1.0M)

## # 검증 헤더와 조건부 요청 Last-Modified, If-Modified-Since 단점
- 1초 미만 단위로 캐시 조정이 불가능
- 날짜 기반의 로직 사용
- 데이터를 수정해서 날짜가 다르지만, 같은 데이터를 수정해서 데이터 결과가 똑같은 경우
- 서버에서 별도의 캐시 로직을 관리하고 싶은 경우
  - 예) 스페이스나 주석처럼 크게 영향이 없는 변경에서 캐시를 유지하고 싶은 경우

## # ETag, If-None-Match
- ETag(Entity Tag)
- 캐시용 데이터에 임의의 고유한 버전 이름을 달아둠
  - 예) ETag : "v1.0", ETag : "aasdjaskl3"
- 데이터가 변경되면 이 이름을 바꾸어서 변경함(Hash를 다시 생성)
  - 예) ETag : "aaaaa" -> ETag : "bbbbb"
- 진짜 단순하게 ETag만 보내서 같으면 유지, 다르면 다시 받기

## # ETag, If-None-Match 정리
- 진짜 단순하게 ETag만 서버에 보내서 같으면 유지, 다르면 다시 받기!
- 캐시 제어 로직을 서버에서 완전히 관리
- 클라이언트는 단순히 이 값을 서버에 제공(클라이언트는 캐시 메커니즘을 모름)
  - 예)
  - 서버는 베타 오픈 기간인 3일 동안 파일이 변경되어도 ETag를 동일하게 유지
  - 애플리케이션 배포 주기에 맞추어 ETag 모두 갱신

