# 박하성

**Technical Leader · System Architect · Full-stack (5+ years)**

📍 서울 / 원격 가능
📞 010-3980-4154
✉️ [haspark912@kakao.com](mailto:haspark912@kakao.com)
🔗 포트폴리오: [https://x-ordo.github.io](https://x-ordo.github.io)
🔗 GitHub: [https://github.com/x-ordo](https://github.com/x-ordo)

---

## 한 줄 요약

**엔지니어링 자체를 애정하며, 문제를 구조적으로 해체하고 깊이 사고하는 실행형 엔지니어**
기술을 목적이 아닌 *사고의 도구*로 사용합니다.

---

## 간단 소개

저는 대용량 데이터 처리, 모바일 애플리케이션, LLM 기반 자동화 시스템을 중심으로 실무 경험을 쌓아온 **5년차 소프트웨어 엔지니어**입니다.

개발을 단순한 구현 행위로 보지 않습니다. 문제를 정의하고, 그 문제를 구성하는 전제와 구조를 하나씩 분해한 뒤, **지금 이 문제에 정말 필요한 기술은 무엇인지**를 고민하는 과정 자체를 엔지니어링의 핵심으로 생각합니다.

초기에는 기술적 완성도를 높이는 데 집중했지만, 실제 서비스와 사업을 직접 운영하며 **완벽한 기술보다 중요한 것은 타이밍, 유통, 그리고 고객 확보**라는 사실을 체감했습니다.

최근에는 AI 생산성 도구(Claude, Gemini, ChatGPT)를 적극 활용해 **아이디어 → 구현 → 테스트 → 검증 → 폐기 또는 고도화**의 사이클을 빠르게 반복하고 있습니다. 총 **36개 이상의 프로젝트**를 수행했습니다.

---

## 경력

### ㈜제타럭스시스템

**소프트웨어 개발자 (주임)**
2021.11 – 2023.05

* Hadoop 기반 대용량 데이터 처리 파이프라인 설계 및 구현
  * 분석 흐름에서 병목이 발생하는 지점을 기준으로 구조를 재정의
* YOLO 기반 산불 영상 인식 시스템 개발 (ETRI 연구용역)
  * Android Native에서 실시간 영상 처리 성능과 안정성의 균형 조정
* 모바일 GIS 솔루션 *MapJoy* GS 인증 대응
  * 전면 수정보다 최소 침습적 개선 선택
* 디지털 사이니지 시스템 (Kafka, Go, Kotlin)
  * '확장성'보다 '운영 가능성'을 우선 고려

> 💭 이 시기에 **기술적 정답과 현실적 해답은 다를 수 있다**는 것을 깊이 체감했습니다.

---

### 애즈금융서비스 (GA)

**현장 영업 구조 이해 목적 근무**
약 6개월

* 보험 GA 영업 현장에서 고객 의사결정 흐름과 설득 구조 관찰
* 기술적으로 단순해 보이는 문제가 현장에서 해결되지 않는 이유 체감
* '사용자가 왜 이 기능을 쓰지 않는가'를 먼저 고민하게 된 계기

---

### 라비인터내셔널

**대표 / 개인사업자**
2023.11 – 2026.01

* 온라인 마케팅 자동화 프로그램 직접 개발 및 운영
* 수산물 판매, 해외 구매대행 자동화 등 다양한 실험 진행
* 모든 과정(기획, 개발, 영업, 운영, 철수)을 직접 경험

> 💭 여러 실패 경험을 통해 **실행하지 않으면 아무것도 알 수 없고, 눈으로 본 것조차 절반만 믿어야 한다**는 판단 기준을 갖게 되었습니다.

---

## Engineering Leadership

| | |
|---|---|
| 🏗️ **Architecture-First Thinking** | 코드 작성 전 시스템을 설계합니다. 모든 프로젝트는 문서화되고 정당화된 아키텍처 결정으로 시작합니다. |
| 🔒 **Security-Conscious Development** | CVE 모니터링, Dependabot 자동화, 보안 우선 코드 리뷰를 모든 프로젝트에 적용합니다. |
| 📊 **Risk Management Orientation** | Kelly Criterion 포지션 사이징부터 Merkle Tree 데이터 무결성까지 - 모든 도메인에 정량적 리스크 평가를 적용합니다. |
| 🔧 **DevOps Culture Advocate** | Conventional commits, semantic versioning, CI/CD 파이프라인, 포괄적 테스트 커버리지를 필수로 적용합니다. |

---

## Engineering Culture Evidence

| 지표 | 값 | 맥락 |
|------|-----|------|
| PRs Merged (ArbQuant) | **40+** | Conventional Commit 표준 |
| Test Coverage (HwpBridge) | **80%+** | Rust Workspace + Integration Tests |
| Issue Triage | **P0/P1/P2** | 우선순위 기반 이슈 관리 |
| Security Posture | **Active** | CVE 패칭, Dependabot 자동화 |
| Documentation | **RUNBOOK + DR** | 프로덕션 런북, 재해 복구 문서 |

---

## 주요 프로젝트 & 기술적 결정

### 1. ArbQuant - 암호화폐 차익거래 시스템

* **고민**: 개인 트레이딩에서 기관급 리스크 관리 구현 가능한가?
* **해결**: Kelly Criterion + Almgren-Chriss + Walk-Forward 백테스트로 정량적 리스크 관리
* **스택**: Go, Next.js, TimescaleDB, NATS JetStream, Fly.io + Oracle Cloud (Multi-cloud)
* **성과**: 40+ PRs merged, CVE 패칭 워크플로우, 일평균 0.3% 알파

### 2. Reporty (Project Iron Dome) - 직장 괴롭힘 리스크 관리

* **고민**: 양측 모두 기록 조작 동기가 있을 때 증거 무결성 보장
* **해결**: Merkle Tree + SHA-256 해시 체인으로 암호학적 변조 탐지
* **스택**: React, FastAPI, PostgreSQL, Qdrant, OpenAI GPT-4
* **성과**: LLM 기반 PII 탐지, 10,000+ 판례 Vector DB 검색

### 3. HwpBridge - Rust HWP 파서

* **고민**: 한국 정부/기업 문서가 AI 도구에서 접근 불가
* **해결**: MCP 서버 + 80%+ 테스트 커버리지 + Semantic Versioning으로 프로덕션급 구현
* **스택**: Rust, cfb, axum, MCP, WASM, Tauri
* **성과**: Claude Desktop 통합, Dependabot 자동화

### 4. Ansim Golf - 골프장 자동화

* **고민**: 시니어 운영자가 복잡한 UI를 탐색할 수 없음
* **해결**: 시니어 친화적 UI + Edge 아키텍처로 정산 수작업 80% 감소
* **스택**: Next.js, TypeScript, Cloudflare D1, Cloudflare Workers
* **성과**: 50ms 이하 응답, Zero-downtime 배포

### 5. Soul Lab - 토스 운세 미니앱

* **고민**: 소비자 앱에도 프로덕션급 운영이 필요
* **해결**: RUNBOOK + DISASTER_RECOVERY 문서화, 1,260개 결정론적 템플릿
* **스택**: React, TypeScript, Cloudflare Workers, Toss SDK
* **성과**: DAU 1,200+, 바이럴 500%+ 공유율

### 6. CHAGOK - AI 법률 보조 서비스

* **고민**: 법률 영역에서 '자동화'가 어디까지 허용되는가
* **해결**: Human-in-the-loop + 이중 RAG로 할루시네이션 최소화
* **스택**: Next.js, FastAPI, PostgreSQL, Qdrant, OpenAI GPT-4o
* **성과**: 멀티모달 증거 분석, SHA-256 Audit Log

### 7. 콘텐츠 자동 생성 시스템

* **고민**: 생성 품질보다 중요한 것은 일관성과 운영 비용
* **해결**: 역할 분리된 멀티 에이전트 구조로 11개+ 플랫폼 통합
* **스택**: React, FastAPI, Gemini 2.0, Claude 3.5, Replicate
* **성과**: YouTube, Instagram, TikTok 등 원클릭 퍼블리싱

---

## Technical Competencies

| 카테고리 | 기술 |
|---------|------|
| **System Architecture** | Event-driven (NATS JetStream), CQRS, Merkle Trees, Multi-cloud failover |
| **Backend / Infra** | Go, Rust, Python/FastAPI, Node.js, AWS, Cloudflare Workers, Fly.io |
| **Frontend / Mobile** | Next.js, React, TypeScript, Flutter, Kotlin, Android |
| **Data & Analytics** | TimescaleDB, PostgreSQL, Qdrant, Redis, Walk-Forward Backtest |
| **AI / LLM** | LangChain, RAG, MCP Server, Multi-Agent, PII Detection |
| **DevOps & Security** | CI/CD, Dependabot, CVE 모니터링, Semantic Versioning, 80%+ Coverage |
| **Risk Management** | Kelly Criterion, Almgren-Chriss, Z-Score Signals, Correlation Risk |

---

## 일하는 방식과 가치관

* 🧠 엔지니어링은 깊은 사고에서 시작된다고 믿습니다
* ✂️ 복잡한 문제일수록 먼저 단순화합니다
* 🎯 충돌을 피하지 않되, 반드시 결과로 수렴시킵니다
* ⭐ 기술은 고통이자 즐거움이며, **평가받을 때 비로소 완성**된다고 생각합니다

---

## 지원 동기

단순히 주어진 일을 처리하는 역할이 아니라,
**문제를 함께 정의하고 구조를 고민할 수 있는 팀**에서 일하고 싶습니다.

엔지니어가 사고할 수 있고, 그 사고의 깊이가 존중받는 환경이라면
**책임 범위를 가리지 않고 기여할 준비가 되어 있습니다.**
