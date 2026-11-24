# 박주윤 | Backend Engineer

Java와 Spring Boot로 서비스를 만드는 백엔드 개발자입니다.
문제는 먼저 재현하고, 고친 뒤에는 같은 조건으로 다시 측정합니다.

- Email: juyoon0423@daum.net

## Projects

**[InsightStock](https://github.com/juyoon0423/insight-stock)** | DART 공시 약 3,700건을 근거로 답하는 RAG 서비스 (1인 개발, 2026.07 ~ 2026.11)
- 검색 API 커넥션 교착을 트랜잭션 범위를 좁혀 해결, 성공률 83.2% → 100% (로컬 k6)
- 26문항 평가에서 답 없는 질문 8/8 거절, 근거 없는 수치 0개

`Spring Boot` `PostgreSQL(pgvector)` `Elasticsearch` `OpenAI API` `Next.js` `AWS`

**[Campus Market](https://github.com/juyoon0423/campus-market-app)** | 대학생 교내 중고거래 서비스 (1인 개발, 2026.04 ~ 2026.11)
- 좋아요 데드락 원인을 FK 검사의 공유 락으로 확인하고 락 순서를 바꿔 1,971회 → 0회
- 홈 목록 캐시가 옛 값을 보여 주던 문제를 고쳐 50회 반복 중 실패 12회 → 0회

`Spring Boot` `JPA` `QueryDSL` `MySQL` `Redis` `WebSocket` `Next.js`

## Experience

**샤이닝라이언** | 백엔드 개발 인턴 (2024.10 ~ 2025.01)
- 스튜디오 촬영 예약 플랫폼에서 예약 도메인 담당, 예약 API 6개와 관리자 페이지 개발

## Tech Stack

Java, Spring Boot, JPA, QueryDSL, MySQL, PostgreSQL, Redis, Elasticsearch, Docker, AWS, GitHub Actions, Next.js, TypeScript

## Education & Certifications

- 상지대학교 컴퓨터공학과 (2027.02 졸업예정)
- 정보처리기사, SQLD
- 멋쟁이사자처럼 백엔드 부트캠프 수료 2023.01 ~ 2023.06 (6개월)
