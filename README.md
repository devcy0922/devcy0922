# devcy0922

만들고, 운영하고, 왜 그렇게 결정했는지 남깁니다.  
화면부터 백엔드, 인프라까지 서비스의 라이프사이클을 다뤄왔습니다.

실제 쓰이는 제품을 만들고 굴려온 경험을 바탕으로,  
요즘은 **AI가 실제 시스템과 워크플로 안에서 안정적으로 동작하기 위한 실행 경계와 기반**을 만드는 데 집중하고 있습니다.

특정 기술을 맹신하기보다 문제를 정의하고, 경계를 나누고, 실패해도 복구 가능한 시스템을 만드는 것을 중요하게 생각합니다.

---

## 지금 집중하는 문제

```text
Application
    │
    ▼
AI / Agent
    │
    ▼
Execution Boundary
    │
    ├─ Authentication / Policy
    ├─ Model Routing
    ├─ Tool Permission
    ├─ Memory / Context
    ├─ Observability / Audit
    └─ Failure Isolation
    │
    ▼
Models / Tools / Infrastructure
```

모델을 호출하는 것에서 끝나기보다, 실제 시스템에 연결된 뒤의 문제를 다룹니다.

- 어떤 모델을 어떤 기준으로 연결할 것인가
- Agent에게 어디까지 실행 권한을 줄 것인가
- Tool Call을 어디에서 통제할 것인가
- Memory와 Context의 경계를 어떻게 나눌 것인가
- 실패한 실행을 어떻게 격리하고 복구할 것인가
- 실행 과정을 어떻게 관측하고 감사할 것인가

---

## Current Work · Private

현재 주요 제품과 플랫폼은 **Private Repository**를 중심으로 개발하고 있습니다.

**AI Platform / Infrastructure**  
LLM Gateway · Model Routing · Local Model Serving · Observability · AI Security

**Agent Infrastructure**  
MCP · Tool Execution · Memory · Workflow · Approval · Runtime

**Product Engineering**  
아이디어 정의 · UX · API · DB · Frontend · Deployment

비공개 프로젝트는 저장소 수나 기능 목록보다  
**어떤 문제를 정의했고, 어떤 구조를 선택했으며, 실제 운영에서 무엇을 바꿨는지**를 중심으로 발전시키고 있습니다.  
자세한 아키텍처와 운영 사례는 [devcy0922.github.io/projects](https://devcy0922.github.io/projects/)에서 정리하고 있습니다.

---

## Public Experiments

공개 저장소는 완성형 제품의 쇼케이스라기보다  
**아이디어와 아키텍처를 작은 코드로 검증하는 공개 실험 공간**입니다.

> Public repositories are prototypes and experiments.  
> Production-oriented work is primarily developed in private repositories.

### [CoexistGate](https://github.com/devcy0922/coexistgate)

Cross-artifact 릴리스 및 롤백 안전성 검증 엔진.  
스키마 변경과 API 배포가 다운타임 없이 공존 가능한지 정적 분석과 규칙으로 판정합니다.

`Go` `Release Safety` `Zero Downtime` `CI/CD`

### [AegisLLM](https://github.com/devcy0922/aegis-llm)

Rust 기반 LLM Security Gateway 프로토타입.  
LLM API 앞단의 인증, DLP/PII, Prompt Policy, Rate Limit, Audit 경계를 실험합니다.

`Rust` `Axum` `LLM Gateway` `Security`

### [Aperture-MCP](https://github.com/devcy0922/aperture-mcp)

Agent의 Tool Call이 실제 시스템에 도달하기 전에 정책을 적용하는 MCP 실행 프록시 실험입니다.

`Rust` `MCP` `Agent` `Tool Control`

### [Office Tone](https://github.com/devcy0922/office-tone)

LLM을 실제 사용자 경험으로 연결한 제품 실험입니다.  
원문의 의미는 유지하면서 직진도 · 방어도 · 비즈니스도를 조절합니다.

`Next.js` `TypeScript` `LLM` `Product`

---

## 주로 다루는 영역

| 영역 | 기술 / 관심사 |
| --- | --- |
| **AI / Agent** | LLM Gateway, MCP, RAG, Agent Runtime, Model Routing |
| **Backend** | Rust, Python, Node.js, PHP |
| **Frontend** | React, TypeScript, React Native |
| **Platform / Infra** | Docker, Kubernetes, GitHub Actions, AWS |
| **Security / Identity** | API Security, DLP, Audit, Keycloak |
| **Data** | PostgreSQL, pgvector, Redis, MySQL |

기술 목록 자체보다 **문제에 맞는 기술을 선택하는 것**을 더 중요하게 생각합니다.

---

## 개발하는 방식

```text
문제를 정의한다
      ↓
경계를 나눈다
      ↓
작게라도 동작하게 만든다
      ↓
직접 실행하고 관측한다
      ↓
실패 원인을 찾는다
      ↓
구조를 다시 다듬는다
```

문서에서 그럴듯한 설계보다  
**실제로 실행해보고 실패하면서 바뀐 설계**를 더 신뢰합니다.

> **Build something that runs. Then find out why it shouldn't.**

---

📝 기술 판단과 시스템 운영 기록은 **[devcy0922.github.io](https://devcy0922.github.io)**에 남기고 있습니다.

