---
title: Chap3. 어떻게 장고 프로젝트를 구성할 것인가
layout: post
category: two scoops of django
---
# 어떻게 장고 프로젝트를 구성할 것인가

- tip : cookiecutter-django

## 3.1 장고 1.8의 기본 프로젝트 구성
```
mysite/
    manage.py
    my_app/
        __init__.py
        admin.py
        models.py
        tests.py
        views.py
    my_site/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```


## 3.2 우리가 선호하는 프로젝트 구성
- `django-admin.py startproject` 명령을 통해 삼단 방식에 기반한 구조가 생성됨

```
<repository_root>/
    <django_project_root>/
        <configuration_root>/
```

### 3.2.1 최상위 레벨: 저장소 루트
- README.rst, docs/, requirements.txt, .gitignore 등 존재

### 3.2.2 두번째 레벨: 프로젝트 루트
- 프로젝트 소스들이 위치함

### 3.2.3 세번째 레벨: 설정 루트
- settings 모듈과 기본 URLConf(urlspy)가 저장됨

## 3.4 virtualenv 설정
- 프로젝트 및 하위 디렉터리 내 virtualenv 존재하지 않음

## 3.5 startproject 살펴보기
- cookiecutter-django 활용 (TODO) : 추후에 내용 보강하기
