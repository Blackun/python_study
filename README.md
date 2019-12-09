# 파이썬을 이용한 웹 크롤링과 스크레이핑

## 환경설정

1. Docker 설치하기
   1. 아래 링크로 접속해서 docker-desktop를 설치한다.
      * [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)
   2. 설치가 완료되면 터미널로 접속한다.
   3. 적당히 작업 프로젝트를 만든다.
      * $ cd ~ 
      * $ mkdir PythonProject
   4. Docker container 를 실행한다
      * $ docker run --name mypy -it -v /Users/\[id\]/PythonProject:/notebooks python /bin/bash

        * run : 이미지를 이용하여 컨테이너를 생성한다.
        * -name \[name\] : 지정한 이름으로 컨테이너 별명을 지정한다.
        * -it : 컨테이너 생성 후 바로 터미널로 접근한다
        * -v : 호스트와 컨테이너의 디렉토리를 연결한다\(마운트\) 

### 



