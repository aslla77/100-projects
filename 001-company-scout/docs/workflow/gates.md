# 워크플로우 게이트

각 게이트는 다음 단계로 넘어가기 전 충족해야 하는 조건이다. 충족 못 하면 멈추고 보고한다.

## Gate 1 — Intake complete
- [ ] `brief/problem-definition.md` 작성
- [ ] `brief/success-metrics.md` 작성
- [ ] 위험도 등급 지정 (README + CLAUDE.md)

## Gate 2 — Research complete
- [ ] `research/research-brief.md` 작성
- [ ] `research/source-log.md` 작성
- [ ] 사실 / 가정 / 의견 분리
- [ ] References 섹션 작성

## Gate 3 — Plan approved
- [ ] `planning/prd-lite.md` 작성
- [ ] `planning/feature-scope.md` 작성
- [ ] `planning/user-flows.md` 작성
- [ ] `planning/risk-register.md` 작성
- [ ] 중요한 결정에 대한 ADR 작성
- [ ] plan-redteam 실행 후 수정 반영
- [ ] **사람 승인 완료**

## Gate 4 — Build complete
- [ ] 승인된 범위 코드 구현 완료
- [ ] 관련 테스트 추가
- [ ] 동작이 바뀐 경우 README 업데이트

## Gate 5 — Review complete
- [ ] code-reviewer 통과 (blocker 없음)
- [ ] test-qa 통과 (blocker 없음)
- [ ] Tier 2+ : security-reviewer 통과

## Gate 6 — Release ready
- [ ] `release/release-plan.md` 작성
- [ ] `release/rollback-plan.md` 작성
- [ ] `release/release-notes.md` 작성
- [ ] Tier 2+ : `ops/slo.md`, `ops/runbook.md` 작성
- [ ] sync-docs 실행됨
- [ ] 미해결 blocker 없음

## 규칙

- blocker가 남아 있으면 "release ready"라고 말하지 않는다.
- 확인하지 않은 항목을 확인했다고 말하지 않는다.
- 위험도 등급에 맞는 게이트만 강제한다 (과설계 금지).

## References

- `project-lifecycle.md`
- `.claude/rules/workflow.md`
