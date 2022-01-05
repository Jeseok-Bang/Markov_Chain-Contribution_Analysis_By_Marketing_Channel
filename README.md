# Markov Chain을 활용한 마케팅 데이터분석
## 각 마케팅 채널의 기여도 분석과 각 기법 결과 비교
* 분석 도구 : Python
* 분석 기법
 * Last Interaction Attribution Model
 * First Interaction Attribution Model
 * Linear Interaction Attribution Model
 * Markov Chain Model
### 프로젝트 요약
#### (1) 분석개요
  * 마케팅의 목적 : 소비자들의 충족되지 못한 욕구를 발견하고, 그것을 충족시킬 방법을 마련하여 판매를 필수불가결하게 하는 것
  * 마케팅의 방법은 갈수록 다양해지고 있으며, 그중 디지털 마케팅의 비중이 더 커지고 있다.
  * 그래서 이번 프로젝트의 주제는 데이터로 디지털 마케팅의 효과를 측정하는 방법에 관하여 다루고자 한다.
  
#### (2) 분석기법
##### Last Interaction Attribution Model
  * 고객이 구매 또는 전환 이전에 마지막으로 상호작용한 채널이 전환 가치에 100% 기여했다고 간주
##### First Interaction Attribution Model
  * 고객이 상호작용한 첫 번째 채널이 전환 가치에 100% 기여했다고 간주
##### Linear Interaction Attribution Model
  * 모든 채널에 균등하게 1/N 전환, 이전의 모든 채널에 균등하게 전환값을 인정
##### Markov Chain
  ![abc](http://latex.codecogs.com/png.latex?\Pr(X_{n+1}=x|X_{1}=x_{1},X_{2}=x_{2},...,X_{n}=x_{n})=Pr(X_{n+1}=x|X_{n}=x_{n}))
  * 시간에 따른 계의 상태의 변화
  * X1, X2, X3 ... 사건들의 Sequence가 있을 때, 다른 state로 이동하는 확률은 과거 전부가 아닌 현재의 사건에서만 영향을 받는다.
    * State : 각각의 경우의 수
  * 이미 과거의 관측값은 더 앞선 과거의 영향을 받은 결과이므로 직전 관측값만 신경쓴다.
  * n번째 시점의 확률 변수가 i일 때, n+1번째 시점에 확률변수가 j가 될 조건부 확률을 전이확률(Transition Probability)이라고 부른다.
  * Removel Effect 제거 - Absorbing Markov Chain
    * 특정 채널의 전환이 아무것도 기여하지 않는다고 가정하여 계산
    * 예) 페이스북의 기존 total conversion이 30%였는데, 페이스북의 100% 전환 실패를 가정했을 때 얼마나 전환율이 떨어질지 계산
