# 운영체제 2주차
# 1. 운영체제의 정의 및 역할
## 하드웨어 관리
- 자원 할당, 프로그램 통제
### CPU, I/O device
- 병렬작동.
# 2. 인터럽트, 시스템 호출
### 벡터 인터럽트 시스템
- Vector 명시: (인터럽트 서비스 루틴의 주소를 포함) 인터럽트 벡터를 통해 제어가 전달됨
- IDT (Interrupt Descriptor Table): 인터럽트 관리를 위한 테이블이 지속적으로 참조됩니다.
- 1. libc 라이브러리의 fork() 함수 호출
- 2. EAX 레지스터에 시스템 호출 번호(예: fork는 2번)를 넣습니다.
- 3. 인터럽트 0x80을 발생시켜 시스템 호출 시작
- 4. 커널은 EAX 값을 참고하여 sys_call_table에서 해당 함수를 호출하여 실행

### 입출력 구조
- 병렬작동 : CPU와 I/O 장치는 동시에 실행될 수 있음(효율 높임)
- DMA (Direct Memory System) : 대량의 데이터 이동 시 CPU 개입 없이 장치 컨트롤러가 직접 메모리와 데이터를 전송.
- 1. I/O -> DMAC : 데이터 전송 요청
- 2. DMAC -> Processor : BusRequest
- 3. Processor -> DMAC : BusAcknowledge
- 4. DMAC -> I/O : 데이터 전송 응답

# 3. 시스템 구조 및 스케줄링
### NUMA (Non-Uniform Memory Access)
- 각 CPU가 자신의 로컬 메모리를 가짐, 다른 메모리에 접근할 때보다 빠름.
### 단일 프로그래밍 (Singleprogramming)
- CPU, I/O 둘 중 하나는 쉬고 있는 경우가 많음
### 다중 프로그래밍 (Multiprogramming)
- CPU가 쉬지 않게 여러 작업을 메모리에 올려두고 전환하며 실행
### 시분할 (Timesharing/Multitasking)
- TQ(Time Quantum)라는 시간 할당량을 각 프로세스에 부여하여, 사용자가 모든 프로세스가 동시에 실행되는 것처럼 느끼게 함
- 다중프로그래밍은 P1의 작업이 '끝나야' 다음 P2로 넘기지만, 시분할은 무조건 TQ(할당된 시간)내에 작업이 끝나지 않아도 강제로 다음으로 넘김.

# 4. 이중 모드 동작
시스템을 보호하기 위해 `사용자 모드`와 `커널 모드`를 구분.
- Mode Bit : 하드웨어의 현재 모드. $I_{bit} = 0$은 커널 모드, $1$은 사용자 모드를 의미함.
- 상태 전이 : 사용자 프로세스가 시스템 호출을 하면 Trap이 발생하여 커널 모드로 전환됩니다. 작업 해결 후 다시 사용자 모드로 복귀함.
- 타이머 : 무한 루프나 자원 독점을 방지하기 위해 TQ를 설정하며, 이는 `커널 모드에서만 설정 가능`한 특권 명령


# 5. 관리 활동 
### 프로세스 관리
- 프로세스 간의 동시성을 맞춰야 하며, 데드락발생 => OS가 이를 해결
### 메모리 관리
- 어떤 메모리가 사용 중인지 인지 => 프로세스를 페이지 단위로 나누는 페이징(Paging) 기법 등을 사용
### 보안
- 파일 접근 제어(User/Group ID) 및 사용자 인증을 담당

# 정리
1. OS 역할 두가지 : 자원 할당, 프로그램 통제
2. Single Programming -> Multi Programming
3. Multi Tasking : TQ를 통해 스케줄링
4. Interrupt : HW or SW(Error, SysCall)
5. Trap(수단) : Error발생시 / SystemCall호출시 => Kernal Mode
6. Dual Mode : 현재 모드는 `User Mode` or `Kernal Mode`
   - 할당된 모드에 맞는 명령어 사용해야함. => 아니면 `Trap` 발생

### System Call Flow
1. Call Syscall (trap)
2. Mode : User -> Kernal
3. Execute Syscall
4. Mode : Kernal -> User
5. Return Syscall