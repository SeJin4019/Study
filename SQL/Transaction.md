# DB Transaction
<br>

### Transaction 이란?
- 데이터베이스의 상태를 변화시키기 위해 수행하는 작업 단위 
  - 상태를 변화시킨다는 것 → SQL 질의어를 통해 DB에 접근(DML 데이터 조작어)
    - SELECT
    - INSERT
    - DELETE
    - UPDATE

  - 작업 단위 → 많은 SQL 명령문들을 사람이 정하는 기준에 따라 정하는 것
    ```
      예시) 사용자 A가 사용자 B에게 만원을 송금한다.

      * 이때 DB 작업
      - 1. 사용자 A의 계좌에서 만원을 차감한다 : UPDATE 문을 사용해 사용자 A의 잔고를 변경
      - 2. 사용자 B의 계좌에 만원을 추가한다 : UPDATE 문을 사용해 사용자 B의 잔고를 변경

      현재 작업 단위 : 출금 UPDATE문 + 입금 UPDATE문
      → 이를 통틀어 하나의 트랜잭션이라고 한다.
      - 위 두 쿼리문 모두 성공적으로 완료되어야만 "하나의 작업(트랜잭션)"이 완료되는 것이다. `Commit`
      - 작업 단위에 속하는 쿼리 중 하나라도 실패하면 모든 쿼리문을 취소하고 이전 상태로 돌려놓아야한다. `Rollback`

    ```

  - 하나의 트랜잭션 설계를 잘 만드는 것이 데이터를 다룰 때 많은 이점을 가져다준다

<br>

### 트랜잭션 특징
- 원자성
  - 트랜잭션이 DB에 모두 반영되거나, 혹은 전혀 반영되지 않아야 된다.
 
- 일관성
  - 트랜잭션의 작업 처리 결과는 항상 일관성 있어야 한다.
 
- 독립성
  - 둘 이상의 트랜잭션이 동시에 병행 실행되고 있을 때, 어떤 트랜잭션도 다른 트랜잭션 연산에 끼어들 수 없다.

- 지속성
  - 트랜잭션이 성공적으로 완료되었으면, 결과는 영구적으로 반영되어야 한다.


### Commit
- 하나의 트랜잭션이 성공적으로 끝났고, DB가 일관성있는 상태일 때 이를 알려주기 위해 사용하는 연산

### Rollback
- 하나의 트랜잭션 처리가 비정상적으로 종료되어 트랜잭션 원자성이 깨진 경우
- transaction이 정상적으로 종료되지 않았을 때, <br>
   last consistent state (예) Transaction의 시작 상태로 roll back 할 수 있음

<br>

### Transaction 관리를 위한 DBMS의 전략
1. DBMS의 구조
   - 크게 2가지 : Query Processor(질의 처리기), Storage System(저장 시스템)
   - 입출력 단위 : 고정 길이의 page 단위로 disk에 읽거나 쓴다.
   - 저장 공간 : 비휘발성 저장 장치인 disk에 저장, 일부분을 Main Memory에 저장
![DBMS 구조](https://github.com/SeJin4019/Study/assets/121854655/7a9550da-10eb-454f-9ba6-fcbf1e43b2f4)
  
2. Page Buffer Manager or Buffer Manager
   - DBMS의 Storage System에 속하는 모듈 중 하나로, Main Memory에 유지하는 페이지를 관리하는 모듈
   - Buffer 관리 정책에 따라, UNDO 복구와 REDO 복구가 요구되거나 그렇지 않게 되므로, transaction 관리에 <br>
     매우 중요한 결정을 가져온다

3. UNDO
   - 필요한 이유 : 수정된 Page들이 Buffer 교체 알고리즘에 따라서 디스크에 출력 될 수 있음<br>
     Buffer 교체는 transaction과는 무관하게 buffer의 상태에 따라서, 결정됨이로 인해,<br>
     정상적으로 종료되지 않은 transaction이 변경한 page들은 원상 복구 되어야하는데, undo라고 함
     
4. REDO
   - 이미 commit한 transaction의 수정을 재반영하는 복구 작업 Buffer 관리 정책에 영향을 받음
  
  [참고사항]
  - [링크](https://gyoogle.dev/blog/computer-science/data-base/Transaction.html)
