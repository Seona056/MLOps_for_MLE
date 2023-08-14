# 01-4) Data Insertion

<br>

## Chapter Preview

<br>

### 목표
1. 생성한 테이블에 iris 데이터 한 줄을 삽입합니다.
2. 삽입한 데이터를 확인합니다.

<br>

### 스펙 명세서
1. Python 스크립트를 이용하여 DB 에 접속합니다.
    - *user* : `myuser`
    - *password* : `mypassword`
    - *host* : `localhost`
    - *port* : `5432`
    - *database* : `mydatabase`
2. `psycopg2` 패키지를 이용하여 생성된 `iris_data` 테이블에 데이터 row 1개를 삽입합니다.
3. `psql` 을 이용하여 삽입한 데이터를 확인합니다.