# 운영체제 3주차 - 2

# 1. 프로세스
   운영체제가 관리하는 최소 단위
### 디스크에 있는 것 : 프로그램
### 메모리에 올라간 것 : 프로세스
### 메모리 구조 : heap을 통해 동적할당
### PCB : 프로세스의 정보(상태, 레지스터)를 저장하는 블록

# 2. 프로세스의 동작과정
## State
1. New - 생성
2. Ready - 준비
3. Running - 실행
4. Waiting - 대기
5. Terminated - 종료

## Scheduling
### Long-term
- `Job Queue -> Ready Queue` : 메모리에 프로세스를 얼마나 올릴지 조절
### Short-term
- `Ready Queue -> CPU` : 사용할 프로세서를 빠르게 고름
### Mideum-term
- Swap out : 메모리 부족시 프로세스를 `메모리 -> 디스크`로 잠시 쫓아냄

## Context Switch
- CPU가 다른 프로세스로 넘어갈 때, PCB에 이전 작업 상황을 저장(Save) / 불러옴(Reload) => Overhead

# 3. 프로세스의 생성과 종료
## 생성
### `fork()` : `SysCall` -> 똑같은 자식 생성
### `exec()` : 자신의 메모리를 새로운 프로그램으로 덮어씀
## 종료
### `exit()` : OS에게 자원 반납 요청
### `wait()` : 자식이 끝날때까지 대기 -> 끝나면 상태 정보 전달받음

# 4. 프로세스간 대화 : IPC
## 1. Shared Memory
- 두 프로세스가 공통으로 사용하는 메모리 구역 생성
- 빠르지만, 동시 접근 시 충동가능성 => 동기화 작업 필요
## 2. Message Passing
- `send`, `receive`로 `Message`를 주고받음
### Socket : IP, Port 연결로 데이터 주고받음
### RPC : 디테일(low level) 알 필요 없이 `Marshalling`으로 자동 전환
### Pipes : 관을 통한 소통 (구조화 X)

# 핵심내용
## 1. Context Switch
## 2. Scheduling
## 3. IPC