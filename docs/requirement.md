# 🏎️ 2주차 미션 - 레이싱 게임

> 부릉부릉 초간단 자동차 경주 게임을 구현하기

<br/>

## 구현할 기능

1. 사용자로부터 쉼표로 구분된 n개의 이름을 각 5자 이하로 입력받는 기능
2. 사용자가 입력한 이름이 유효한 값인지 판별하는 기능
3. 유효한 값을 입력했다면, 사용자로부터 시도 횟수를 입력받는 기능
4. 사용자가 입력한 횟수가 유효한 값인지 판별하는 기능
5. 유효한 값을 입력했다면, 전진하는 자동차와 자동차 이름을 출력하는 기능
6. 횟수 당 각 자동차들의 무작위 값이 4 이상일 경우 전진하고, 3 이하라면 멈추는 기능
7. 사용자가 입력한 시도 횟수가 지나면 최종 우승자(1명 또는 여러 명)을 출력하는 기능

<br/>

## 절차 지향 명세 (완료율 : %)

### 게임 시작

- [x] `App.js`의 `play()`로 게임이 시작된다.

### 자동차 이름을 입력받는 기능

- [ ] 게임 시작과 동시에 경주할 자동차 이름 입력을 유도하는 메시지가 출력된다.
- [ ] 사용자는 쉼표를 기준으로 n개의 자동차 이름을 입력할 수 있다.

### 자동차 이름 유효성 검사 기능

- [ ] 자동차 이름은 쉼표를 기준으로 구분하여 이름은 5자 이하만 가능하다.
- [ ] 쉼표를 기준으로 구분한 자동차 이름은 2개 이상이어야 한다.
- [ ] 자동차 이름은 중복될 수 없다.
- [ ] 위의 조건을 하나라도 만족하지 않으면 예외를 발생시키고, 게임은 즉시 종료된다.

### 시도 횟수를 입력 받는 기능

- [ ] 자동차 이름 입력 후, 시도 횟수 입력을 유도하는 메시지가 출력된다.
- [ ] 사용자는 게임 시도 횟수(몇 번의 이동을 할 것인지)를 입력할 수 있다.

### 사용자 입력 숫자 유효성 검사 기능

- [] 시도 횟수는 1 이상의 정수여야 한다.
- [] 위의 조건을 만족하지 않으면 예외를 발생시키고, 게임은 즉시 종료된다.

### 횟수에 따라 전진 또는 후진하는 기능

- [] 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- [] 전진하는 조건인 0에서 9 사이의 무작위 값을 구할 수 있다.
- [] 무작위 값이 4 이상일 경우 전진하고, 3 이하의 경우 멈춘다.
- [] 각 자동차에 이름을 부여할 수 있으며, 전진하는 자동차 출력 시 자동차 이름을 같이 출력한다.

### 횟수가 지나면 최종 우승자를 알려주는 기능
- [] 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- [] 가장 많이 이동한 자동차를 최종 우승자로 판별할 수 있다.
- [] 우승자가 여러 명일 경우 쉼표를 이용하여 구분한다.

### 게임 종료

- [] 예외 발생 시, 에러 메시지 출력과 동시에 애플리케이션이 종료된다.
- [] 최종 우승자 출력과 동시에 애플리케이션이 종료된다.

<br/>

## 객체 지향 명세 (MVC 패턴 적용)

### [Model] Car

- 자동차들의 데이터를 저장 및 객체화

### [View] inputView

- 사용자가 자동차 이름과 시도 횟수를 입력
- 사용자가 입력한 값이 유효한지 검증

### [View] outputView

- 사용자에게 결과 메시지와 결과 값을 출력
- 사용자에게 최종 우승자(들)을 출력

### [Controller] GameController

- Model과 View 사이에서 비즈니스 로직을 처리

### Utils

- 비즈니스 로직 외의 역할을 담당하는 함수

### constants

- 출력 문자열과 게임 규칙 관련 숫자들을 상수화

<br/>

## 프로그래밍 요구 사항

### 실행 환경

- [] Node.js `18.17.1 버전`에서 실행 가능한가?
- [] 프로그램 실행의 시작점인 `App.js`의 `play` 메서드로 실행시킬 수 있는가?
- [] `package.json`을 변경할 수 없고 외부 라이브러리(jQuery, Lodash)를 사용하지 않는다. 순수 Vanilla JS로만 구현했는가?
- [] 프로그램 종료 시 `process.exit()`를 호출하지 않도록 했나?
- [] 프로그램 구현이 완료되면 `ApplicationTest`의 모든 테스트가 성공하나?
- [] 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 이름을 수정하거나 이동하지 않았는가?

### 라이브러리

- [] @woowacourse/mission-utils`의 `Random` 및 `Console` API를 사용하여 구현했는가?
- [] Random 값 추출은 `Random.pickNumberInRange()`를 활용했는가?
- [] 사용자의 값을 입력 받고 출력하기 위해서는 `Console.readLineAsync`, `Console.print`를 활용했는가?

<br/>

## 리팩토링
- [] 모든 출력 메시지와 값을 상수 처리했는가?
- [] 에러 메시지를 상황에 따라 내용을 세분화 했는가?
- [] 함수는 하나의 일만 하도록 여러 메서드로 세분화 했는가?
- [] else 예약어를 쓰지 않고 early return 했는가?
- [] 불필요한 주석은 없는가?
- [] 세미콜론, 괄호 간격 등 컨벤션이 일관적인가?

<br/>

## ↪️ 다른 문서 바로가기

- [🏎️ 미션 개요](./README.md)
- [📦 컨벤션 문서](./convention.md)