# 조윤솔

Backend Developer

결제 원장부터 LLM 답변까지, 틀린 상태가 사용자에게 도달하지 않도록 설계합니다.

저는 백엔드를 요청 처리 계층이 아니라 상태를 보존하는 시스템으로 봅니다. 결제, 예약, 기부, 고객상담 자동화처럼 실패의 비용이 큰 영역에서 불변식, 멱등성, 실패 격리, 측정 가능한 품질 기준을 코드와 운영 절차로 남겨 왔습니다.

[GitHub](https://github.com/solzip) · [Blog](https://solarchive.tistory.com/) · [Email](mailto:solarchive.dev@gmail.com)

---

## 관심 있는 문제

제가 반복해서 파고드는 질문은 비슷합니다.

- 이 상태가 만들어지면 안 된다면, 애초에 표현 불가능하게 만들 수 있는가?
- 같은 요청이 두 번 와도 같은 결과로 수렴하는가?
- 외부 시스템이 멈췄을 때 우리 시스템은 어디서 멈추는가?
- 출시해도 된다는 판단을 로그, 평가셋, 기준선으로 설명할 수 있는가?

## 대표 작업

**ERP 고객상담 AI 챗봇**  
RAG/LLM 답변을 출처 지지도와 평가셋으로 검증하는 품질 게이트를 만들었습니다. ERP 조회·액션 Function Calling 22종을 멀티턴 흐름으로 구성했고, provider별 Circuit Breaker와 Bulkhead로 LLM 장애가 서비스 전체 장애가 되지 않게 분리했습니다.

**스터디카페 결제·예약 MSA**  
“결제되지 않은 예약”이 만들어질 수 없도록 결제 → 발급 → 예약 순서를 불변식으로 고정했습니다. Spring Cloud MSA 8서비스, REST 26개, Stored Procedure 27개 범위에서 `clientTid` 멱등키와 보상 트랜잭션을 설계했습니다.

**무인매장 결제 게이트웨이**  
외부 전송 실패가 매출 확정을 막지 않도록 결제 상태와 전송 상태를 분리했습니다. 외부 API 무응답으로 PHP 워커와 DB 커넥션이 고갈되던 운영 장애는 짧은 timeout, 실패 상태, 감사 로그로 끊었습니다.

**사내 기부 키오스크 백엔드**  
사원증 기반 기부 흐름에서 개인정보를 로컬 DB에 저장하지 않는 pass-through 구조로 재설계했습니다. RFID UID 변환, 캠페인별 집계, 증감 감사 이력까지 백엔드 흐름을 단독 구현했습니다.

**레거시 ERP MSA 재설계**  
Django 모놀리식 `views.py` 16,462줄을 19개 도메인 서비스로 나누는 설계를 맡았습니다. Gateway JWT, 서비스별 Flyway, DB-per-Service 논리 분리, 테스트 700여 개를 기준으로 제품화 가능한 구조를 제안했습니다.

## 공개 프로젝트

- [**agent-diary**](https://github.com/solzip/agent-diary): AI 작업 세션을 나중에 검토할 수 있는 기록으로 남기는 CLI입니다. 멱등키, 원인별 재시도, 스키마 버저닝, 포스트모템 문서화를 다뤘습니다.
- [**CodeFleet**](https://github.com/solzip/codeFleet): AI 에이전트가 완료했다고 말한 것과 하네스가 실제로 관측한 것을 분리하는 실험적 CLI입니다. 아직 제품이라기보다 AI coding workflow를 검증 가능한 절차로 만들기 위한 골격에 가깝습니다.

## 주로 쓰는 도구

Java, Spring Boot, Spring Cloud, MySQL, PostgreSQL, Redis, JPA, MyBatis, Flyway, Docker, systemd, Prometheus, Grafana, TypeScript

---

문제가 생기지 않게 설계하고, 생겼을 때 추적 가능하게 남기는 백엔드를 만듭니다.
