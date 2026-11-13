# 박주윤 | Backend Engineer

측정으로 문제를 재현하고 수치로 판단을 검증하는 백엔드 개발자입니다.
Java와 Spring Boot로 공시 약 3,700건을 근거로 답하는 RAG 서비스 InsightStock을 기획부터 AWS 배포까지 혼자 만들었습니다.
가설이 틀린 결과도 기록해 다음 판단의 근거로 씁니다.

- Email: juyoon0423@daum.net
- Live: [InsightStock](https://frontend-steel-omega-0zye89ut4w.vercel.app) (면접 기간 중 운영)

<br>

## Projects

### InsightStock | AI 금융 공시 분석 서비스

`2026.07 ~ 2026.10` 1인 개발 (기획, 백엔드, 프론트엔드, AWS 배포)

공시 원문을 근거로 질문에 답하고, 답변 속 출처를 DART 원문과 연결하는 RAG 서비스입니다. 색인 공시 약 3,700건, 청크 약 17만 건 규모입니다.

**Stack** Spring Boot, Spring Security, PostgreSQL(pgvector), Elasticsearch(Nori), OpenAI API, Next.js, AWS EC2, Nginx

- AI 답변 시, 모델이 출처를 지어낼 위험을 번호 인용과 서버의 DART 원문 연결로 막아 26문항 평가에서 답 없는 질문 8/8 거절, 근거 없는 수치 0개 확인
- 검색 전략 설계 시, "하이브리드가 키워드보다 낫다"는 가정을 평가 세트 18문항으로 측정해 한국어 공시에서는 키워드 단독을 넘지 못함을 확인
- 인덱스 점검 시, EXPLAIN ANALYZE로 실제 쿼리를 측정해 HNSW는 유지(738ms → 12ms), 쓰이지 않던 pg_trgm은 제거
- 검색 API 부하 테스트 시, 처리량 정체 원인을 서버 로그로 커넥션풀과 스레드풀에서 찾아 성공률 16.0% → 94.8% 개선 (로컬 k6, 20 → 100 VU)
- Blue-Green 전환 시, 두 인스턴스가 DB 연결을 가득 채우는 문제를 HikariCP minimum-idle 조정으로 해결해 전환 구간 연결 100개 → 21개 감소, 전환 2회 모두 요청 400회 전부 200 응답
- 임베딩 시, 1.1억 토큰을 호출 전 로컬 토크나이저로 계산해 비용 $2.23 추정, 분당 토큰 한도에 맞춘 요청 간격과 재시도로 429 에러 3,235건 → 0건

[Repository](https://github.com/juyoon0423/insight-stock)

### Campus Market | 대학생을 위한 교내 중고거래 서비스

`2026.04 ~ 2026.06` (동시성 개선 `2026.08 ~ 2026.10`) 1인 개발 (기획, 백엔드, 프론트엔드)

대학생끼리 물품을 사고팔 수 있는 교내 중고거래 웹 서비스입니다.

**Stack** Spring Boot, JPA, QueryDSL, MySQL, Redis, WebSocket(STOMP), Next.js

- 거래완료 동시 요청 시, 서로 다른 구매자가 모두 성공해 거래 상대가 바뀌는 문제를 비관적 락과 상태 검증으로 해결해 2건 중 정확히 1건만 성공
- 좋아요 동시 요청 시, 20건 중 17~18건이 InnoDB 데드락으로 실패하는 문제를 데드락 포함 재시도와 유니크 제약으로 개선해 좋아요 수와 실제 저장 건수 일치
- 상품 동시 조회 시, 조회수와 좋아요가 같은 버전 필드를 공유해 생긴 충돌을 원자적 UPDATE 분리로 해결해 100건 중 실패 93~94건 → 0건
- 세 문제 모두 JUnit과 ExecutorService 동시성 테스트로 먼저 재현하고, 수정 후 같은 테스트로 반복 검증

[Repository](https://github.com/juyoon0423/campus-market-app)

<br>

## Experience

### 샤이닝라이언 (Shining Lion) | 백엔드 개발 인턴

`2024.10 ~ 2025.01` 스튜디오 촬영 예약 플랫폼 Toucheese

기획, 디자인, iOS, Android, 웹 5개 직군이 함께한 팀에서 백엔드 2인 중 1인으로 참여했습니다.

- 예약 도메인 개발 시, 예약 REST API 6개와 관리자 예약 관리 페이지를 단독 개발하고 겹치는 예약 검사와 스케줄러 기반 지난 예약 자동 완료 구현
- 스튜디오 검색 API 개선 시, 조건 조합마다 늘어나던 JPQL 메서드 7개를 QueryDSL 동적 쿼리 1개로 통합
- 서비스 배포 시, 수동 배포를 GitHub Actions와 Docker 파이프라인으로 바꿔 release 브랜치 push만으로 EC2 배포 자동화

<br>

## Tech Stack

**Backend**<br>
<img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/> <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/> <img src="https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=flat-square&logo=spring&logoColor=white"/> <img src="https://img.shields.io/badge/QueryDSL-0769AD?style=flat-square&logoColor=white"/> <img src="https://img.shields.io/badge/WebSocket(STOMP)-010101?style=flat-square&logo=socketdotio&logoColor=white"/>

**Database & Search**<br>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/PostgreSQL(pgvector)-4169E1?style=flat-square&logo=postgresql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white"/>

**Infra & DevOps**<br>
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white"/> <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/> <img src="https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white"/> <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white"/> <img src="https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white"/>

**Frontend**<br>
<img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white"/> <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black"/> <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white"/>

**Test & Etc**<br>
<img src="https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white"/> <img src="https://img.shields.io/badge/JUnit5-25A162?style=flat-square&logo=junit5&logoColor=white"/> <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white"/> <img src="https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white"/>

<br>

## Certifications & Education

- 정보처리기사 (2026.09)
- SQLD (2024.09)
- 상지대학교 컴퓨터공학과 편입, 2027.02 졸업 예정
- 멋쟁이사자처럼 백엔드 부트캠프 수료 (2023.01 ~ 2023.06)
