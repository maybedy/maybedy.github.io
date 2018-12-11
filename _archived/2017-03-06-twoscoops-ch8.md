---
title: Chap8. 함수 기반 뷰와 클래스 기반 뷰
layout: post
category: two scoops of django
---
## 8.1 함수 기반 뷰와 클래스 기반 뷰를 언제 이용할까?
- 저자 추천 : p.88 내 순서도

## 8.2 URLConf로부터 뷰 로직 분리
- 장고의 URL 디자인 철학 : 뷰와 URL의 결합은 느슨해야 한다.
- 뷰 모듈은 뷰 로직을 포함해야 한다.
- URL 모듈은 URL 로직을 포함해야 한다.

- 참고
  - 뷰에서 정의된 내용 재사용 가능하게 하자
  - 반복되는 작업을 하지 말라
  - (URL의) 무한한 확정성을 고려하자

## 8.3 URLConf에서 느슨한 결합 유지하기
- 다 분리를 해버리자

- 이유
  - 반복 작업 금지
  - 느슨한 결함 : 모델과 템플릿 이름 제거
  - URLConf는 한 번에 한가지씩 업무를 명확하고 매끄럽게 처리
  - 클래스 기반일 경우 상속을 이용하여 로직을 잘 표현하자
  - 표준화된 정의를 구현 -> 무한한 유연성 고려

## 8.4 URL 이름 공간 이용하기
- `tastings_detail` 대신 `tastings:detail`이라고 정의
  - 서드 파티 라이브러리와 상호 운영성을 높임
  - 검색, 업그레이드, 리팩터링을 쉽게 하게 함

## 8.5 URLConf에서 뷰를 문자열로 지목하지 말자
- 뷰를 명시적으로 정의하자

## 8.6 뷰에서 비즈니스 로직 분리하기

## 8.7 장고의 뷰와 함수
- 장고의 뷰는 HTTP를 요청하는 객체(request)를 받아서 HTTP를 응답하는 객체로 변경하는 함수(response)
-
```
HttpResponse = view(HttpRequest)

HttpResponse = View.as_view()(HttpRequest)
```
- 뷰의 기본 형태 : 함수형, 클래스형(HTTP 메서드의 선언이 필요)

## 8.8 locals()를 뷰 콘텍스트에 이용하지 말자
- 안티 패턴임