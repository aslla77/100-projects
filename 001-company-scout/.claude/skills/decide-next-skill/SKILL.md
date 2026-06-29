---
name: decide-next-skill
description: 현재 프로젝트 상태를 게이트에 매핑해 다음에 실행할 스킬을 결정할 때 사용. project-pipeline이 내부적으로 호출한다. 판단은 파일 존재 여부와 문서 내용에만 근거한다.
---

# decide-next-skill

## 목적
파일 증거를 바탕으로 현재 gate를 판정하고 다음 스킬(또는 멈춤)을 결정한다.

## 읽어야 할 파일
- `.project-state.md` (있으면)
- README.md, CLAUDE.md
- brief/*, research/*, planning/*, adr/*, tests/*, security/*, release/*, ops/*

## 판단 규칙
- **오직 파일 존재 여부와 문서 내용**에 근거한다. 기억·추측 금지.
- 산출물이 없으면 "없음"으로 본다. 가짜 완료 상태를 만들지 않는다.
- 추론이 필요하면 "가정"으로 표시한다.
- 위에서부터 순서대로 첫 번째로 충족되지 않은 gate를 현재 gate로 한다.

## 게이트 → 다음 스킬 매핑

| Gate | 판정 조건 (충족 안 됨 = 이 gate에 머묾) | 다음 행동 |
|---|---|---|
| Gate 0: Project not created | 프로젝트 폴더 없음 | skill `new-project` |
| Gate 1: Intake incomplete | README.md / brief 3종 / risk tier 중 하나라도 없음 | skill `new-project` 또는 `run-discovery` |
| Gate 2: Research incomplete | research/research-brief.md 또는 source-log.md 없음, 사실/가정/의견 분리 없음 | skill `run-discovery` |
| Gate 3: Planning incomplete | planning/prd-lite.md / feature-scope.md / user-flows.md / backlog.md 중 없음 | skill `run-planning` |
| Gate 4: Redteam incomplete | planning/risk-register.md 또는 redteam 결과 없음 | skill `run-redteam` |
| Gate 5: Human approval required | planning 승인 기록 없음 | **사람 승인 요청 후 멈춤** |
| Gate 6: Build incomplete | MVP 구현 전 (src/ 코드 없음) | skill `run-build` |
| Gate 7: Review incomplete | code-reviewer 결과 없음 | skill `run-review` |
| Gate 8: QA incomplete | tests/test-plan.md 또는 qa-report.md 없음 | skill `run-qa` |
| Gate 9: Security review needed | Tier 2+ 인데 security/security-review.md 없음 | skill `run-security-review` |
| Gate 10: Docs not synced | 코드와 문서 불일치 가능성 | skill `sync-docs` |
| Gate 11: Release not ready | release-plan / rollback-plan / release-notes 중 없음 | skill `prepare-release` |
| Gate 12: Ready | 위 전부 충족 | **사용자에게 다음 목표를 질문** |

## 출력 형식
- 판정한 현재 Gate (번호 + 이름)
- 판정 근거 (어떤 파일이 있고/없는지 — 증거 명시)
- 다음 스킬 또는 멈춤/질문
- 사람 승인 필요 여부 (Yes/No)
- 위험도 등급 (없으면 Unknown)

## 멈춰야 하는 지점
- Gate 5(planning 승인), 릴리즈/배포, 보안 변경에서는 자동 진행하지 않는다.

## 레퍼런스 규칙
`docs/workflow/gates.md`, `.claude/rules/workflow.md`를 따른다.
