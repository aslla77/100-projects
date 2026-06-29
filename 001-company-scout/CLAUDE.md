# company-scout — 프로젝트 운영 계약서

이 파일은 이 프로젝트의 운영 헌법이다. 짧고 강하게 유지한다.
공통 규칙은 상위 `Projects/CLAUDE.md`를 상속한다. 여기에는 이 프로젝트 고유 내용만 둔다.

## 제0지침

`docs/00-principles/reference-policy.md`의 제0지침을 최상위로 따른다. (요약: 모르면 모른다고, 추론 금지, 출처 우선, 사실·가정·의견·추천 분리)

## 미션

> 타깃 회사 1곳의 **공개·검증 가능한 실제 문제**를 출처와 함께 수집·구조화해, AX 인재전쟁 2026 예선 Codex 플러그인 기획의 신뢰 가능한 입력을 만든다.

## 위험도 등급

> Tier 0 — 근거: 개인용 로컬 도구. 사용자 데이터·로그인·외부 결제 없음. 공개 자료만 다룸. 외부 배포 없음. (단, 출처 검증 원칙은 예선 채점 규칙과 동일하게 Tier와 무관하게 엄격히 적용)

## 산출 형식 (고정 제약)

> 예선 제출물 = **Codex 플러그인**. `submission.zip` 안에 `src/.codex-plugin/plugin.json`(필수) + `skills/<이름>/SKILL.md` 등. Claude 스킬 아님. [예선 과제 원문 primary]

## 기술 스택 / 실행

| 항목 | 값 |
|---|---|
| 언어/프레임워크 | 확인 필요 — planning에서 확정 |
| 산출 포맷 | Codex 플러그인 (`src/.codex-plugin/plugin.json` + `SKILL.md`) |
| 빌드 | 확인 필요 |
| 테스트 | 확인 필요 |
| 실행 | Codex 플러그인으로 실행 가능해야 함 |
| 배포 | 해당 없음 (개인 도구) |

## 빠른 시작: `/project-pipeline`

개별 스킬을 외울 필요 없이 `/project-pipeline` 하나만 실행하면 현재 상태(`.project-state.md` + 파일 증거)를 점검해 다음 스킬을 순서대로 실행/추천한다.
- 새 프로젝트: 프로젝트 정보(이름/아이디어/타깃/목표/유형/스택)를 주면 `new-project`부터 시작.
- 이어서 작업: 인자 없이 실행하면 현재 gate를 판정해 다음 단계 진행.
- 사람 승인 게이트(planning→build, 릴리즈/배포, 보안 변경, 데이터 삭제, 대규모 변경)에서는 멈춘다.

## 워크플로우 단계 & 필수 산출물

intake → research → planning → redteam → (승인) → build → review → qa → security → sync-docs → release → ops
게이트 상세: `docs/workflow/gates.md`. 상태 기반 자동 진행: skill `project-pipeline` / `decide-next-skill`

## Definition of Ready (build 시작 조건)

- [ ] problem-definition.md, success-metrics.md 작성됨
- [ ] 위험도 등급 지정됨
- [ ] prd-lite.md, feature-scope.md, user-flows.md 작성됨
- [ ] risk-register.md 작성, plan-redteam 반영됨
- [ ] 중요한 결정에 ADR 존재
- [ ] 사람 승인 완료

## Definition of Done (release 조건)

- [ ] 승인된 범위 구현 + 테스트 추가됨
- [ ] code-reviewer / test-qa 통과
- [ ] Tier 2+ : security-reviewer 통과
- [ ] sync-docs 실행됨
- [ ] release-plan / rollback-plan / release-notes 작성됨
- [ ] Tier 2+ : SLO / runbook 작성됨

## 규칙 라우팅

| 영역 | 파일 |
|---|---|
| 코딩 | `.claude/rules/coding.md` |
| 테스트 | `.claude/rules/testing.md` |
| 보안 | `.claude/rules/security.md` |
| 디자인 | `.claude/rules/design.md` |
| 릴리즈 | `.claude/rules/release.md` |
| 문서 | `.claude/rules/documentation.md` |
| 출처 | `.claude/rules/reference-policy.md` |

## 에이전트 역할

`.claude/agents/` 참조: research-analyst, planner-architect, plan-redteam, ui-designer, coder, code-reviewer, security-reviewer, test-qa, release-ops

## 사람 승인 게이트

- planning → build 전
- 릴리즈 직전
- 보안 변경 / 데이터 마이그레이션 / 비용 발생 작업 전

## References

- 상위 `Projects/CLAUDE.md`
- `docs/workflow/project-lifecycle.md`
