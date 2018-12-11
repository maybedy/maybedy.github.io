---
title: Chap6. 장고에서 모델 이용하기
layout: post
category: two scoops of django
---
# 장고에서 모델 이용하기

## 6.1 시작하기

### 6.1.1 모델의 수
- 저자의 추천 : 앱 하나에 모델이 5개 이상을 넘기지 않도록 하자.

### 6.1.2 모델 상속 주의
- 장고의 3가지 모델 상속 방법
  - 추상화 기초 클래스(abstract base class)
  - 멀티테이블 상속(multi-table inheritance)
  - 프락시 모델(proxy model)
- 멀티테이블 상속은 반드시 피하자. 모델들 사이에서 OneToOneFields와 ForeignKeys를 이요함으로써 수월하게 컨트롤

### 6.1.3 실제로 모델 상속해 보기 : TimeStampedModel
- 장고에서는 created와 modified 타임스탬프 필드를 생성해두는 것이 일반적. 그렇지만, TimeStampedModel을 만들어 이 모델이 필드 추가를 처리해주게 함.(created와 modified 필드를 자동으로 업데이트해 주는 추상화 기반 클래스 모델)

``` python
from django.db import models

class TimeStampedModel(models.Model):
  created = models.DateTimeField(auto_now_add=True)
  modified = models.DateTimeField(auto_now=True)

  class Meta: # 추상화 기초 클래스
      abstract = True
```
- 추상화 기초 클래스 : 위의 정의를 이용하면, core_timestampedmodel 테이블이 생성되지 않는다.

### 6.1.4 데이터베이스 마이그레이션
- django.db.migrations라는 강력한 데이터베이스 마이그레이션 도구 제공
- `python manage.py makemigrations`로 실행
- MySQL을 이용할 때: 데이터베이스를 반드시 백업(롤백 불가)

## 6.2 장고 모델 디자인
### 6.2.1 정규화하기
- 데이터베이스 정규화 : 장고 모델 디자인은 항상 정규화로부터, 비정규화는 되도록이면 피하자

### 6.2.2 캐시와 비정규화

### 6.2.3 반드시 필요한 경우에만 비정규화를 하도록 하자

### 6.2.4 언제 널을 쓰고 언제 공백을 쓸 것인가
- null=True, blank=True (TODO :: 보강)

### 6.2.5 언제 BinaryField를 이용할 것인가?
- 파일을 직접 서비스하는 것은 금물
- 데이터베이스의 읽기/쓰기 속도는 항상 파일 시스템의 읽기/쓰기 속도보다 느리다.

### 6.2.6 범용 관계 피하기
- 범용관계 이용과 models.field.GenericForeignKey 이용은 자제
- 쿼리 속도에 손해(NoSQL과 유사)

## 6.3 모델의 \_meta API
- `_meta`의 원래 목적은 모델에 대한 부가적인 정보를 장고 내부적으로 이용하기 위함
- 문서 읽어보기

## 6.4 모델 매니저
- 모델 매니저 : 데이터베이스와 연동하는 인터페이스(장고의 ORM)
- 장고는 각 모델 클래스에 대한 기본 모델 매니저 제공. 스스로 제작 가능
- 모델 상속 시, 추상화 기초 클래스의 자식은 부모 모델의 모델 매니저를 받게됨
- 모델 클래스에 적용되는 첫 번째 매니저는 장고가 기본값을 취급하는 매니저
- (단, 파이썬의 일반적인 패턴을 무시함 -> `objects = models.Manager()`를 정의)
- (TODO :: 다시 이해하기)

## 6.5 거대 모델
- 거대 모델 : 데이터 관련 코드를 모델 메서드, 클래스 메서드, 프로퍼티, 혹은 매니저 메서드 안에 넣어 캡슐화
- 거대 모델은 프로젝트 전체를 통해 코드 재사용을 개선할 수 있는 최고의 방법
- 모델 코드의 크기를 폭발적으로 증가. 테스트 유지 보수 어려워진다.
- 겹치는 코드의 경우 로직들을 모델 행동이나 상태 없는 헬퍼 함수로 이전
### 6.5.1 모델 행동(믹스인)
- 캡슐화, 구성화의 개념 -> 문서 보기

### 6.5.2 상태 없는 헬퍼 함수
