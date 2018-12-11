---
title: Chap2. 최적화된 장고 환경 꾸미기
layout: post
category: two scoops of django
---
# 최적화된 장고 환경 꾸미기

## 2.1 같은 데이터베이스를 이용하라
- 실제 운영 환경과 로컬 개발 환경에서 같은 데이터베이스 엔진을 사용하여라
- tip : 최고의 조합 = 장고 + PostgreSQL

## 2.2 pip와 virtualenv 이용하기
- virtualenv는 파이썬 패키지 의존성을 유지할 수 있게 독립된 파이썬 환경을 제공하는 도구
- virtualenv를 활용하여 장고의 재설치 등을 막을 수 있다
- pip는 파이썬 패키지 인덱스와 그 미러 사이트에서 파이썬 패키지를 가져오는 도구

## 2.3 pip를 이용하여 장고와 의존 패키지 설치하기
- pip와 requirements 파일을 이용하여 파이썬 패키지 설치
- requirements 파일 내 패키지 이름과 버전 명시

# 2.5 동일한 환경 구성
- 가상화를 이용하여 동일한 환경으로 맞추어 준다.
- Tip: Docker Conatiner
