[CodeStates Project] US Adult Income 데이터를 활용한 머신러닝 모델 구현
===

![01](https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/01.jpg)

## 개요
* 코드스테이츠 AI 부트캠프에서 머신러닝을 구현한 프로젝트입니다.
* 문제 정의: **개인 신상정보 데이터를 바탕으로 연소득 5만 달러 초과 여부 분류(Classfication)**
* 데이터셋: 케글(Kaggle) US Adult Income 32,561건

## 내용
1. 베이스라인 및 평가지표  

 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/03.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/04.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/07.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/08.jpg' width='400px' height='300px'></img>
* OECD 국가 내 국민 소득 5만 달러의 의미는 선진국 중 선진국임을 의미
  - Target으로 5만 달러 이하 / 초과 여부를 예측하는 분류 모델을 만들고자 함
* 머신러닝 모델의 성능 향상 여부를 측정하기 위해 Decision Tree 모델을 베이스라인으로 지정
* 모델 평가지표는 정확도와 AUC Score를 사용

<br>

2. EDA/데이터 전처리  

 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/13.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/14.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/15.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/19.jpg' width='400px' height='300px'></img>
* 연소득 5만 달러 초과 비율은 30~40대가 가장 많음
* 중복되는 Education 특성 삭제(Education Num과 의미 동일)
* 교육 수준과 연소득이 가장 높은 상관관계를 보임
<br>

3. 베이스라인 모델

 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/20.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/21.jpg' width='400px' height='300px'></img>
* 베이스라인 모델(Decision Tree): 훈련 정확도 0.941 / 검증 정확도 0.812 / AUC Score 0.790
<br>

4. 모델별 비교 

 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/22.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/23.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/24.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/25.jpg' width='400px' height='300px'></img>
* 각 모델별 Default 설정값과 하이퍼파라미터 튜닝 후 설정값 비교 진행
* GradientBoostingClassifier 최종 모델 선정
  - 선정이유: 훈련/검증 정확도 모두 편차가 크지 않으며, AUC Score가 가장 우수
  
5. 결과 및 회고  

 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/26.jpg' width='400px' height='300px'></img>
 <img src='https://github.com/Sanghoon-Oh-34/cs_project02/blob/main/2.%20Slides/27.jpg' width='400px' height='300px'></img>
* 다양한 머신러닝 모델을 상호 비교하고, 이를 하이퍼파라미터 튜닝을 통해 성능을 개선
* 데이터마다 적합한 모델과 파라미터는 다를 수 있다는 점과 여러 시도를 통해 더 나은 결과를 도출할 수있음을 학습함
