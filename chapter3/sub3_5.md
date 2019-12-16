# 3.5 데이터베이스에 저장하기

* 데이터베이스에 저장하면 단순한 파일로 저장하는 것과 다르게 여러 개의 프로세스에서 동시에 읽고 쓰는 성능이 높다
* 데이터의 중복을 방지하기도 쉽다
* 데이터를 분석에 활용할 때 조건에 맞게 일부 데이터만을 추출하는 것도 쉽다.



* 관계형 데이터베이스
  * 관계모델과 트랜잭션을 기반으로 데이터의 정합성을 보
  * 표준화된 SQL 구문을 사용해 유연하게 데이터를 관
  * 대표 : MySQL
* NoSQL
  * 관계형 DB에 비해 데이터 정합성은 약함
  * 대신 확장성과 읽고 쓰기 성능이 굉장히 높음
  * 대표 : MongoDB

## MySQL에 데이터 저장하기

```bash
# 설치 후 실행 까지 완
$ docker run --name=jg_mysql --env="MYSQL_ROOT_PASSWORD=root_password" -p 3306:3306 -d mysql:latest

# mysql docker 컨테이너 접속하기
$ docker exec -it jg_mysql mysql -uroot -proot_password

mysql> create database scraping default character set utf8mb4;
Query OK, 1 row affected (0.14 sec)

# 최신 mysql에서 암호화 방식이 기 caching_sha2_password 로 바뀌었다.
# 이전 버전 암호화 방식으로 바꿔준다.
mysql> create user `scraper`@`%` IDENTIFIED WITH mysql_native_password BY 'password';
Query OK, 0 rows affected (0.10 sec)


mysql> grant all on scraping.* to scraper;
Query OK, 0 rows affected (0.03 sec)
```

## 파이썬에서 MySql에 접속하기

```bash
# 사용하기 쉽고 성능도 좋은 mysqlclient 설
$ pip install mysqlclient


```

