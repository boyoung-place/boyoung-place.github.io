---
title: "SNU경제통계학-Week3.상관관계와 회귀분석"
date: 2022-05-31
categories: statistics economic-statistics
---

K-MOOC 에서 제공하는 경제통계학 강의를 들으며 정리한 내용입니다. <br/>
[경제통계학_강의페이지](http://www.kmooc.kr/courses/course-v1:SNUk+SNU212_204_1k+2021_T2/course/)

# Week3. 상관관계, 회귀직선, 회귀분석

- 상관관계: 두 변수 사이의 상호관계를 분석하기 위한 방법을 익힌다. 산포도를 이용해 그림으로 나타내거나, 상관계수를 이용해 수치적으로 두 변수의 관계를 표현해보자.
- 상관관계와 회귀직선: 상관관계와 인과관계를 이해하고, 회귀직선을 통한 두 변수 사이의 관계를 학습한다. 추정된 회귀 직선의 회귀 계수의 의미에 대해 생각해보자.
- 회귀분석: 하나의 변수와 다른 여러 변수 간의 관계를 밝히기 위한 통계적 기법인 회귀분석에 대해 익힌다. 또한 자료의 평균의 그래프와 회귀직선의 관계에 대해 학습한다.



## 1. 상관관계

### 1.1 산포도와 상관관계

- **결합분포(joint distribution)**: 두 변수 간의 관계 전모를 보여줌  <br/>

  - ex. 교육과 임금, 통화증가율과 물가상승률, 또는 학급 규모와 학생 성적
  - 여기에서 상관계수의 개념이 나오게 된다.

- **산포도(scatter plot)**: 데이터가 얼마나 그리고 어떻게 퍼져있나를 나타냄  <br/>

  - 두 변수 사이의 관계를 살펴보기 위해 산포도를 이용한다.
  - 설명변수는 x로 표기하고 가로축에 표시하며, 피설명변수는 y로 표기하고 세로축에 표시한다.
  ![scatter_plot2](https://bokyeong-kim.github.io/assets/img/testscore.png)

  - 위의 산포도 그림에서 x와 y는 양(+)의 관계이다.

    - 중간고사 150점대의 기말고사 성적 분포를 보면, 둘의 관계가 다소 약한 것을 확인할 수 있다.

    - 변수 사이의 **관계가 약하면** 한 변수 값이 다른 변수 값을 **예측**하는 데 **큰 도움이 되지 않는다**.

    - 변수 사이의 **관계가 강하면** 한 변수 값이 다른 변수 값을 **예측**하는 데 **크게 도움이 된다**.

  - 산포도의 요약
    ![scatter1](https://bokyeong-kim.github.io/assets/img/scatter.png)
    - 가로로 보면 대략 95%의 점들이 x평균점을 기준으로 $\pm2SD_x$ 이내에 위치

    - 세로로 보면 대략 95%의 점들이 y평균점을 기준으로 $\pm2SD_x$ 이내에 위치

    - x의 평균과 표준편차, y의 평균과 표준편차는 x와 y의 분포를 따로따로 요약

        

### 1.2 상관계수

상관계수란 관계의 **방향**과 **강도**를 측정하는 지표이다. <br/>

상관계수(correlation coefficient)는 r로 표기한다. <br/>![scatter_plot_compare](https://bokyeong-kim.github.io/assets/img/scatter2.png)

- 위 산포도 그림을 보면, 가로든 세로든 평균과 표준편차가 동일해도 두 변수의 관계는 상이하다.

- 두 변수간 **선형관계**의 **방향(음/양)**과 **강도**가 얼마나 되는지 측정이 필요하며, 이를 나타내는 것이 상관계수이다.

- 한 산포도 그래프 상에 x와 y 두 변수가 있고, 이 두 변수(점)의 관계가 **직선에 의해서 잘 묘사될수록** 상관계수의 **절댓값이 크다**.

- 상관계수의 범위, 부호

  - 범위: $-1 \leq r \leq 1$

  - 상관계수 = 1 또는 -1이면 **완전상관(perfect correlation)**, 산포도 상의 모든 점들이 정확히 하나의 선 위에 위치

  - 상관관계가 양이면 산포도 상의 점의 분포가 우상향하고, 음이면 우하향한다.

  - 두 변수의 표준편차가 모두 0이면 상관계수를 정의할 수 없고, 둘 중 어느 한 변수만의 표준편차가 0이면 상관계수는 0이다.

  - 상관계수는 단위를 갖지 않는다.(단위와 관계없이 정의됨)

  - 또한 방향성을 갖지 않는다. 즉 x와 y의 상관계수는 y와 x의 상관계수와 같다.

  - 평균점을 원점으로 두고 구간을 나누어 보았을 때, 사분면(quadrant)이 확인된다. <br/>
    ![quadrant](https://imgur.com/ApC8G7d.png)

  - 상관계수를 구하는 공식  <br/>
    ![correlation_coefficient](https://imgur.com/x5CJm6S.png)

    - 각 변수를 평균으로부터의 편차로 변환
    - 두 편차를 서로 곱하여 합친 뒤 자유도 n-1로 나누어 공분산 구하기
    - 두 표준편차를 곱하고, 공분산 값을 해당 값으로 나눈다.



### 1.3 상관계수와 선형관계

상관계수가 유용하지 않은 경우가 있는데,  <br/>

1. **이탈값(outlier)**가 존재하는 경우 
2. 두 변수간 관계가 **비선형**인 경우
   - 선형관계만 가능
   - ex. 온도와 쾌적함
   - 직선근사불가능의 경우이며, 상관계수는 거의 0인 경우이다.
   - 상관계수가 0이라고 두 변수간에 아무런 상관관계가 존재하지 않는다는 해석은 잘못된 것이다.

- **변수변환**

  - 적절한 변수변환을 통하여 비선형 관계를 선형으로 근사시킨다.

  - x, y 간 존재하는 원래의 비선형 관계가 x, ln(y) 간의 선형 관계로 바뀐 경우가 변수변환의 예에 해당

    예시) 나폴레옹 군대의 1812 러시아 침공

    ![napoleon1](https://imgur.com/FigZOq3.png)

    ![napoleon2](https://imgur.com/aLabAqk.png)

    - 로그 변환을 통해서 진군 900km와 퇴각 900km의 구분점을 두고 기울기의 변화를 확인할 수 있다.
    - logy(로그 생존자 수), x, $(x-900)^+$ . 이렇게 3개의 변수에 대해서 **중회귀분석**을 한 것과 같다.
      - 중회귀분석(multiple regression analysis): 설명변수가 여러 개 있는 회귀분석





## 2. 상관관계 및 다른 관계들

### 2.1 상관관계와 실제 관계

##### 1) **상관관계가 실제의 관계를 과장하는 경우**가 생길 수 있다. 

![example_img](https://imgur.com/h4AV8e8.png)

- A, B, C (지역)의 교육수준 및 소득 관련 그래프
  - 왼쪽 그래프에서는 지역과 관계없이 개개인의 교육수준이 개개인의 소득과 관계가 있는 것으로 보이나, 오른쪽 그래프에서 지역별로 교육수준을 평균내어 보여주니 지역에 따라 평균소득에 차이가 발생하는 것처럼 과장된 결과를 보여준다.
    - 즉, 지역이나 국가 등 집단의 자료로부터 구한 상관계수는 개개인에게 적용되는 선형관계를 과장할 가능성이 있다.



##### 2) **상관관계가 곧바로 인과관계는 아니다.**

- x,y의 두 변수가 있고 이 둘의 상관 관계가 유의미할 때, x로 인해 y가 영향을 받는다 라고는 말할 수 없다.
- 상관관계 **is not** 인과관계!
- 생각해볼 예시
  - 자유무역과 경제성장
    - 많은 연구에서 자유무역과 경제성장 간에는 양의 상관관계가 존재하는 것으로 나타났다. 과연 자유무역이 경제 성장의 원동력이라고 말할 수 있을까? Maybe or Maybe Not
    - 후진국: 낙후된 지역, 잘못된 거시정책 등의 **제 3의 혼동요인이 존재**한다.
  - 자본유입과 경제성장
    - 중국 내 12개 성을 대상으로 조사한 결과 해외자본을 많이 유치한 성일수록 경제성장률이 높았다. 이 결과로부터 해외자본이 경제성장을 촉진시켰다고 말할 수 있을까?
    - 해외투자자: 성장잠재력이 큰 성에 투자할 수 있는 **역인과 관계의 가능성**이 존재한다.



## 3. 회귀직선

### 3.1 변수간의 관계 - 회귀분석

![regression_analysis](data:image/png;base64,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)

- 회귀분석(regression analysis)은 **집단별 평균을 분석**하는 통계적 방법

- 집단을 구분하는 분류지표가 1개, 2개, 또는 그 이상인지에 따라 **단순회귀분석**과 **중회귀분석**으로 나누어짐

- 위 그래프에서 실선(파란색)은 **회귀직선**이며, 원점을 지나는 점선은 **표준편차선**이다.

  - 회귀직선: 표준화된 x의 z값(그래프에서 +2)에 대응하는 y의 z값이 +2보다 작으므로 기울기가 완만해짐

  - 표준편차선: 두 변수(키와 몸무게)의 표준화된 변수 값이 같은 점들을 이은 직선이다.  <br/>

    *만약, 키와 몸무게의 관계가 완벽하다면 모든 점들은 표준편차선 위에 있어야 한다.

  - 위 그래프에서의 상관계수는 0.67이며, 키가 평균보다 $1SD_x$만큼 큰 사람들은 몸무게가 평균보다 대략 $0.67DS_y$만큼 더 나감

- 상관계수 r이 1보다 작으면 기울기(회귀직선의 기울기)가 표준편차선의 기울기보다 완만해진다.

  - x값이 x평균값에서 $1SD_x$ 증가할 때 y값은 y평균값에서 $r X SD_y$ 증가  <br/>

    => 회귀직선은 평균점을 지난다. 기울기는 $1SD_x$에 대해서  $r X SD_y$가 대응한다.

- 회귀직선은 평균의 그래프를 하나의 직선으로 근사시킨 것(x를 가지고 y를 설명하는 직선)

- 평균의 그래프가 비선형이면 회귀직선으로의 선형 근사는 부적절하다.





### 3.2 회귀분석방법

![graph](https://mblogthumb-phinf.pstatic.net/MjAxODA5MThfMzAg/MDAxNTM3MjcwNTExNDM3.-d7JIwlnu5nII5KoEXDnTRghPMOxXa_f12a67EiOzrEg.nlJD33ImeeHcHgyHmRpZqhQaUJWqoL0DvB8zxEooKg4g.PNG.bsw2428/image.png?type=w800)

- 분류집단에 대한 정보가 있으면 그 부분집단의 평균적인 y의 성향을 가지고 대답하는 것이 더 적합하다.

- 위 그림에서도 집단의 평균으로 추정한다. (키의 정보를 가지고 평균 몸무게로 대략적인 몸무게를 추정)

- 회귀분석방법의 예시 <br/>

  경제학부 10학번 학생 100명의 성적 정보를 활용하여 경제원론 학점 3.7인 지희의 경제통계학 학점 구하기

  - 경제원론 평균 = 3.0 / 표준편차 = 0.70
  - 경제통계학 평균 = 3.0 / 표준편차 = 0.60
  - 상관계수(r) = 0.5  <br/>

  => 경제원론의 표준편차: (3.7-3)/0.7=1  ->  $1SD_x$  <br/>

  => 경제원론의 표준편차를 기반으로, 경제통계학 학점은 평균보다 상관계수 x 표준편차만큼 높을 것이다. (회귀분석의 성질을 생각! 3.1 참조) <br/>

  => 0.5*0.6의 결과인 0.3을 경제통계학 평균 3.0에 더해준다. 따라서 지희의 경제통계학 학점은 3.3으로 예측된다.



### 3.3 회귀효과

##### 평범으로의 회귀(regression to mediocrity)

 ![regression_1](https://mblogthumb-phinf.pstatic.net/MjAxODA5MThfMjYx/MDAxNTM3MjcyNDAwNzI2.fN4s8ZbsVx1YAVht551iuYYtuNcqcZ4UdDq4x8hDnesg.IZ8LJHDGasF6vfWWptVhqLkDaeEnDcIuun0LHPPagkkg.PNG.bsw2428/image.png?type=w800)

- 상관계수가 완벽하지 않기 때문에, 즉 기말고사 점수를 결정하는 것은 중간고사 점수도 있지만 중간고사의 점수가 기말고사의 점수를 완벽하게 설명하지는 않는다. 추가적 불확실성이 존재하며 이로 인해 회귀직선은 보수적으로 그려진다.

- 1800년대 후반 유전학자 프랜시스 골턴은  아들들의 키는 아버지들의 키를 닮아가는 것과 함께 사람들의 평균키가 구심점으로 작동한다는 것을 알게 되었다. 이 현상을 골턴은 “평범으로의 회귀(regression toward mediocrity)”라고 칭하였다. 오늘날에는 일방적으로 "평균으로의 회귀"라고 한다. <br/>

  출처: [데이터링크](https://www.datadata.link/qa52-2/)

##### 회귀오류(regression fallacy)

- 회귀효과를 무언가 중요한 효과로 착각하는 것

- 상관관계가 인과관계를 의미하지 않는다는 의미의 다른 표현 방법이기도 하다.

- 회귀오류 예시

  - 소방관들은 집에 피해를 입히는 원인이다.
  - 가정교사는 아이들의 낮은 성적을 야기한다.  <br/>

  출처: [what_is_regression_fallacy](https://www.quora.com/What-is-the-regression-fallacy)

  

## 4. 3주차 퀴즈

[퀴즈 풀이 및 정답 링크](https://skillful-caboc-884.notion.site/Week3-Quiz-128deae168ad4d868b53cda2085814e7)
