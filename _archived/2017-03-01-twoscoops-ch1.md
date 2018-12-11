---
title: Chap1. Coding Style
layout: post
category: two scoops of django
---

# 코딩 스타일
## 1.3 임포트에 대해
1. 표준 라이브러리 임포트
2. 연관 외부 라이브러리 임포트
3. 로컬 애플리케이션 또는 라이브러리에 한정된 임포트

## 1.4 명시적 성격의 상대 임포트 이용하기
|코드|임포트 타입|용도|
|:------|:----|:-------|
| `from core.views import FoodMixin` | 절대 임포트 | 외부에서 임포트해서 현재 앱에서 이용할 때|
| `from .models import WaffleCone` | 명시적 상대 | 다른 모듈에서 임포트해서 현재 앱에서 이용할 때|
|`from models import WaffleCone`| 암묵적 상대| 종종 다른 모듈에서 임포트해서 현재 앱에서 이용할 때 쓰지만 좋은 방법은 아니다.|

## 1.5 import \*는 피하자

``` python
from django.forms import *
from django.db.models import *
```
- 위와 같은 짓은 하지 말자

## 1.6 장고 코딩 스타일

__1.6.1 장고 코딩 스타일__
- http://2scoops.co/1.8-coding-style 참조



-------------
