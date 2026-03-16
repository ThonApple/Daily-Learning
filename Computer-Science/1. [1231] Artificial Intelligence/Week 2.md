# 인공지능 2주차

# Intelligent Agents

## 1. What is Agent?
### Agent : 자율 존재

로봇 : 정해진대로 움직임
AI : 센서로 환경 감지 => '자율적으로' 행동 결정

Effector : 환경을 변화시킴(행동)

### 2. Agent function
Percept Sequence와 Action들을 나열

Sensing을 통해 Percept(지각) => Percept Sequnce(지각열)
Percept Sequence을 통해 -> Actions 결정

청소 로봇
Percept = [Location, Status]
Actions = [Left, Right, Suck, NoOp]

### Agent program
Agent function을 실행하는 아키텍처
(Percept로 Action 자율적 결정)

f(location, status) return `action`
  if ~ then
  else if ~ then
  else if ~ then

### 3. Rational Agent
`성능지표` 기대값을 가장 높이는 행동을 하는 에이전트

### 4. PEAS
설계 이전에 구체적으로 명세되어야 하는 네가지
Perfomance Measure
Enviroment
Actuators
Sensors

### 5. 환경 특성 분석
1. Fully observable vs Partially observable
  - 완전 관찰 : 작업에 필요한 '모든 정보'를 실시간 파악 (체스 - 판 위의 모든 말이 보임)
  - 부분 관찰 : 정보 일부가 누락, 노이즈가 섞임(포커 - 상대 패를 모름)
2. Deterministic vs Stochastic
- 결정론적 : 현재 상태에서 에이전트의 행동이 다음 상태를 100% 예측 가능하게 결정 (퍼즐)
- 확률론적 : 행동의 결과에 불확실성이 존재 (주식)
3. Static vs Dynamic
- 정적 : 행동을 고민하는 동안에도 환경이 변하지 않음 (턴 게임)
- 동적 : 실시간으로 환경이 변함 (FPS)
4. Discrete vs Continuos
- 이산적 : 딱 딱 끊어진 유한함 (전자시계)
- 연속적 : 속도, 위치, 각도 등이 실수형태로 끊임없이 이어짐(아날로그 시계)
5. Episodic vs Sequential
- 에피소드적 : 현재 결정이 미래에 영향 X
- 순차적 : 현재 행동이 미래의 상태/결과에 계속 영향을 미침
6. Signle Agent vs Multiagent
- 단일 에이전트 : 환경에 나 혼자 존재 (벽돌게임)
  멀티 에이전트 : 다른 에이전트 존재, 협력이나 경쟁 (축구 등)