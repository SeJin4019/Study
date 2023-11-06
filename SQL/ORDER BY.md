# ORDER BY
- 정렬방법에는 오름차순(ascending sort), 내림차순(descending) 두가지가 있다
- 오름차순 작은 값부터 큰 값으로 정렬, 내림차순 큰 값부터 작은 값으로
```SQL
SELECT 컬럼명
  FROM 테이블명
 WHERE 조건식
 GROUP BY 컬럼명
 ORDER BY 컬럼명1 [ASC|DESC], 컬럼명2 [ASC|DESC], 컬럼명3 [ASC|DESC] ...
```
- 오름차순은 정렬 기본값 ASC 생략 가능
- DESC를 붙이면 큰 값부터 순서대로 내림차순으로 정렬

### 사용법
```SQL
 ORDER BY job, sal DESC -- 이런식으로도 가능 두개의 컬럼 내림차순

CASE WHEN sal > 2000 THEN '1등급'
            WHEN sal > 1000 THEN '2등급'
            ELSE '3등급'
       END AS sal_grade
  FROM emp
 WHERE deptno = 30
 ORDER BY sal_grade, sal DESC -- 별칭으로 사용도 가능

ORDER BY 5, 4 DESC --컬럼 순번으로 정렬 가독성이 떨어져서 파악이 힘들다.

 GROUP BY job
 ORDER BY job, SUM(sal), MAX(comm) -- GROUP BY 절을 사용할 경우 ORDER BY 절에 그룹 함수(COUNT, SUM, MAX, MIN...)를 사용할 수 있다.
```
