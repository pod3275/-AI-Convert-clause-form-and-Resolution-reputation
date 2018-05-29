# Convert-clause-form-and-Resolution-reputation
 - 2017년 1학기 성균관대학교 이지형 교수님 인공지능 수업 2번째 과제
 - 주어진 logic operation을 clausal form으로 변환 및 resolution reputation을 수행하는 문제.

## 1. Problem
 - 모든 명제(propositions)는 알파벳 소문자로 되어있다고 가정한다.
 - Logic operation인 ‘negation’, ‘and’, ‘or’, ‘implication’ 그리고 ‘if and if only’는 각각 ‘~’, ‘*’, ‘+’, ‘>’ 그리고 ‘=’로 표시한다.
 - logic 표현에 괄호(parenthesis)가 사용된다.
 - 모든 logic expression에는 문법적 에러(grammatical error)가 없다고 가정한다.
 - 예시)
 
   ![image](https://user-images.githubusercontent.com/26705935/40596223-7a983fba-6274-11e8-9cec-afaf4a756188.png)
 
### (1) Convert to clausal form
 - 주어진 logic 표현을 clausal form으로 변환하여 출력하는 프로그램을 작성하라.
 - 단순함을 위해, 명제의 부정(negation)을 알파벳 대문자로 표시하고, clasual form은 'or'를 생략하여 표시한다.
 - 예시)
 > input : ~(a*b)    ||    output : AB (= ~a+b)
 
 > input : ~(a+~b)    ||    output : A b (two clauses)
 
 > input : (a>b)+~(c*~d)    ||    output : AbCd
 
### (2) Resolution reputation for predication logic
 - 주어진 predication logic에 대해 resolution reputation을 수행하는 프로그램을 작성하라.
 - 먼저, 프로그램은 goal을 부정하고, 모든 logic 표현을 clausal form으로 변환한다.
 - 추론 중의 모든 과정은 출력되어야 한다.
 - 최종 output은 "The goal is TRUE" 또는 "Unable to prove"이다.
 - 추론은 다음과 같은 breadth first 전략을 통해 이루어진다.
 
   ![image](https://user-images.githubusercontent.com/26705935/40596369-4980fff6-6275-11e8-8769-dc92e5011282.png)
 
 - 예시)
 
   ![image](https://user-images.githubusercontent.com/26705935/40596385-59b4392e-6275-11e8-9457-aadee4d616f8.png)
 
## 2. Environment
 - language : C++
 - IDE : Microsoft Visual studio 2017
 
## 3. Result
(1) Convert to clausal form
 - input : ~(a*b)    ||    output : AB (= ~a+b)
 
 ![image](https://user-images.githubusercontent.com/26705935/40596519-66677608-6276-11e8-808c-8b1839651af1.png)
 
 - input : ~(a+~b)    ||    output : A b (two clauses)
 
 ![image](https://user-images.githubusercontent.com/26705935/40596544-88659a46-6276-11e8-806d-30c13c0cf00d.png)
 
 - input : (a>b)+~(c*~d)    ||    output : AbCd
 
 ![image](https://user-images.githubusercontent.com/26705935/40596555-a1763932-6276-11e8-9c60-b14777fa1f05.png)
 
(2) Resolution reputation for predication logic
 - 예시)에 대한 결과
 
   ![image](https://user-images.githubusercontent.com/26705935/40596571-c9f37b9a-6276-11e8-9436-6d171cdc55ca.png)
 
 - "The goal is TRUE" 결과
 
   ![image](https://user-images.githubusercontent.com/26705935/40596602-f42b5900-6276-11e8-86e2-68bff87acfe6.png)
 
 ## 4. Future work
 - 전체 코드가 600줄이 넘을 정도로 매우 길다. 코드를 정리하고, c++의 객체(클래스) 특성을 이용하여 간결화할 필요가 있다.
 > 무분별한 for문과 while문을 빼자.
