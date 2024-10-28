# javascript-racingcar-precourse

## 기능 요구 사항

초간단 자동차 경주 게임을 구현한다.

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
- 사용자가 잘못된 값을 입력할 경우 "[ERROR]"로 시작하는 메시지와 함께 Error를 발생시킨 후 애플리케이션은 종료되어야 한다.

## 입출력 요구 사항

### 입력

- 경주할 자동차 이름(이름은 쉼표(,) 기준으로 구분)

```javascript
pobi,woni,jun
```

- 시도할 횟수

```javascript
5
```

### 출력

- 차수별 실행 결과

```javascript
pobi : --
woni : ----
jun : ---
```

- 단독 우승자 안내 문구

```javascript
최종 우승자 : pobi
```

- 공동 우승자 안내 문구

```javascript
최종 우승자 : pobi, jun
```

### 실행 결과 예시

```javascript
경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
pobi,woni,jun
시도할 횟수는 몇 회인가요?
5

실행 결과
pobi : -
woni : 
jun : -

pobi : --
woni : -
jun : --

pobi : ---
woni : --
jun : ---

pobi : ----
woni : ---
jun : ----

pobi : -----
woni : ----
jun : -----

최종 우승자 : pobi, jun
```

## 요구 사항 분석

- 자동차의 이름은 5글자 이하이며, 쉼표(,)를 통해 구분한다.
- 몇 번의 이동이 있을지 입력받아야 하며, 각각의 자동차는 각 시도마다 0~9사이의 무작위 값을 구한 후 4 이상일 경우 전진한다.
- 잘못된 값이 입력될 경우 "[ERROR]{메시지}"를 출력하면서 Error를 발생킨 후 종료되어야 한다.
- 정상적인 값이 입력될 경우 자동차 경주 게임을 완료한 후 우승자를 출력하며, 우승자는 한명 이상일 수 있다.
- 우승자가 여러명일 경우 쉼표(,)를 통해 구분한다.

## 구현할 기능 목록

- 경주할 자동차의 이름을 입력받는 기능
- 입력받은 자동차의 이름을 쉼표(,)를 통해 분리하는 기능
- 시도할 횟수를 입력받는 기능
- 무작위 값을 통해 자동차가 전진할지 판별하는 기능
- 각 차수별로 실행결과를 출력하는 기능
- 우승자를 판별하는 기능
- 우승자를 출력하는 기능

## 프로그래밍 요구 사항

- indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- 3항 연산자를 쓰지 않는다.
- 함수(또는 메서드)가 한 가지 일만 하도록 최대한 작게 만들어라.
- Jest를 이용하여 정리한 기능 목록이 정상적으로 작동하는지 테스트 코드로 확인한다.

## 기능 요구 사항에 기재되지 않은 내용에 대한 판단

- 차량이 1대만 있을 경우  
  차량이 1대만 있을 경우에는 해당 차량이 움직이든 안움직이든 무조건 우승자가 된다.  
  기능 요구사항에는 n대의 자동차가 입력될 수 있다고 되어있으니 1대인 경우도 다른 경우와 동일하게 작동한다.
- 모든 차량이 움직이지 않았을 경우  
  n대의 차량이 모두 움직이지 않은 경우 모든 차량은 출발선에 있다.  
  하지만 우승 조건이 가장 많이 움직인 차량이기 때문에 움직이지 않은 경우는 0으로 카운트하고 만약 가장 많이 움직인 경우가 0이라도 정상적으로 우승자로 출력한다.

## 개발하면서 마주친 예외사항

- 차량 이름이 중복이 되는 경우
  - 중복이 될 경우 에러를 발생시키고 종료되도록 개발
- 차량 이름이 없는 경우
  - 차량 이름의 길이가 0인것이 하나라도 있을 경우 에러를 발생시키고 종료되도록 개발
