# 안녕하세요, 백엔드 개발자 박주윤입니다

> **API 개발부터 배포·운영·장애 대응까지 직접 해보는 백엔드 개발자입니다.**
> 문제가 생기면 로그와 측정으로 근본 원인을 찾고, 해결 결과는 테스트와 수치로 검증합니다.

- 🔍 "보통 이렇게 한다"보다 **직접 측정한 결과**로 결정합니다. 인덱스도, 검색 방식도 실측해 보고 효과 있는 것만 남깁니다.
- 🤖 AI 검색·답변 서비스를 데모가 아닌 **배포 가능한 서비스**로 만들고, AI가 근거 없는 답을 지어내지 않도록 서버 구조로 제어합니다.
- 📫 **Contact** · juyoon0423@daum.net

<br>

## 🚀 Projects

### InsightStock — AI 금융 공시·뉴스 분석 서비스
`2026.07 – 2026.10` · 개인 프로젝트 · Spring Boot · PostgreSQL(pgvector) · Elasticsearch · OpenAI API · AWS

- 부하 테스트로 애플리케이션 설정 병목을 찾아 **동시 요청 성공률 16% → 95%**
- 검색 결과가 없으면 AI를 호출하지 않고, 출처 링크는 AI가 아닌 서버가 붙여 **잘못된 답변·링크 생성 차단**
- 키워드(BM25)·의미(벡터) 하이브리드 검색 설계, 벡터 인덱스(HNSW)로 **조회 59배 단축(738ms → 12ms)**
- Nginx Blue-Green 무중단 배포 구성, 전환 중 400회 요청 모두 정상 응답 검증

🔗 Repository (공개 준비 중)

### Campus Market — 대학생 전용 교내 중고거래 서비스
`2026.04 – 2026.05` · 개인 프로젝트 · Spring Boot · MySQL · Redis · WebSocket(STOMP) · Next.js

- 동시 요청 시 좋아요 **20건 중 1건만 반영**되던 문제를 재현하고, 락 전략을 비교해 **20건 모두 정확히 반영**
- 채팅방 중복 생성 레이스 컨디션 해결 과정에서 트랜잭션 스냅샷 함정까지 테스트로 발견·수정
- 채팅 메시지 위조, 타인 대화 열람(IDOR) 등 **보안 취약점 7건 점검·수정**

🔗 [Repository](https://github.com/juyoon0423/campus-market-app)

<br>

## 💼 Experience

**샤이닝라이언** · 백엔드 개발 인턴 `2024.10 – 2025.01`
- 기획·디자인·iOS·Android·웹 5개 직군과 API 명세를 조율하며 스튜디오 촬영 중고거래 플랫폼 백엔드 개발
- Spring Security·JWT 인증, AWS S3 이미지 업로드, GitHub Actions 배포 자동화, EC2·RDS 운영 환경 구축

<br>

## 🛠️ Tech Stack

**Backend**<br>
<img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/> <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/> <img src="https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=flat-square&logo=spring&logoColor=white"/> <img src="https://img.shields.io/badge/QueryDSL-0769AD?style=flat-square&logoColor=white"/> <img src="https://img.shields.io/badge/WebSocket(STOMP)-010101?style=flat-square&logo=socketdotio&logoColor=white"/>

**Database & Search**<br>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/PostgreSQL(pgvector)-4169E1?style=flat-square&logo=postgresql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white"/>

**AI**<br>
<img src="https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white"/> <img src="https://img.shields.io/badge/RAG-555555?style=flat-square"/> <img src="https://img.shields.io/badge/Hybrid_Search-555555?style=flat-square"/>

**Infra & DevOps**<br>
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white"/> <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/> <img src="https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white"/> <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white"/> <img src="https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white"/>

**Test**<br>
<img src="https://img.shields.io/badge/JUnit5-25A162?style=flat-square&logo=junit5&logoColor=white"/> <img src="https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white"/>

**Frontend**<br>
<img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white"/> <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black"/> <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white"/>

<br>

## 📜 Certifications

정보처리기사 · SQLD
