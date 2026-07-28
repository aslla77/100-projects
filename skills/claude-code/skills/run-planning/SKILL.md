---
name: run-planning
description: 기획 단계를 실행할 때 사용. planner-architect로 PRD-lite, 사용자 흐름, 기능 범위, 백로그, 리스크를 작성하고 중요한 결정을 ADR로 남긴다. 아직 코딩하지 않는다.
---

# run-planning

## 목적
리서치를 가벼운 MVP 계획으로 변환한다 (Gate 3).

## 읽어야 할 파일
- README.md, brief/*, research/*
- `.claude/rules/planning.md`, `reference-policy.md`

## 업데이트할 파일
- planning/prd-lite.md, user-flows.md, feature-scope.md, backlog.md, risk-register.md
- 중요한 결정 시 adr/000N-*.md
- docs/architecture/architecture-overview.md (필요 시)

## 절차
1. planner-architect 에이전트를 사용한다.
2. 가장 작은 MVP를 정의하고 포함/제외를 나눈다.
3. PRD-lite, user-flows, feature-scope, backlog를 작성한다.
4. 중요한 기술 결정은 ADR로 기록한다 (선택지·트레이드오프·출처).
5. 사실/가정/의견/추천을 구분한다.

## 출력 형식
- MVP 범위, 핵심 사용자 스토리, 제외 항목, 리스크, ADR 목록, References

## 멈춰야 하는 지점
- redteam 전이므로 build로 넘어가지 않는다.

## 레퍼런스 규칙
`.claude/rules/planning.md` 준수. 과설계 금지.
