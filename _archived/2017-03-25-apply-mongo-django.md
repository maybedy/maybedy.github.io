---
title: mongodb를 django에 적용해보기 
layout: post
category: django 
---
(mac os 기준으로 작성됨)
# mongodb 설치
1. 우선, ```brew install mongodb``` 실행
2. db path 생성(기본은 /data/db)
3. ```mongod``` 실행
- 기본 포트는 27017
- ```mongod --rest```시 28017포트로 admin? 페이지 생성됨
- db path가 permission 문제로 접근이 안될 경우,```chmod ugo+rwx dbpath```로 해결하자 
- GUI client로는 robomongo가 그나마 편한 듯
- windows에서 설치 시에 다음의 post를 참고했더니 좋았음 [http://devman.tistory.com/entry/MONGO-DB-%EC%89%BD%EA%B2%8C-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0-%EB%B0%8F-%EC%B2%B4%ED%81%AC%EC%82%AC%ED%95%AD-STEP-by-STEP]

# django에 mongo 연결  
- 다양한 라이브러리가 존재하는 듯함. 머가 좋은진 모르니 일단 쓰겠음.
- http://blog.hannal.com/category/start-with-django-lectures/ 
- https://www.peterbe.com/plog/using-mongodb-in-your-django-app/django-mongodb-html5-slides/html5.html#slide16
