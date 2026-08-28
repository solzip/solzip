<div align="center">

# 조윤솔 | Backend Developer

결제 원장부터 LLM 출력까지, 정합성을 검증하는 백엔드

[![GitHub](https://img.shields.io/badge/GitHub-solzip-181717?style=flat-square&logo=github)](https://github.com/solzip)
[![Blog](https://img.shields.io/badge/Blog-solarchive.tistory.com-FF5A4A?style=flat-square)](https://solarchive.tistory.com/)
[![Email](https://img.shields.io/badge/Email-solarchive.dev%40gmail.com-0A66C2?style=flat-square)](mailto:solarchive.dev@gmail.com)

</div>

---

## What I Build

돈, 예약, 기부, 고객상담처럼 상태가 틀리면 사고가 되는 도메인을 주로 다뤄 왔습니다.  
단순히 기능을 붙이는 것보다 `불변식`, `멱등성`, `실패 격리`, `운영 검증`이 코드에 남는 구조를 선호합니다.

| Focus | How I Think |
|---|---|
| Payment consistency | 결제 성공, 티켓 발급, 예약 생성의 순서를 불변식으로 고정합니다. |
| Legacy migration | 멈출 수 없는 레거시 DB와 신규 서비스를 읽기 전용 경계, SP, Flyway로 분리합니다. |
| Failure isolation | 외부 API, PG, LLM provider 장애가 전체 장애로 번지지 않도록 timeout, circuit breaker, bulkhead를 둡니다. |
| LLM reliability | LLM 응답도 신뢰하지 않고 출처 지지도, 평가셋, No-Go 기준으로 검증합니다. |

## Tech Stack

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Cloud](https://img.shields.io/badge/Spring_Cloud-6DB33F?style=flat-square&logo=spring&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)

## Selected Work

| Project | Problem | Built |
|---|---|---|
| 고객상담 AI 챗봇 | ERP 데이터를 다루는 LLM 챗봇에서 오답과 데이터 유출을 막아야 했습니다. | RAG/LLM 검증 게이트, Function Calling 22종, provider별 Circuit Breaker, 평가셋 108건 |
| 스터디카페 결제·예약 MSA | 결제 실패 예약, 중복 승인, 레거시 DB 동거 문제가 있었습니다. | Spring Cloud MSA 8서비스, REST 26개, SP 27개, clientTid 멱등성, 보상 트랜잭션 |
| 무인매장 결제 게이트웨이 | 외부 API 장애가 PHP 워커와 DB 커넥션 고갈로 이어졌습니다. | 결제/전송 상태 분리, cURL timeout, inbound 19개 계약, RS232 도어 제어 |
| 사내 기부 키오스크 백엔드 | 사원증 기반 기부에서 개인정보를 최소 수집해야 했습니다. | 5서비스 MSA, pass-through 인사정보 처리, RFID 변환, 집계 정합성 |
| MailBean MSA 재설계 | Django 모놀리식 `views.py` 16,462줄을 도메인 서비스로 나눠야 했습니다. | 19개 서비스 설계, Gateway JWT, DB-per-Service 논리 분리, 테스트 700여 개 |

## Open Source

| Repository | Description |
|---|---|
| [agent-diary](https://github.com/solzip/agent-diary) | AI 작업 세션을 재현 가능한 기록으로 남기는 CLI. 멱등키, 재시도, 스키마 버저닝, 포스트모템 문서화를 구현했습니다. |
| [CodeFleet](https://github.com/solzip/codeFleet) | AI 에이전트의 주장과 하네스의 관측을 분리해 검증되지 않은 성공 보고가 통과하지 못하게 만드는 CLI 하네스입니다. |

## Current Interest

- 운영 가능한 LLM/RAG 시스템의 품질 게이트
- 결제, 예약, 원장성 데이터의 정합성 설계
- 레거시 시스템을 멈추지 않고 분리하는 백엔드 구조
- AI coding workflow의 검증 가능성

## Links

- GitHub: [github.com/solzip](https://github.com/solzip)
- Blog: [solarchive.tistory.com](https://solarchive.tistory.com/)

---

<div align="center">

문제가 생기지 않게 설계하고, 생겼을 때 추적 가능하게 남기는 백엔드를 만듭니다.

</div>
