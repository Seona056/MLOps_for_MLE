# 5) Data Generator on Docker

<br>

## Chapter Preview

<br>

### 목표
1. 앞서 작성했던 코드를 Docker 컨테이너 안에서 실행하기 위해 Dockerfile 을 작성합니다.
2. Docker 컨테이너 간의 네트워크를 연결하여 DB 에 데이터를 계속해서 삽입합니다.
3. DB 안에 데이터가 계속해서 삽입되고 있는지 확인합니다.

### 스펙 명세서
1. `4) Data Insertion Loop` 챕터에서 작성한 스크립트를 build 할 수 있는 Dockerfile 을 작성합니다.
    - Base image 는 `amd64/python:3.9-slim` 을 사용합니다.
    - 컨테이너에서 `psql` 을 이용하여 DB 에 접속할 수 있도록 `postgresql-client` 를 설치합니다.
    - 컨테이너에서 코드가 실행될 수 있도록 `scikit-learn`, `pandas`, `psycopg2-binary` 을 설치합니다.
    - `4) Data Insertion Loop` 챕터에서 작성한 스크립트를 복사합니다.
    - `ENTRYPOINT` 와 `CMD` 를 이용하여 스크립트를 실행합니다.

2. Dockerfile 을 이용하여 이미지를 build 하고 실행합니다.

3. Docker Network 를 통해 컨테이너 간의 네트워크를 연결하여 DB 에 데이터를 계속해서 삽입합니다.
    - `docker network create` 명령어를 이용하여 `my-network` 라는 네트워크를 생성합니다.
    - `docker network connect` 명령어를 이용하여 생성한 `my-network` 에 postgres server 를 연결합니다.
    - Build 된 이미지를 다시 실행합니다. 이때 `--network` 옵션을 이용하여 `my-network` 네트워크에 연결합니다.

4. `psql` 을 이용하여 DB 에 데이터가 계속해서 쌓이고 있는지 확인합니다.