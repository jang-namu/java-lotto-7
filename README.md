# java-lotto-precourse

- 로또: 1-45 수 중 중복되지 않는 6개의 숫자
- 당첨번호 추첨 시, 중복되지 않는 숫자 6개와 보너스 번호 1개를 뽑음
    - 1등: 6개 번호 일치 / 2,000,000,000원
    - 2등: 5개 번호 + 보너스 번호 일치 / 30,000,000원
    - 3등: 5개 번호 일치 / 1,500,000원
    - 4등: 4개 번호 일치 / 50,000원
    - 5등: 3개 번호 일치 / 5,000원
- 입력받은 금액만큼 로또 발행 (1장 = 1000원)
- (시스템쪽)당첨번호와 보너스 번호는 입력
  - 사용자는 자동만?
- 당첨 내역 및 수익률 출력 후 종료
- IllegalArgumentException 처리 -> "[ERROR]"로 시작하는 에러 메시지를 출력 후 그 부분부터 입력을 다시 받는다.

입력
- 로또 구입 금액 -> 1000원 단위 -> if (입력 % 1000 != 0) -> IllegalArgumentException 예외처리 -> 다시 입력
- 당첨번호 -> 1-45 사이 중복되지 않는 숫자 6개(delimiter=',') -> ex)1,2,3,4,5,6
- 보너스 번호 -> 1-45 사이 당첨번호와 중복되지 않는 숫자 1개


출력
- 로또 발행 수량 및 번호, 로또 번호는 오름차순 정렬
    ```
    8개를 구매했습니다.
    [8, 21, 23, 41, 42, 43]
    [3, 5, 11, 16, 32, 38]
    [7, 11, 16, 35, 36, 44]
    [1, 8, 11, 31, 41, 42]
    [13, 14, 16, 38, 42, 45]
    [7, 11, 30, 40, 42, 43]
    [2, 13, 22, 32, 38, 45]
    [1, 3, 5, 14, 22, 45]
    ```
- 당첨 내역
  ```
  3개 일치 (5,000원) - 1개
  4개 일치 (50,000원) - 0개
  5개 일치 (1,500,000원) - 0개
  5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
  6개 일치 (2,000,000,000원) - 0개
  ```
- 수익률 -> 소수점 둘째 자리에서 반올림
    ```
    총 수익률은 62.5%입니다.
    ```
- 예외 -> 에러 문구 출력. 단, 에러 문구는 "[ERROR]"로 시작해야 한다.
    ```
    [ERROR] 로또 번호는 1부터 45 사이의 숫자여야 합니다.
    ```

실행 결과 예시
```
구입금액을 입력해 주세요.
8000

8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]

당첨 번호를 입력해 주세요.
1,2,3,4,5,6

보너스 번호를 입력해 주세요.
7

당첨 통계
---
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
총 수익률은 62.5%입니다.
```

## 기능 목록
- [x] 로또 구입 금액을 입력받는다.
- [x] 발행한 로또 수량을 출력한다.
- [x] 발행한 로또 번호를 출력한다.
- [x] (구입 금액 / 1000)개의 로또 뭉치를 생성한다.
  - [x] 로또 하나를 생성한다.
  - [x] 로또 번호는 오름차순으로 정렬한다.

- [x] 당첨번호를 입력받는다.
- [ ] 보너스 번호를 입력받는다.

- [ ] 당첨 통계를 출력한다.
  - [ ] 당첨 내역을 출력한다.
    - [ ] 당첨인지 계산한다.(1등, 2등, ..., 꽝)
  - [ ] 수익률을 출력한다.
    - [ ] 수익률을 계산한다.
      - [ ] 전체 당첨 보상금을 계산한다.



## 예외상황
> 에러 문구 출력. 단, 에러 문구는 "[ERROR]"로 시작해야 한다.  
ex) [ERROR] 로또 번호는 1부터 45 사이의 숫자여야 합니다.
- [x] 입력받은 구입 금액의 파싱이 불가능하면 예외를 일으킨다.
- [x] 로또 구입 금액이 음수이면 예외를 일으킨다.
- [x] 로또 구입 금액이 1000원으로 나누어 떨어지지 않으면 예외를 일으킨다.

- [x] 입력받은 당첨번호 파싱이 불가능하면 예외를 일으킨다.
- [x] 당첨 입력 번호가 6개가 아니면 예외를 일으킨다.
- [x] 당첨 입력 번호가 1-45의 숫자가 아니면 예외를 일으킨다.
- [x] 당첨번호 숫자가 중복되면 예외를 일으킨다.

- [ ] 입력받은 보너스 번호의 파싱이 불가능하면 예외를 일으킨다.
- [ ] 보너스 번호가 1개가 아니면 예외를 일으킨다.
- [ ] 보너스 번호가 1-45의 숫자가 아니면 예외를 일으킨다.
- [ ] 보너스 번호가 당첨번호와 중복되면 예외를 일으킨다.



## 고민
1. InputView에서 WinningLotto를 만들어서 반환해도 될까?  
   테스트는 어떻게 해야될까?