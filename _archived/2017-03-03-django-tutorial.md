---
title: django tutorial 중
layout: post
category: django
---

# Django tutorial

## django tutorial part 2
[https://docs.djangoproject.com/en/1.10/intro/tutorial02/#]
- Database 는 PostgreSQL로 진행
- time zone setting 관련하여, 구글링 중
```
# Internationalization
...
TIME_ZONE = 'Asia/Seoul'
```
발견.
~~이게 바로 적용이 안되어서 이외의 옵션은 주석처리 하라는 포스트를 보았다...~~ `USE_L10N = False` 처리. 왜 그런지는 좀더 알아보기로!
공식문서:https://docs.djangoproject.com/en/1.10/ref/settings/#std:setting-TIME_ZONE

### TODO
- 문수형 "smart url, debugger"
- datetime module 사용하지 말자
- https://libsora.so/posts/good-django-library
