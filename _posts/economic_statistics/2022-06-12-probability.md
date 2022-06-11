---
title: "SNU경제통계학-Week5.확률이란"

date: 2022-06-12

categories: statistics economic-statistics


---

K-MOOC 에서 제공하는 경제통계학 강의를 들으며 정리한 내용입니다. 활용한 이미지들은 출처표기가 따로 없는 경우에는 모두 해당 강의의 자료에서 가져온 것임을 참고해주세요. <br/>
[경제통계학 강의페이지](http://www.kmooc.kr/courses/course-v1:SNUk+SNU212.204.2k+2021_T2/course/)


# Week5. 확률이란

## 확률을 보는 2가지 견해

- **도수이론(frequentist view)**: 상대도수의 극한치. 확률은 한 시행을 동일한 조건 하에서 독립적으로 반복할 때 그 사건이 일어날 것으로 예측되는 횟수의 전체 시행횟수에 대한 백분율
- **주관적 견해(subjective view)**: 사건에 대한 주관적 확신의 정도(믿음의 정도)가 확률이다.



## 확률의 특성

- 확률은 0%부터 100% 사이의 값을 가진다.
- 어떤 사건 A가 일어날 확률이 P(A)이면 그 사건이 일어나지 않을 확률은 1-P(A)이다.
- **P(A^C) = 1 - P(A)** : 여기에서 A의 여사건은 "anything but A"를 의미



## 확률 추출 방법

- 복원추출: 한번 뽑은 표본을 모집단에 **다시 넣고** 다른 표본을 추출
  - 다시 정의: 크기가 n인 표본을 뽑기 위해 n개의 원소를 하나씩 뽑는다. 원소를 하나 뽑을 때마다 복원하고 다음 원소를 뽑는다. n개의 원소를 다 뽑으면 모집단에 돌려놓는다.
- 비복원추출: 한번 뽑은 표본을 모집단에 **다시 넣지 않고** 다른 표본을 추출
  - 다시 정의: 크기가 n인 표본을 뽑기 위해 n개의 원소를 하나씩 뽑는다. 원소를 하나 뽑을 때마다 복원하지 않고 다음 원소를 뽑는다. n개의 원소를 다 뽑으면 모집단에 돌려놓는다.

출처: [복원추출과 비복원추출에 대한 오해](https://hsm-edu.tistory.com/980)



## 경우의 수

![numofcase](https://imgur.com/4QlDxCs.png)

- 주사위를 3번 던져서 3개의 값을 가지는 것이 동일하다고 해도, 나올 수 있는 숫자의 조합(combination)별 구성방법의 수를 고려해야 **경우의 수**를 구하는 것이라 할 수 있다.



## 벤 다이어그램과 배반

- 벤 다이어그램의 예시: 하나의 직사각형과 그 안에 든 원을 이용하여 한 개 또는 그 이상의 사건을 나타내는 그림
- event = subset of S

![venndiagram](https://imgur.com/IaFOOFO.png)

- 상호배반: 한 사건이 발생할 때 다른 사건이 함께 발생할 수 없는 경우 두 사건은 '상호배반(mutually exclusive)' 또는 단순히 '배반' 관계에 있다고 한다.
- 배반인 경우(왼쪽 그림) -> <img src="https://latex.codecogs.com/gif.latex?\text{ P } {(A\cap B)} = 0 " />
- 배반이 아닌 경우(오른쪽 그림) -> <img src="https://latex.codecogs.com/gif.latex?\text { A } \cup \text { B } = \text {A or B} " />



## 덧셈법칙

-  <img src="https://latex.codecogs.com/gif.latex?\text{ P(A or B) } " />: 두 사건 중 적어도 하나의 사건이 일어날 확률
-  <img src="https://latex.codecogs.com/gif.latex?\text{ P(A and B) } " /> : 두 사건이 함께 일어날 확률
-  <img src="https://latex.codecogs.com/gif.latex?\text{ P(A or B) = P(A) + P(B) - P(A and B) } " />



## 조건부 확률

- 반대 되는 것으로 **주변확률**이 있다.
- 정보가 바로 **조건**이다!
- 관련 곱셈법칙
  - <img src="https://latex.codecogs.com/gif.latex?\text{ P(A and B) } " /> : 결합확률(joint probability)
    - 두 사건이 함께 일어날 확률
    - = <img src="https://latex.codecogs.com/gif.latex?\text{ P(A)}\cdot P(B\mid A) =  \text{ P(B)}\cdot P(A\mid B) " /> 
  - <img src="https://latex.codecogs.com/gif.latex?\text{ P(A}\mid {B)} " /> : 조건부확률(conditional probability)
    - 사건 B가 주어진 조건(given B) 하에서 사건 A가 일어날 확률
  - <img src="https://latex.codecogs.com/gif.latex?\text{ P(A), P(B) } " /> : 주변확률(marginal probability)
    - 비조건부 확률
    - 개별 사건의 확률이지만, 결합사건(joint event)들의 합으로 표시될 수 있는 확률을 의미 (출처: [간토끼 DataMining Lab](https://datalabbit.tistory.com/17))

![conditional probability](https://i.ibb.co/HBnpssW/image.png)



## 독립

- 하나의 사건이 일어나느냐 마느냐와 **상관없이** 다른 사건이 일어날 확률이 변하지 않으면, 두 사건의 관계가 **독립(independent)**이라고 한다. 그렇지 않은 경우 두 사건의 관계가 **종속(dependent)**이라고 한다.
  - 복원 추출일 경우에는 매번의 추출이 독립이고, 비복월추출일 경우에는 종속이다.
- 두 사건이 서로 독립일 때, 두 사건이 모두 일어날 확률은 각각의 비조건부 확률을 곱하여 얻는다. 이를 **좁은 의미의 곱셈법칙**이라고 부른다.
  - 두 사건 A와 B가 독립이면, <img src="https://latex.codecogs.com/gif.latex?\text{ P(A and B) } = \text {P(A)P(B)} " /> 



## 배반과 독립, 덧셈과 곱셈

- 상호배반: 하나의 사건이 발생하면 다른 사건이 발생할 수 없는 경우 (서로 동시에 일어날 수 없음)
- 상호독립: 하나의 사건이 발생하든 말든 다른 사건이 일어날 확률이 변하지 않는 경우 (서로 영향을 미치지 않음)
- 상호배반인 두 사건은 서로 종속: 두 사건 A, B가 상호배반이면 사건 A가 일어나는 경우 사건 B가 일어날 확률은 0으로 변경된다. 즉, **상호배반이면 독립일 수 없다.**
- 덧셈법칙
  - 두 사건 중 적어도 하나의 사건이 일어날 확률과 관련
  - 좁은 의미의 덧셈법칙은 상호배반일 경우만 가능
  - 배반이 아닌 경우 중복 계산되는 부분을 제거해야 한다.
- 곱셈법칙
  - 두 사건이 함께 일어날 확률과 관련
  - 좁은 의미의 곱셈법칙은 상호독립일 경우만 가능
  - 독립이 아닌 (종속의) 경우 하나의 주변확률과 다른 하나의 조건부확률을 곱해야 한다.



## 분할(partition)

- 합쳐서 전체를 포괄하되(collectively exhaustive) 겹쳐서 전혀 중복이 안되는 (mutually exclusive) 사건들의 집합
  - 예) 주사위를 한 번 던질 때 홀수가 나오는 사건과 짝수가 나오는 사건은 전체를 분할한다.
    - 반례 1) 홀수가 나오는 사건과 6이 나오는 사건 (전체 포괄 못함)
    - 반례 2) 홀수가 나오는 사건과 2 이상의 숫자가 나오는 사건 (중복 발생)



## 베이즈 정리

![bayes](https://imgur.com/WSjRUXr.png)

- 추론에 있어서 가장 중요한 확률 정리 가운데 하나이다.
- 조건부확률 <img src="https://latex.codecogs.com/gif.latex?\text{P(A} \mid \text{B)}"/>를 구하기 위해 <img src="https://latex.codecogs.com/gif.latex?\text{ P(B}\mid \text{A)}" />, <img src="https://latex.codecogs.com/gif.latex?\text{ P(B}\mid {A^C)}" />등 "입장이 바뀐" 조건부확률이 이용되고 있음



### 베이즈 정리의 응용

사지선다 문제를 맞추었을 때(B). 알고 풀었을(A) 확률은? <br/>

- 사전확률(prior probability) : 과거 경험에 비추어 P(A)= 1/2 상정 (사전 정보)
- <img src="https://latex.codecogs.com/gif.latex?{P(A^C) = 1-P(A)=1/2}" /> 
- 상식에 비추어 P(B|A) = 1 (알고 풀면 맞을 확률은 1)
- <img src="https://latex.codecogs.com/gif.latex?{P(B\mid A^C)=1/4}" /> (사지선다 문제이므로 "모르고 찍으면" 맞을 확률으 4분의 1)
- 베이즈 정리를 이용한 **사후확률(posterior probability)**의 계산, 확률의 업데이트(재평가)
  - ex. 양치기소년 : 자꾸 거짓말을 하니 사람들이 소년이 진실을 말할 확률을 점점 낮게 재평가

- 베이즈 정리 심화 내용 : [데이터사이언스스쿨](https://datascienceschool.net/02%20mathematics/06.06%20%EB%B2%A0%EC%9D%B4%EC%A6%88%20%EC%A0%95%EB%A6%AC.html) 참조
- 사전확률과 사후확률 심화 내용 : [Seungwoo's Daily](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=bsw2428&logNo=221388415015) 참조
