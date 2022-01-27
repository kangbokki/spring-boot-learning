# spring-boot-learning

## Table of Contents

  1. [docker](#docker)
  1. [redis](#redis)
  1. [기타](#etc)
  1. [참고](#references)

----------------------------

## docker
  - **설치**
  홈페이지에서 m1용 다운로드 후 설치  


## redis

  - **이미지 다운로드**
~~~
docker pull redis:alpine
~~~

  - **네트워크 구성 및 확인**
~~~
 docker network create redis-net
 docker network ls
~~~

  - **실행**  
~~~
docker run --rm --name redis-auth -p 6379:6379 --network redis-net -v /Users/kangbokki/docker/redis:/data -d redis:alpine redis-server --appendonly yes
~~~


|옵션|설명|
|:---:|:---|
|--name|컨테이너 이름 지정|
|-p|포트설정   내부:외부|
|--network|네트워크 설정|
|-v|볼륨 지정 컴퓨터 패스:도커 패스|
|-d|백그라운드 실행|

그 외 옵션
--appendonly yes    <-- AOF방식으로 데이터 저장

  
  - **redis-cli**
~~~
docker run -it --network redis-net --rm redis:alpine redis-cli -h redis-auth
exit
~~~

|옵션|설명|
|:---:|:---|
|-it|컨테이너를 종료하지 않고 터미널 입력 (-i:interactive, -t:tty)|
|--rm|실행할 때 컨테이너 아이디가 존재하면 삭제 후 실행|

  - **컨테이너 목록 확인**
~~~
docker container ps -a
~~~

>container 생략 가능

|옵션|설명|
|:---:|:---|
|-a|전체(종료된 컨테이너 포함)|

  - **상태 확인**
~~~
docker container stats b86a159b53b9
~~~

  - **log확인**

~~~
docker container logs -t 
~~~

|옵션|설명|
|:---:|:---|
|-t|???|
|-f|실시간|

## 기타 <a name="#etc"></a>

  - **열려 있는 포트닫기**
~~~mac
sudo lsof -i :8080
sudo kill -9 PID
~~~

## 참고 <a name="#references"></a>

  - [spring-redis](https://docs.spring.io/spring-data/data-redis/docs/current/reference/html/#reference)