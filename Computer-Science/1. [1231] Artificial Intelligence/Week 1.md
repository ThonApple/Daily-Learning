# 인공지능 1주차

# OT

## 필요 기술 스택
- Python 지식 필수
- Google colab 개발환경 이용 (무료 제약에 주의할 것)

### AI가 아무리 발전한다고 한들, '결국 방향성은 인간이 정한다.'
### 핵심 : 코드를 분석하며 '원리를 이해하라'

## 1~8주차 : Old AI
  1. Agent 개념 - Week 2
  2. (Search) 탐색 기술 - Week 3~6
  3. MCTS / 자동 계획(Planning) - Week 7~9

## 9~15주차 : 머신러닝
   4. Spuervised Learning (교사/ 감독 학습) - Week 10~11
   5. Reinforcement Learning, Unsupervise Learning, Deep Learning - Week 12~14

### 2. 탐색 기술
- 적대탐색 : 매 순간 나한테 유리하고, 상대한테 불리한 최선을 탐색 => 바둑, 오목
### 3. MCTS, 자동 계획
- MCTS : 알파고
- Planning : 임무가 주어짐 => 스스로 행동을 계획한다.
### 4. Supervised Learning (교사/감독 학습)
- Teaching => Learning (데이터로부터 학습한다.)
- 결정트리에 의해 결정
### 5. Reinforcement / Unsupervised / Deep Learning
- Reinforcement Learning(강화 학습)
- = 랜덤 행동 => 계속해서 결과에 대해 평가하며 최선을 찾아감
- Unsupervised Learning(비교사/무감독 학습)
- = 평균을 군집화함
- Deep Learning

# What is AI?
### 튜링 : 최초의 AI '지능 판단 척도'를 세움
- 판단자가 AI를 '사람'이라고 판단한다면 => 이것이 지능 판단 척도

### 1. 기호 처리 (과거)
- Fact를 기호로 : on(Mug, Table) => 컵이 테이블 위에
- 지식 기반 접근법 (지식의 양, 질, 행동패턴이 판단기준)
- 단점 : 느림. / 장점 : 양질의 답안
### 2. 신호처리 (현대))
- 수치데이터 -> (신경망) 연산 -> 행동제어신호
- '환경과의 상호작용'을 중시
- 단점 : 답안이 너무 단순 / 장점 : 빠름.
### 3. 혼합적, 계층적
- 저수준 : 신호처리 => 실시간성이 요구되는 빠른 행위
- 고수준 : 기호처리 => 답안의 질이 더 중요한 문제들 (추론, 탐색, 계획)

  