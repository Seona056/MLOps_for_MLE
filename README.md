# Chapter Preview

<br>

## 목표
1. 생성된 DB 에 query 를 작성하여 테이블을 생성합니다.
2. 생성된 테이블을 확인합니다.

<br>

## 스펙 명세서
1. `pandas`, `psycopg2-binary`, `scikit-learn` 패키지를 설치합니다.
2. Python 스크립트를 이용하여 DB 에 접근합니다.
    - user : myuser
    - password : mypassword
    - host : localhost
    - port : 5432
    - database : mydatabase
3. `psycopg2` 패키지를 사용하여 `iris_data` 테이블을 생성합니다.
    - 테이블은 다음과 같은 column 들을 갖고 있어야 합니다.  

    |column|id|sepal length (cm)|sepal width (cm)|petal length (cm)|petal width (cm)|target|
    |:---:|:---:|:---:|:---:|:---:|:---:|:---:|
    |type|primary key|float|float|float|float|int|

4. `psql` 을 이용하여 생성한 테이블을 확인합니다.