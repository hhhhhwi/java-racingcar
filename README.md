# 🚀 1단계 - 학습 테스트 실습

---

## String 클래스에 대한 학습 테스트
1. 요구사항 1
   - [x] "1,2"을 ,로 split 했을 때 1과 2로 잘 분리되는지 확인하는 학습 테스트를 구현한다.
     - 배열로 반환하는 값의 경우 assertj의 containsExactly()를 활용
   - [x] "1"을 ,로 split 했을 때 1만을 포함하는 배열이 반환되는지에 대한 학습 테스트를 구현한다.
     - 배열로 반환하는 값의 경우 assertj의 contains()를 활용
   
2. 요구사항 2
   - [x] "(1,2)" 값이 주어졌을 때 String의 substring() 메소드를 활용해 ()을 제거하고 "1,2"를 반환하도록 구현한다.

3. 요구사항 3
   - [x] "abc" 값이 주어졌을 때 String의 charAt() 메소드를 활용해 특정 위치의 문자를 가져오는 학습 테스트를 구현한다.
   - [x] String의 charAt() 메소드를 활용해 특정 위치의 문자를 가져올 때 위치 값을 벗어나면 StringIndexOutOfBoundsException이 발생하는 부분에 대한 학습 테스트를 구현한다.
   - [x] JUnit의 @DisplayName을 활용해 테스트 메소드의 의도를 드러낸다.


## Set Collection에 대한 학습 테스트
1. 요구사항 1
   - [x] Set의 size() 메소드를 활용해 Set의 크기를 확인하는 학습테스트를 구현한다.

2. 요구사항 2
   - [x] Set의 contains() 메소드를 활용해 1, 2, 3의 값이 존재하는지를 확인하는 학습테스트를 구현하려한다.
   - [x] JUnit의 ParameterizedTest를 활용해 중복 코드를 제거해 본다.

3. 요구사항 3
   - [x] 입력 값에 따라 결과 값이 다른 경우에 대한 테스트도 가능하도록 구현한다.
        - 예를 들어 1, 2, 3 값은 contains 메소드 실행결과 true, 4, 5 값을 넣으면 false 가 반환되는 테스트를 하나의 Test Case로 구현한다.
        - @CsvSource를 활용

---

# 🚀 2단계 - 문자열 덧셈 계산기

---
## 요구사항
- [x] 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환 
    - “” => 0, "1,2" => 3, "1,2,3" => 6, “1,2:3” => 6
- [x] 앞의 기본 구분자(쉼표, 콜론)외에 커스텀 구분자를 지정할 수 있다. 커스텀 구분자는 문자열 앞부분의 “//”와 “\n” 사이에 위치하는 문자를 커스텀 구분자로 사용한다. 
  - “//;\n1;2;3”과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
- [x] 문자열 계산기에 숫자 이외의 값 또는 음수를 전달하는 경우 RuntimeException 예외를 throw한다.

---

# 🚀 3단계 - 자동차 경주

---
## 요구사항
- 초간단 자동차 경주 게임을 구현한다.
- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 사용자는 몇 대의 자동차로 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 random 값을 구한 후 random 값이 4이상일 경우이다.
- 자동차의 상태를 화면에 출력한다. 어느 시점에 출력할 것인지에 대한 제약은 없다.

### 위 요구사항에 따라 3대의 자동차가 5번 움직였을 경우 프로그램을 실행한 결과
~~~
자동차 대수는 몇 대 인가요?
3
시도할 회수는 몇 회 인가요?
5

실행 결과
-
-
-

--
-
--

---
--
---

----
---
----

----
----
-----
~~~

## TODO
- [x] 입출력
  - [x] 입력
    - 자동차의 대수를 묻는다
    - 시도할 회수를 묻는다
  - [x] 출력
  - 실행 결과를 출력한다
  - 자동차 움직임 출력
- [x] 자동차
  - 움직인다
- [x] 게임
  - 게임을 시작한다

---

# 🚀 4단계 - 자동차 경주(우승자)

---
## 요구사항
- 각 자동차에 이름을 부여할 수 있다. 자동차 이름은 5자를 초과할 수 없다.
- 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분한다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한명 이상일 수 있다.

## 실행 결과
~~~
경주할 자동차 이름을 입력하세요(이름은 쉼표(,)를 기준으로 구분).
pobi,crong,honux
시도할 회수는 몇회인가요?
5

실행 결과
pobi : -
crong : -
honux : -

pobi : --
crong : -
honux : --

pobi : ---
crong : --
honux : ---

pobi : ----
crong : ---
honux : ----

pobi : -----
crong : ----
honux : -----

pobi : -----
crong : ----
honux : -----

pobi, honux가 최종 우승했습니다.
~~~

## TODO
- [ ] 자동차 별 이름 입력
  - 이름 입력 값으로 자동차의 수 대체
- [ ] 최종 우승자 구하는 객체 - Winner
  - 테스트 코드 작성
- [ ] 입출력 수정
