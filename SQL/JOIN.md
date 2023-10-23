# JOIN

### JOIN이란?
- 두 개의 테이블을 서로 묶어서 하나의 결과를 만들어 내는 것을 말한다.

### JOIN 종류
- INNER JOIN(내부 조인)은 두 테이블을 조인할 때, 두 테이블에 모두 지정한 열의 데이터가 있어야 한다.
- OUTER JOIN(외부 조인)은 두 테이블을 조인할 때, 1개의 테이블에만 데이터가 있어도 결과가 나온다.
- CROSS JOIN(상호 조인)은 한쪽 테이블의 모든 행과 다른 쪽 테이블의 모든 행을 조인하는 기능이다.
- SELF JOIN(자체 조인)은 자신이 자신과 조인한다는 의미로, 1개의 테이블을 사용

<br>
### INNER JOIN(교집합)
```SQL
SELECT <열 목록>
FROM <첫 번째 테이블>
  INNER JOIN <두 번째 테이블> -- JOIN으로 써도 INNER JOIN으로 인식
  ON <조인 조건>
[WHERE 검색 조건]
```

```SQL
-- Oracle JOIN
SELECT a,b,c,d,e,f,k (A,B 테이블에 있는 칼럼 가져올 수 있음)
FROM A, B
WHERE A.a = B.a; (A테이블의 a와 B테이블의 a가 같 떄)
```

```SQL
-- ANSI JOIN(표준화)
SELECT a,b,c,d,e,f,k (A,B 테이블에 있는 칼럼 가져올 수 있음)
FROM A JOIN B
ON A.a = B.a;
```
<br>
