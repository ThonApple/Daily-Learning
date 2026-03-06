# 백엔드 기초-01

2026-03-01

# 백엔드 프로그래밍
-  컴퓨터는 기본적으로 메시지를 수신할 수 없음.
- 메시지 수신을 위해서 '컴퓨터 -> 서버'로 바꾸어 메시지를 수신할 수 있게 함.

### 자주 사용되는 백엔드 프로그래밍 언어
1. `JavaScript`
2. `Python`
3. `php`
4. `Ruby`
5. `Java`

하지만 언어만으로 서버를 구축하는 것은 어렵기에, 도구를 사용한다.

### 1. 프레임워크
- 애플리케이션의 기본 뼈대와 규칙, 도구, 미리 작성된 코드 등을 묶어서 제공하는 기반 환경
- 대표적 : `JS Express`, `Django`, `Ruby on rails`, `Java Spring`, `PHP Laravel`

### 2. 패키지 매니저
- 패키지 : 다른 사람들의 코드 / 패키지 매니저 : 이를 설치하고, 관리함
- 대표적 : `npm(JS)`, `pip(Python)`, `Maven(Java)`

### 3. 데이터베이스
- 회원 정보, 구매 기록 등의 데이터가 저장되는 소프트웨어
- 대표적 : `MySQL`, `PostgreSQL`, `mongoDB`

# 요청 / 응답
1. 고객이 구매 버튼을 누름
2. 주문 내역이 서버로 전달 => `Request`
3. 서버는 주문내역을 DB에 저장
4. 서버는 주문완료 메시지를 고객에게 보냄 => `Response`

### Request
- id, 상품명, 수량, 결제수단, 고객주소 등 여러 정보가 담김
### URL에도 Request 정보가 담김
1. `요청Type` : `Post`, `GET`, `DELETE` ..
2. `Domain` : 경로 (ex : `www.'naver'.com`)
3. `URL Path` : `order`, `user`, `profile` ..

# API
### '서버가 처리할 수 있는 요청'을 일컫는다.
### REST 규칙
- `요청 Type` : 동사 (`POST` : 생성하기 / `GET` : 불러오기 / `DELETE` : 삭제하기)
- `URL PATH` : 명사 (`order`, `user`, `profile`)

### REST API
=> REST 규칙을 따른 API를 일컫는다.

### GraphQL 규칙
- `URL PATH`를 `graphql`로 통일
- ex) `POST/graphql`

### RPC 규칙
- `URL PATH`를 좀 더 상세하게
- ex) `POST/createOrder`, `POST/getOrderHistory`

# 클라우드 컴퓨팅
### 서버를 직접 구입하고 운영 X => 렌트해서 사용
- AWS, Google Cloud, Azure, Naver Cloud
### 1. IaaS (Infrastructure as a Service)
- 여러 대의 컴퓨터를 빌리는 것
- 소프트웨어 내의 컴퓨터 = '가상머신'을 빌린다.

### LB(로드 밸런서)
- 가상머신으로, 여러 VM에 작업을 분배함
- 트래픽 증가, 서버 과부하가 예상될 때 유동적으로 VM 갯수를 늘리고, 트래픽이 감소되면 VM 갯수를 다시 줄이는 등 유동적이고 비용적으로도 효율적 운용

### 2. PaaS (Platform as a Service)
- 백엔드 소스코드를 업로드 하기만 해도 `가상머신`, `로드밸런서` 세팅

### MicroService
- `주문 처리`, `결제 처리`, `이메일 송부` 세가지 기능을 지닌 백엔드 서버가 존재
- 기능별로 각각의 백엔드를 갖게됨. 또한 각 백엔드끼리 다른 언어를 사용해도 무관함.

### 3. SaaS (Software as a Service)
- 특정 서비스의 `백엔드`와 `API` 제공
- `MicroService`조차 직접 구축하지 않아도 됨.
- 이메일 송부 기능을 `twilio`가 제공하는 API를 통해 '내 고객에게 이메일을 보내달라'라는 요청을 보내면 됨


# Primary Database
- 일반적으로 웹에서 사용하는 데이터베이스를 일컫음. 대표적으로는 `MySQL`, `PostgreSQL`, `mongoDB`
- 이미지 업로드, 텍스트 검색, 데이터 분석 등에는 `Primary Database`가 적절하지 않음.
- redis와 같은 캐시 사용으로 성능 개선
### => 웹 백엔드에서는 각 목적에 따라 적절한 소프트웨어가 따로 존재함.
- `Primary DB`뿐만 아니라 폭넓게 공부해야 한다.