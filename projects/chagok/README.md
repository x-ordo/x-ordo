# CHAGOK (차곡)

> **이혼 소송 전용 AI 파라리걸 & 멀티모달 증거 허브**
> "변호사는 사건만 생성하고 증거를 S3에 올린다. AI는 AWS 안에서 증거를 정리·분석해 '소장 초안 후보'를 보여준다."

---

## 🔍 Project Overview

CHAGOK은 이혼 소송 과정에서 발생하는 방대한 비정형 증거 데이터(카톡, 녹음, 동영상 등)를 처리하는 데 드는 비효율을 해결하기 위해 개발된 **AI 파라리걸 플랫폼**입니다.

기존에 1~2주가 걸리던 증거 정리 작업을 **S3 Event 기반의 완전 자동화된 파이프라인**을 통해 **3분 이내**로 단축시켰으며, **이중 RAG(Dual RAG)** 기술을 적용해 법률 문서 작성의 정확도와 신뢰성을 획기적으로 높였습니다.

### 🛑 Problems Faced (직면한 문제)

1.  **비정형 데이터의 홍수**: 수백 개의 녹음 파일과 수천 장의 스크린샷을 엑셀에 수기로 정리하는 과정에서 인적 오류와 시간 낭비가 극심했습니다.
2.  **RAG의 환각(Hallucination)**: 일반적인 LLM은 판례와 사건 증거를 혼동하거나, 없는 사실을 지어내는 치명적인 리스크가 있어 법률 문서에 바로 적용하기 어려웠습니다.
3.  **컴플라이언스 이슈**: AI가 소장을 직접 작성하는 것은 변호사법 위반 소지가 있어, 기술과 법적 책임 사이의 명확한 경계가 필요했습니다.

### 💡 Solutions (해결책)

1.  **Event-Driven ETL Pipeline**:
    *   사용자가 S3에 파일을 업로드하는 즉시 `S3 ObjectCreated` 이벤트가 트리거되어, 파일 타입별(이미지/오디오/텍스트) AI Worker가 병렬로 분석을 수행합니다.
    *   Whisper(STT), GPT-4o Vision(OCR)을 활용해 모든 증거를 텍스트화하고 구조화된 데이터로 변환합니다.

2.  **Dual RAG Architecture**:
    *   **Legal RAG**: 변하지 않는 법률 조문, 판례, 양식
    *   **Case RAG**: 사건별로 격리된(Isolated) 증거 데이터
    *   이 두 가지 지식 베이스를 분리하여 쿼리함으로써, AI가 "법리"와 "사실 관계"를 명확히 구분하여 초안을 작성하도록 했습니다.

3.  **Draft Preview Pattern**:
    *   AI의 결과물을 "완성본"이 아닌 **"수정 가능한 초안(Preview)"** 형태로 제공합니다.
    *   최종적인 법적 판단과 제출 책임은 변호사에게 있음을 UI/UX적으로 명시하여 리걸테크 규제 리스크를 해소했습니다.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | Next.js 14, TypeScript, Tailwind CSS, Zustand |
| **Backend** | FastAPI, Python 3.11, Pydantic |
| **Database** | PostgreSQL (User/Case), DynamoDB (Evidence Metadata) |
| **Vector DB** | Qdrant (Case RAG Index) |
| **Storage** | AWS S3 (Server-Side Encryption) |
| **AI Model** | OpenAI GPT-4o, Whisper, GPT-4o Vision |
| **Infra** | AWS Lambda, ECS, CloudFront |

---

## 🏗️ System Architecture

```mermaid
flowchart TB
    User[변호사/의뢰인] -->|Upload| S3[AWS S3 Bucket]
    S3 -->|Trigger| Event[S3 Event Notification]
    Event -->|Invoke| Worker[AI Worker (Lambda/ECS)]
    
    subgraph "AI Analysis Pipeline"
        Worker -->|OCR/Description| Vision[GPT-4o Vision]
        Worker -->|STT/Diarization| Whisper[Whisper API]
        Worker -->|Parsing| Text[Text Parser]
    end
    
    Worker -->|Save Meta| Dynamo[DynamoDB]
    Worker -->|Indexing| Qdrant[Qdrant Vector DB]
    
    User -->|View Dashboard| Next[Next.js Client]
    Next -->|API Request| Fast[FastAPI Backend]
    Fast -->|Query| Qdrant
    Fast -->|Query| Dynamo
    Fast -->|Generate Draft| GPT[GPT-4o]
```

---

## 🚀 Key Features

*   **멀티모달 증거 분석**: 이미지 내 상황 묘사, 통화 녹음 화자 분리, 카카오톡 대화 흐름 분석을 통합 지원합니다.
*   **민법 제840조 자동 태깅**: 분석된 증거가 이혼 사유(부정행위, 악의의 유기 등) 중 어디에 해당하는지 AI가 자동으로 분류합니다.
*   **증거 타임라인 & 필터**: 수천 건의 증거를 시간순으로 시각화하고, 중요도/유책사유별로 필터링하여 사건의 맥락을 한눈에 파악할 수 있습니다.
*   **데이터 무결성 보장**: 모든 증거 파일에 SHA-256 해시를 적용하고, 조회/수정 이력을 Audit Log로 기록하여 법적 증거 능력을 유지합니다.

---

## 📊 Performance & Impact

*   **처리 속도**: 증거 100건 기준 분석 및 정리 시간 **3분 이내** (기존 2주 소요)
*   **초안 정확도**: 이중 RAG 적용 후 할루시네이션(없는 증거 인용) **0건** 달성
*   **보안**: 사건별 Qdrant Collection 격리로 데이터 오염 원천 차단

---

## 🔗 Links

*   **Repository**: [x-ordo/CHAGOK](https://github.com/x-ordo/CHAGOK) (Private)
*   **Demo**: (요청 시 제공)