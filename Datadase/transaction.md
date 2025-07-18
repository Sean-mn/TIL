# 트랜잭션(Transaction)이란?

**트랜잭션(Transaction)** 이란 데이터베이스에서 하나의 작업 단위를 말한다. <br>
즉, 논리적으로 하나로 묶여야 하는 일련의 연산들을 의미한다.

>예를 들어, 은행 계좌 이체는 <br>
A 계좌에서 돈을 출금하고 B 계좌에 입금하는 두 개의 작업이지만, <br>
전체가 함께 성공하거나 함께 실패해야 올바른 결과다. <br>
이 두 작업을 하나의 트랜잭션으로 처리하는 것이다. <br>

<br>

##  트랜잭션의 4가지 성질 (ACID)

| 성질                    | 설명                              |
| --------------------- | ------------------------------- |
| **원자성 (Atomicity)**   | 모두 성공하거나 모두 실패해야 함              |
| **일관성 (Consistency)** | 트랜잭션 전후의 DB 상태가 일관되어야 함         |
| **격리성 (Isolation)**   | 동시에 실행되는 트랜잭션끼리 서로 영향을 주지 않아야 함 |
| **지속성 (Durability)**  | 성공한 트랜잭션 결과는 영구적으로 반영되어야 함      |
