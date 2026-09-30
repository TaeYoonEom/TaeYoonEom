# Hi there 👋 I'm TaeYoon Eom

### Backend Developer | 문제를 분석하고, 설계와 검증을 통해 해결합니다.

동시성 제어부터 데이터 정합성, 트랜잭션, DB 성능까지 고민하는 백엔드 개발자입니다.

Java와 Spring Boot를 중심으로 MSA 기반 서비스를 개발하며, Race Condition·외부 시스템 장애·트랜잭션 경계 문제를 분석하고 Testcontainers 기반 테스트로 검증해 왔습니다. 기술을 선택할 때는 트레이드오프를 근거로 판단하고, 설계와 검증 과정을 함께 공유하는 개발 방식을 지향합니다.

---

## 💡 About Me

- 💪 **Strengths:** #실행력 #문제해결 #책임감 #협업
- ☕ **Backend:** Java / Spring Boot 기반 백엔드 개발
- 🏗️ **Architecture:** MSA · Spring Cloud · Kafka 기반 이벤트 처리
- 🔒 **Core Interests:** 동시성 제어 · 데이터 정합성 · 트랜잭션 설계
- 📈 **Engineering:** 성능 개선 · 외부 장애 대응 · 테스트 기반 검증

### 🔍 What I Solved

- **동시성 문제를 애플리케이션과 DB 양쪽에서 방어**
  `PESSIMISTIC_WRITE`로 동일 자원의 처리를 직렬화하고, PostgreSQL Partial Unique Index를 최종 방어선으로 사용했습니다.
- **외부 호출과 DB 트랜잭션 경계 분리**
  외부 Feign 호출을 트랜잭션 밖으로 이동하고 DB 반영 전용 계층을 분리해 트랜잭션 범위를 데이터 변경 구간으로 축소했습니다.
- **MSA 환경에서 서비스 간 책임과 통신 구조 설계**
  Feign 기반 동기 통신과 Kafka 기반 비동기 이벤트 처리를 적용하고, 서비스 간 의존성과 트랜잭션 경계를 고려해 구조를 설계했습니다.
- **외부 시스템 장애와 비즈니스 실패 구분**
  Timeout은 실패가 아닌 미확정 상태로 관리하고, 체결 조회로 실제 결과를 재확인하도록 설계했습니다.

---

## 🛠 Tech Stacks & Tools

**Backend**

Java · Python · Spring · Spring Boot · JPA · Django

**Database**

PostgreSQL · MySQL · MariaDB · Redis · SQL

**Architecture / Messaging**

MSA · Spring Cloud · Kafka · RabbitMQ

**Tools / Infra**

Docker · Git · GitHub · IntelliJ · VS Code

---

## 🚀 Core Projects

### 📈 [AI 기반 주식 자동매매 플랫폼](https://github.com/sajo-team/sajo)

2026.08 - 2026.09 | 6인 팀 | Trading 도메인

Kafka Signal 기반 주문 생성과 KIS 주문·체결 연동을 담당했습니다.

| 중복 주문 | 오확정 |
| :---: | :---: |
| 4% → 0% | 12% → 0% |

- `PESSIMISTIC_WRITE`로 동시 Signal 경합 직렬화
- TIMEOUT 주문 재조정 및 KIS 체결 조회 보정
- Partial Unique Index로 AutoTrading 중복 생성 방어

`Java` `Spring Boot` `Kafka` `PostgreSQL` `Flyway` `Feign` `Testcontainers` `Docker`

### 🚚 [MSA 기반 B2B 물류 플랫폼](https://github.com/develop-9/delivery-project)

2026.08 | 6인 팀 | Delivery Service

배송 경로 관리, 배송 담당자 라운드로빈 배정과 상태 전이를 구현했습니다.

| 순번 중복 | 배송 수정 API 응답 |
| :---: | :---: |
| 12% → 0% | 850ms → 320ms |

- 순번 채번 `PESSIMISTIC_WRITE` + Partial Unique Index
- DeliveryRoute 이중 상태 전이 동시성 제어
- 외부 Feign 호출과 DB 트랜잭션 경계 분리 (DB Connection 평균 점유시간 700ms → 90ms)
- PostgreSQL 제약 회귀 테스트 5개 자동화

`Java` `Spring Boot` `Spring Cloud` `JPA` `QueryDSL` `PostgreSQL` `Flyway` `Feign` `Testcontainers` `Docker` `Zipkin`

### 📚 국제 저명학술지 연구 동향 분석 시스템 (졸업 작품)

2024.12 - 2025.12 | 3인 팀

국제 학술 논문을 수집·분석하고 검색, 연구동향 시각화, 자연어 분석을 제공했습니다.

- BERT 임베딩과 코사인 유사도 기반 의미 검색
- KeyBERT 기반 핵심 키워드 자동 추출
- 반정규화와 SQL 최적화를 통한 대량 데이터 조회 개선

`Python` `Django` `MariaDB` `BERT` `KeyBERT` `TF-IDF` `LLaMA` `Nginx` `Gunicorn`

### 🚗 중고차 거래 플랫폼 클론

2025.06 - 2025.12 | 3인 팀 | Full-stack

차량 검색·상세조회·찜하기·판매등록과 마이페이지 기능을 구현했습니다.

- 단계형 차량 판매 등록 프로세스 구현
- Draft 데이터 관리 및 차량 유형별 DB 분리
- 정렬·페이지네이션·차량 상세 데이터 연동

`Spring Boot` `Java` `JavaScript` `MariaDB`

---

## 🗂 Other Projects

- 🛵 [AI 메뉴 설명 생성을 접목한 모놀리식 배달 플랫폼](https://github.com/9jo-delivery/repo) — 지역·배송지 도메인 담당, 기본 배송지 동시성 문제를 `PESSIMISTIC_WRITE`로 해결 · `Java` `Spring Boot` `Spring Security` `JPA` `PostgreSQL` `JWT`

---

## 🎓 Education & Certificates

- **안양대학교 소프트웨어공학부** | 2020.03 - 2026.02 졸업 | 학점 4.02 / 4.5
- **정보처리기사** | 한국산업인력공단 | 2026.06
- **SQL 개발자(SQLD)** | 한국데이터산업진흥원 | 2024.12

---

## 📖 Currently Learning

대규모 AI 시스템 설계를 위한 백엔드 아키텍처 심화 과정을 수강하고 있습니다.

- Spring Boot · MSA · DDD
- Apache Kafka · RabbitMQ · Redis
- Concurrency Control · Distributed Systems
- Transaction Management · System Design

---

## 🌱 Growing as a Backend Developer

왜 이 기술을 사용하는지 이해하고, 문제를 발견하고, 설계하고, 구현한 뒤 검증할 수 있는 개발자를 목표로 성장하고 있습니다.

**기능의 완성뿐 아니라 데이터의 정합성과 시스템의 안정성까지 책임지는 백엔드 개발자가 되겠습니다.**

---

📫 **Contact:** djaxodbs0101@naver.com | [Tech Blog](https://taeyoon2.tistory.com)
