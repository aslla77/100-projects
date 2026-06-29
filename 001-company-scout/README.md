# 001 · company-scout (회사 리서치 스카우트)

> 타깃 회사 1곳을 입력하면 **공개·검증 가능한 자료만으로** 그 회사를 회사·제품·고객·재무신호·문제·관련회사로 구조화하고, **초심자도 읽고 이해할 수 있는 출처 검증 보고서(dossier)** 를 만들어 주는 개인용 리서치 도구.

| 항목 | 값 |
|---|---|
| 프로젝트 | 001-company-scout |
| 위험도 등급 | **Tier 0** — 개인 로컬 도구, 사용자 데이터·로그인·결제 없음, 공개 자료만 사용 |
| 상태 | **MVP 사용 가능** (build 완료 · 구조 검증 · 패키징 완료) |
| 산출 형식 | Codex 플러그인 + Claude Code 스킬 (동일 방법론) |

## 무엇을 하나

회사명 하나(`/company-scout <회사명>`)를 받아:

1. **회사 유형 판별 → 검색 전략** 수립 (커머스/핀테크/컨설팅/비상장 등)
2. **5축 수집**: 회사 → 제품 → 고객 → 문제 → 관련회사
3. **출처-주장 일치 점검**: 모든 사실 주장에 공개 URL + 등급(A/B/C) + 확인일. 충돌 시 양쪽 병기·"재확인 필요"
4. **문제 후보 ≥3개** 발굴 + 적합성 3축 점수
5. **초심자용 보고서 조립** (요약 우선, 평이한 문장, 용어 설명 포함)

### 절대 규칙 (제0지침)

- 공개·검증 가능한 자료만 근거로 사용. 출처 없으면 **"근거 부족"** 또는 **"가설"** 로 강등.
- **확정 사실**과 **이슈 예측(가설)** 을 절대 섞지 않는다.
- 모르면 모른다고 한다. 추론은 "가정/가설"로 표시.

### 출처 등급

| 등급 | 정의 |
|---|---|
| **A** | 공식·표준: 회사 공식 사이트·채용공고(JD)·보도자료, DART 전자공시, 정부·표준 문서 |
| **B** | 평판 있는 2차: 주요 경제·테크 매체 |
| **C** | 단서 전용: 커뮤니티·블로그·유튜브·위키 (사실 단정 금지) |

## 사용 방법

**Claude Code 판** (이 디렉터리):

```
/company-scout <회사명>
```

→ WebSearch/WebFetch로 5축 수집 후 `out/<회사명>-dossier-YYYYMMDD.md` 로 저장.

**Codex 플러그인 판**: `src/.codex-plugin/plugin.json` + `src/skills/company-scout/SKILL.md`.

## 산출물 예시

- `out/SK하이닉스-dossier-20260629.md` — SK하이닉스 공개자료 기반 기업 이해 보고서 (실제 생성물)
- `src/examples/myrealtrip-dossier.md` — 형식·깊이의 골든 예시 (마이리얼트립)

## 디렉터리 구조

```
.claude/            Claude Code 운영 자산 (rules / agents / skills)
brief/              intake 산출물 (problem-definition, success-metrics 등)
research/           리서치 산출물 (research-brief, source-log)
planning/           기획 산출물 (prd-lite, feature-scope, backlog, risk-register)
adr/                주요 기술 결정 기록
src/                Codex 플러그인 본체 (.codex-plugin/plugin.json, skills/, examples/)
dist/               자기완결형 배포 zip (claude-skill / codex-plugin)
out/                생성된 회사 dossier 출력물
docs/               워크플로우·원칙 문서
tests/              보고서 합격 체크리스트
CLAUDE.md           프로젝트 운영 계약서
.project-state.md   단일 상태 소스 (게이트 진행 추적)
```

## 워크플로우 (게이트 기반)

```
intake → research → planning → redteam → (승인) → build → review → qa → security → sync-docs → release → ops
```

현재까지: intake·research·planning·redteam·build 완료 → MVP 사용 가능.

---

이 프로젝트는 [100 Projects](../README.md) 시리즈의 **#001** 입니다.
