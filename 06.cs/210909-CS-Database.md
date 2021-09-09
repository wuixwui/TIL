|   date   |    title     | skill |
| :------: | :----------: | :---: |
| 21.09.09 | CS, Database |  cs   |

---

# TIL

1. CS

---

[wuixite](https://www.notion.so/wuixite-d8b5ee54b67949e8b38cbd6ac3eb44d7)

# 0909

- 정보처리 기사 자격증

  4년치 안의 기출

- jam stack

## Progammers - today

[코딩테스트 연습 - 폰켓몬](https://programmers.co.kr/learn/courses/30/lessons/1845#)

[코딩테스트 연습 - 로또의 최고 순위와 최저 순위](https://programmers.co.kr/learn/courses/30/lessons/77484)

## CS

### Compute & Calculate

- computation 규칙을 정한 계산 → 저장 및 실행이 되는가?
- calculation 단순 연산 계산

## Computer

(기본 구성) 메모리 - 중앙처리장치 - 입력장치

### 64bit 32bit

[64비트 32비트 CPU와 운영체제 에 대하여](https://eine.tistory.com/entry/64%EB%B9%84%ED%8A%B8-32%EB%B9%84%ED%8A%B8-CPU%EC%99%80-%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C-%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC)

### CISC & RISC

[CISC와 RISC의 기술구조적 차이](https://chlalgud8505.tistory.com/8)

### Memory

- RAM (Random Access Memory)

  주기억장치

  어떤 위치로든 같은 시간에 접근

  전원을 종류하면 사라집니다.

- ROM (Read Only Memory)

  계속 정보를 유지하는 주기억장치

  부팅에 필요한 정보들을 가지고 있다 (OS, BIOS, Firmware등의 정보 저장)

### Kernel

하드웨어랑 응용프로그램을 이어주는 핵심 시스템 소프트웨어

하드웨어 추상화 - 일관성 있는 인터페이스 제공

### OS

UNIX 기반 / WINDOWS

---

## Database

체계화된 데이터의 모임

### data = octet

### DBMS

DB를 관리할 수 있는 응용 프로그램

### DB 특성

- 데이터의 무결성
- 데이터의 중복 방지
- 보안
- 성능 향상
- 프로그램 수정과 유지 보수 용이

응용프로그램과 DB의 차이점

- 자기 기술성
  - .xls는 엑셀이 필요 / .doc word 필요
  - DB는 SQL이 있으면 가능

### SQL

Structured Query Language

데이터 관리를 위해 설계된 특수 목적의 프로그래밍 언어

조작 언어

- CREATE
- DROP
- AFTER
- INSERT
- UPDATE
- DELETE
- SELECT

제어 언어

- GRANT 권한 부여
- REVOKE 권한 박탈

### RDBMS

엑셀과 비슷한 형태

(row와 column이 존재)

schema(스키마) 존재

- PostgreSQL

### NoSQL (Not only SQL)

다양한 형태를 가지고 있다.

(Row, Document, key-value등의 형태)

확장 가능성

스키마 없는 데이터 모델에 유리

- join이 불가능
- 수평확장 용이 (정보가 늘어날 경우)
  - 수직확장은 가입자가 늘어날 경우 ( RDB가 유리)
- {key:value} Redis
- [Column] 분석용 (Cassandra)
- MongoDB (Document)

안전하게 사용되어야 하는 정보는 RDB

구매관련(관리가 까다로운 정보)은 NoSQL위주

### Schema

- 데이터 베이스의 구조와 제약조건에 대한 전반적인 명세 기술
- 데이터베이스의 청사진

> **외부스키마, 개념스키마**, 내부스키마

- 외부 스키마 : 데이터의 논리적인 구조
- 개념 스키마: 연결관계를 정의
- 내부 스키마: 데이터 베이스가 저장되는 방법

## Software Engineering

### DevOps

- 좋은 소프트웨어를 위한 필수조건

  기획팀과의 원활한 소통으로 요구사항을 충실히 반영

  운영팀과의 원할한 소통으로 소비자 불만과 의견을 반영

운영과 개발을 통합하여 커뮤니케이션 리소스를 줄임

- 지속적 통합 / 지속적 배포

개발 생명 주기

### SDLC

계획 개발 시험 배포

### Requirements

무엇이 구현되어야 하는가에 대한 명세

요구 분석은 개발자와 클라이언트 모두를 만족시키기 위한 연결 고리

- 요구사항 유도
- 요구사항 분석
- 요구사항 기록

### Business Requirements

> 왜? 프로젝트를 수행하는지

고객이 제품을 개발함으로써 얻을 수 있는 이득

- Use case diagram
- User stories 화면의 구성 순서

### Functional Requirements

> 개발자가 이 제품의 "무엇"을 개발할 것인지

- ~해야한다.

### System Requirements

> 어떤 장비에서

### Business Rules

비즈니스 스트럭쳐의 요구나 제약사항을 명세

- "유저 프로필 페이지에 접근하지 위해서는 로그인 되어 있어야 한다."

### Quality Attribute

소프트웨어의 품질에 대해 명세

### Constraint

제약조건 (기술, 표준, 업무, 법)

---

## Process Model

### Build-fix Model

만들고 고친다. → 좋지 않음

### Waterfall Model

추가 사항을 추가하기 어렵고

### Prototype Model

최소한의 요구사항으로 제작

피드백 반영에 빠름

## Agile

### UP (Unified Process)

waterfall 과 비슷한 형태의 애자일

### XP (eXtreme Process)

스크럼 마스터가 주도적으로 프로세스를 주도

TDD 중시

### TDD

test driven development

- 객체지향적

반복적으로 개발

### Scrum

상호 점진적 개발 방법론

개발할 기능에 우선순위를 부여하고 순서대로 진행

매일 15분의회의(Daily Scrum) 진행 1~4주의 sprint
