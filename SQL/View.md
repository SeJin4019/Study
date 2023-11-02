# View
- 'View'는 SELECT FROM으로 조회한 결과를 데이터베이스에 테이블 형식으로 저장한 객체
- 매번 SQL 쿼리로 자주 쓰는 조회 결과를 불러오지 않더라도 <br>
  뷰를 한번 저장하면 해당 조회 결과를 마치 테이블처럼 간편하게 축약하여 하거나 편집
- 뷰를 편집하더라도 원본 데이터에 영향을 미치지 않고, 원본 데이터의 컬럼 이름과 같은 정보를 보호

### CREATE VIEW
- 오라클SQL에서 '뷰(view)'를 생성해 주는 명령어
```SQL
create view 뷰이름A as (
SELECT FROM 구문);
```

### CREATE OR REPLACE VIEW
- 오라클SQL에서 '뷰(view)'를 생성해 주는 명령어<br>
  이미 같은 이름의 뷰를 생성할 경우 존재하고 있는 뷰를 갱신(덮어쓰기)하기도 합니다.

```SQL
create or replace view 뷰이름A as (
SELECT FROM 구문);
```

### WITH READ ONLY 
- '읽기 전용'으로 생성 읽기 전용 모드에서는 DML 작업이 불가능 

```SQL
-- 읽기 전용 생성
create or replace view 뷰이름A as (
SELECT FROM 구문)
with read only;
```

```SQL
-- 읽기 전용인지 여부
select read_only 
from user_views
where view_name='뷰이름A';
```

### 기본식 : 서브쿼리 조건 검사
- 서브쿼리인 SELECT FROM 구문에 WHERE 조건절이 있을 경우, WHERE 조건을 만족하지 않는 데이터가<br>
뷰 A에 생성되는 것을 방지

### 기본식 : 뷰 조회
```SQL
select * from 뷰이름A;
```

[참고]
[Haven 블로그 뷰생성하기](https://m.blog.naver.com/regenesis90/222228928522)
