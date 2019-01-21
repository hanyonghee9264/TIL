## EC2

클라이언트로부터의 접속을 설정

Django application이 실행되고 있는 서버 컴퓨터



## S3 (정적파일)

클라우드(실제로 존재는 하지만 가상공간) 객체 스토리지



## RDS(외부에 있는 데이터베이스 서버)

클라우드 데이터베이스 서버



## WebServer, WSGI, DOCKER 개념

request -> EC2 -> (runserver:8000) 				     -> Django

request -> EC2 -> Nginx(WebServer:80) -> uWSGI(WSGI) -> DJango

request -> EC2 -> 					     uWSGI(WSGI) -> DJango



**Cloud Server** (외부의 물리서버 혹은 가상서버)

-> `WebServer` application (사용자의 Request를 받고, 응답을 보내주는데 특화)

-> `WSGI application` ( WebServer와 Python web application을 중개)

-> `Python web application` (동적으로 Response를 보내주는 기능)

---

**장고에서 허용하는 데이터베이스**

- Oracle
- MySQL
- PostgreSQL
- SQLite

**데이터베이스 연결 과정**

Django - ORM - python - psycopg2 - PostgreSQL

- psycopg2 는 python이랑 PostgreSQL을 연결시켜줌

---

**운영체제 가상화**

Docker (Ubuntu)

**파이썬 환경 가상화**

virtualenv (Python

----

## Nginx uWSGI 차이

Nginx는 웹서버로 정적파일(이미지, HTML 파일)을 처리하는데 특화 되어 있습니다.

uWSGI는 웹 서버로 들어오는 다양한 프로그래밍 언어에 대해 해석할 수 있는 인터페이스 입니다.

_인터페이스_ 사용자가 기기를 쉽게 동작시키는데 도움을 주는 시스템

## Docker 란?
여러 서버에 동일한 환경을 구축하고 문제(장애)를 해결하기 쉽고 테스트 환경 구축이 쉽다

## HTTP 통신 vs SOCKET 통신
**가장 큰 차이점은 접속의 유지 여부**
http는 클라이언트의 요청이 있을 때 , 서버가 해당 페이지에 대한 자료를 전송하고 곧바로 전송을 끊는다 전송을 끊는 이유는 서버의 부하를 줄이기 위함. 서버에 많은 request를 유지시켜 서버를 공격하는 개념이 DDOS

SOCKET 클라이언트가 서버와 접속이 되면 서버나 클라이언트 둘 중 하나가 접속을 끊을때 까지 유지가 된다. 서버가 대응할 수 있는 클라이언트는 제한적. 실시간 데이터 교류가 필요한 서비스에 사용)
