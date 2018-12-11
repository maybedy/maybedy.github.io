---
title: Chap7. 쿼리와 데이터베이스 레이어
layout: post
category: two scoops of django
---

# 7.1 단일 객체에서 get_object_or_404() 이용
- 뷰에서만 이용한다
- 뷰와 직접적으로 관련된 곳이 아닌 곳에서는 이용하지 말자

# 7.2 예외를 일으킬 수 있는 쿼리를 주의하자
- `get_object_or_404()`는 try-except 블록으로 예외 처리를 할 필요가 없다.
- 단, 아래의 경우들은 해야 한다.

## 7.2.1 ObjectDoesNotExist와 DoesNotExist
- ObjectDoesNotExist는 어떤 모델에서도 이용
- DoesNotExist는 특정 모델에서만 이용

## 7.2.2 여러 개의 객체가 반환되었을 때
- MultipleObjectsReturned 예외

# 7.3 쿼리를 좀 더 명확하게 위해 지연 연산 이용하기

# 7.4 고급 쿼리 도구 이용하기
## 7.4.1 쿼리표현식
- 쿼리표현식을 이용하여 데이터를 처리하자

# 7.5 필수불가결한 상황이 아니라면 로우 SQL은 지향하자
# 7.6 필요에 따라 인덱스를 이용하자
# 7.7 트랜잭션
- 데이터베이스 트랜젝션 : 둘 이상의 데이터베이스 업데이트를 단일화된 작업으로 처리
- 원자성(atomic), 일관성(consistent), 독립성(isolated), 지속성(durable) = ACID
- (TODO :: 실습 통해서 보충하자)
