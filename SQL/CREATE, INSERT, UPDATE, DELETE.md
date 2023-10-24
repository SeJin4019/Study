## CREATE
<br>

### 사용형식
```SQL
CREATE TABLE 테이블 명
(
  컬럼명 데이터타입 기본 값(생략 가능) NULL(생략 가능),
);
```

- 테이블 명, 컬럼 명 : 길이는 30byte 문자, 문자, 숫자, 특수문자(_,$,#)만 가능

- 데이터타입
  - NUMBER(4) : 4자기의 가변 길이 정수
  - NUMBER(7, 2) : 7자리의 가변 길이 정수 와 2자리의 가변길이 소수 
  - VARCHAR(10) : 10byte의 가변 길이 문자  
  * 대부분으로 영어 1byte, 한국어 2byte 라고 생각하면 편함(?)

-기본 값
  - 테이블에 값이 입력(insert) 될 때 값이 없으면 기본으로 생성되는 값
  - DEFAULT[값(문자,숫자,날짜)], 사용하지 않으면 생략 가능

- NULL 허용 여부
  - 기본 값은 NULL 허용(꼭 안넣어도 된다! 이렇게 생각), NOT NULL 선언 시 해당 컬럼은 NULL 값을 허용하지 않음(무조건 넣어줘!)
  - Primary Key로 등록된 컬럼은 무조건 데이터 값이 있어야한다!!

* 데이터 타입은 나중에 다시 정리

## INSERT
<br>

### 생성된 테이블에 새로운 자료를 삽입

### 사용형식
```SQL
INSERT INTO 테이블명[(컬럼명1, 컬럼명2)]
```

기본 사용법 1
- VALUES(값1, 값2,...) : 이 방법은 컬럼명을 생략하고 값을 넣어준 형태임 
                          컬럼명을 생략하면 테이블 생성시 기술한 순서와 모든 컬럼에 배정될 값을 VALUES 안에 넣어줘야한다

- (컬럼명1, 컬럼명2,...) :  컬럼명을 기입 후 VALUES를 이용해 데이터를 넣어주는 형태 
                            필요한 컬럼에만 값을 배정하기 위해서 사용 NOT NULL인 컬럼은 생략하지 못함(당연히 NOT NULL이 아닌건 생략이 가능함)

```SQL
INSERT INTO emp VALUES(7788, 'SCOTT', 'ANALYST', 7566, '1787-04-19', 3000, NULL, 20) -- 모든 컬럼에 배정될 값을 VALUES 안에 넣어줘야함(NULL 허용이더라도)

-- INTO 절의 컬럼 개수와 데이터타입이 VALUES 절의 컬럼 개수와 데이터 타입이 동일해야함 (이 방식을 권장함)
-- VALUES절에 테이블의 모든 컬럼이 나열되어 있다면, INTO절의 컬럼을 생략할 수 있음 바로 위에 있는 코드 구조
INSERT INTO emp (empno, ename, job, mgr, hiredate, sal, comm, deptno) VALUES(7788, 'SCOTT', 'ANALYST', 7566, '1787-04-19', 3000, NULL, 20) -- 채우고 싶은 컬럼값을 넣어주면됨 NULL 허용시 생략이 가능

```

## UPDATE
<br>

* []안에 있는건 필수 값이 아니라는것
### 특정 값을 수정하는 명령어

### 사용형식

```SQL
UPDATE 테이블명 
SET 속성이름1 = 값1, [속성이름2 = 값2...] -- 바꾸고 싶은 대상(?) 뭐 그런
[WHERE];
```

```SQL
UPDATE persons SET first_name= '길똥' WHERE person_id = 1;
-- person_id가 1인 row의 first_name을 길똥으로 바꾼다!
```

## DELETE
<br>

### 테이블에 있는 튜플(행)을 삭제하는 명령이다. 가로로 한줄을 지움

### 사용형식

```SQL
DELETE FROM 테이블이름 [WHERE 검색조건];
```

```SQL
DELETE FROM discounts WHERE discount_id = 1;
-- discounts 테이블에서 discount_id가 1인 튜플(행)을 지운다
```
