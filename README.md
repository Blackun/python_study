# 파이썬을 이용한 웹 크롤링과 스크레이핑

## 환경설정

1. Docker 설치하기 1. 아래 링크로 접속해서 docker-desktop를 설치한다.
   * [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)
     1. 설치가 완료되면 터미널로 접속한다.
     2. 적당히 작업 프로젝트를 만든다.
   * $ cd ~ 
   * $ mkdir PythonProject
     1. Docker container 를 실행한다
   * $ docker run --name mypy -it -v /Users/\[id\]/PythonProject:/notebooks python /bin/bash
     * run : 이미지를 이용하여 컨테이너를 생성한다.
     * -name \[name\] : 지정한 이름으로 컨테이너 별명을 지정한다.
     * -it : 컨테이너 생성 후 바로 터미널로 접근한다
     * -v : 호스트와 컨테이너의 디렉토리를 연결한다\(마운트\) 
   * 컨테이너에서 빠져나올 때
     * $ exit
   * 컨테이너를 종료할 때
     * $ docker stop mypy
   * 컨테이너 재시작
     * $ docker start mypy
   * 컨테이너 삭제
     * $ docker rm mypy
   * 컨테이너에 접속할 때
     * $ docker exec -it mypy /bin/bash
   * 그동안 변경사항을 바탕으로 컨테이너 이미지 생성하기
     * $ docker commit mypy mypy
     * 나중에 mypy 이미지로 컨테이너를 생성하면 최근 설치한 라이브러리를 모두 포함하게 된다.
2. Docker mysql 설치하기
   * [https://hub.docker.com/\_/mysql](https://hub.docker.com/_/mysql)

```bash
# mysql docker 컨테이너 생성하
$ docker run --name=jg_mysql --env="MYSQL_ROOT_PASSWORD=root_password" -p 3306:3306 -d mysql:5.6

# python 컨테이너에 mysql을 링크한다.
# 먼저 컨테이너를 중지
$ docker stop mypy
# 컨테이너 삭제
$ docker rm mypy
# 컨테이너 재실
$ docker run --name mypy --link jg_mysql -it -v /Users/[id]/PythonProject:/notebooks python /bin/bash
```

```bash
# mysql docker 컨테이너 접속하기
$ docker exec -it jg_mysql mysql -uroot -proot_password
```

