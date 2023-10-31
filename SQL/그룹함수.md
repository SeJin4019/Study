# 그룹함수(Group Functions)
### 그룹함수란 
- 여러 행 또는 테이블 전체의 행에 대해 함수가 적용되어 하나의 결과값을 가져오는 함수를 말합니다
- GROUP BY절을 이용하여 그룹 당 하나의 결과가 주어지도록 그룹화 할 수 있음
- HAVING절을 사용하여 그룹 함수를 가지고 조건비교를 할 수 있음
- COUNT(*)를 제외한 모든 그룹함수는 NULL값을 고려하지 않음
- MIN,MAX 그룹함수는 모든 자료형에 대해서 사용할 수 있음

### 그룹함수의 종류
- COUNT(검색된 행의 수를 반환), MAX(지정된 컬럼에서 가장 큰 값을 반환), MIN(컬럼중의 최소값을 반환), AVG(평균값), SUM(컬럼의 합을 반환), STDDEV(표준편차를 반환)

### Group By절과 Having절 
- Group By
  - 특정한 컬럼의 데이터 들을 다른 데이터들과 비교해 유일한 값에 따라 무리를 짓습니다.
  - Group BY절을 사용하여 한 테이블의 행들을 원하는 그룹으로 나눕니다.
  - Column명을 Group함수와 SELECT절에 사용하고자 하는 경우 GROUP BY뒤에 Column명을 추가

- HAVING 절
  - WHERE절에 GROUP Function을 사용할 수 없음
  - HAVING절은 GROUP 함수를 가지고 조건비교를 할 때 사용
  - WHERE -> GROUP BY -> HAVING -> ORDER BY순으로 쿼리문이 와야함  
