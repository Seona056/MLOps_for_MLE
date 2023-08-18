# 6) Data Generator on Docker Compose

<br>

## Chapter Preview

<br>

### 목표
1. DB 컨테이너와 Data Generator 컨테이너를 함께 띄우기 위한 Docker Compose 파일을 작성합니다.
2. DB 안에 데이터가 계속해서 삽입되고 있는지 확인합니다.


### 스펙 명세서
1. Docker Compose 파일을 작성합니다.

    - Postgres Server
    - Service name : `postgres-server`
    - Image : `postgres:14.0`
    - Container name : `postgres-server`
    - Environment
        - POSTGRES_USER : `myuser`
        - POSTGRES_PASSWORD : `mypassword`
        - POSTGRES_DB : `mydatabase`
    - Port forwarding : `5432:5432`
    - Data Generator
        - Service name : `data-generator`
        - Image : `Dockerfile`
        - Container name : `data-generator`
        - Command : `["postgres-server"]`

> INFO
Postgres Server 서비스와 Data Generator 서비스를 띄울 때 어떤 서비스가 먼저 생성되어야 하는지 생각해보고, 그 기능을 Compose 파일에 추가합니다.

2. Docker Compose 파일을 실행합니다.

3. `psql` 을 이용하여 DB 에 데이터가 계속해서 쌓이고 있는지 확인합니다.
    - Local 에서 확인합니다.
    - Data Generator server 에서 확인합니다.