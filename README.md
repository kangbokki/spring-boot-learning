# spring-boot-learning

## Table of Contents

  - [docker](#docker)
  - [redis](#redis)
  - [etc](#etc)
  - [see also](#see-also)

## TODO
  - [ ] 퍼블리셔
  - [ ] 이벤트
  - [ ] 공통예외처리
  - [ ] 커스텀 어노테이션
  - [ ] 인터페이스 결과처리 
  - [ ] 유저 또는 상황별 로그전략(logback 활용...)

----------------------------

## docker
  - **설치**
  홈페이지에서 m1용 다운로드 후 설치  


## redis

  - **이미지 다운로드**
~~~
docker pull redis:alpine
~~~

  - **실행**  
~~~
docker run --rm --name redis-auth -p 6379:6379 --network redis-net -v /Users/kangbokki/docker/redis:/data -d redis:alpine redis-server --appendonly yes
~~~

  - **redis-cli**
~~~
docker run -it --network redis-net --rm redis:alpine redis-cli -h redis-auth
exit
~~~

## etc
  11 <a name="#etc"></a>

  - **열려 있는 포트닫기**
~~~mac
sudo lsof -i :8080
sudo kill -9 PID
~~~

## see also
  - [spring-redis](https://docs.spring.io/spring-data/data-redis/docs/current/reference/html/#reference)