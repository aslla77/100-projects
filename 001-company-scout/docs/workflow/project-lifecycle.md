# 프로젝트 라이프사이클

아이디어를 단계별로 이동시키는 가벼운 대기업식 프로세스. 위험도 등급에 따라 무게를 조절한다.

## 단계

| # | 단계 | 주체 에이전트 | 핵심 산출물 | 게이트 |
|---|---|---|---|---|
| 1 | intake | (사람) | README, brief/* , 위험도 등급 | Gate 1 |
| 2 | research | research-analyst | research-brief, source-log | Gate 2 |
| 3 | planning | planner-architect | prd-lite, user-flows, feature-scope, risk-register, backlog, ADR | Gate 3 |
| 4 | redteam | plan-redteam → planner 수정 | 수정된 planning 문서 | Gate 3 |
| — | **사람 승인** | (사람) | build 착수 승인 | — |
| 5 | build | coder | src/*, 테스트 | Gate 4 |
| 6 | review | code-reviewer | 리뷰 결과 | Gate 5 |
| 7 | qa | test-qa | test-plan, qa-report | Gate 5 |
| 8 | security | security-reviewer | security-review (Tier2+ : threat-model, dependency-review) | Gate 5 |
| 9 | sync-docs | (skill) | 최신화된 문서 | Gate 6 |
| 10 | release | release-ops | release-plan, rollback-plan, release-notes | Gate 6 |
| 11 | ops | release-ops | slo, runbook, incident-log | — |

## 등급별 적용

- **Tier 0**: 2·3 경량, 6·7 자체 점검, 8 생략 가능, 10 경량.
- **Tier 1**: 6·7 필수(경량), 8 기본 점검.
- **Tier 2**: 8 필수(threat-model + dependency-review), 10 강한 게이트.
- **Tier 3**: 위협 모델링 + 롤백 + SLO + runbook + postmortem 체계 필수.

## 반복 루프

```
만들기 전: 리서치 → 기획 → 레드팀
만드는 중: 작게 구현 → 코드 리뷰 → QA
내보내기 전: 보안 리뷰 → 문서 동기화 → 릴리즈 플랜
세션 후: 배운 점 기록 → CLAUDE.md 최적화
```

## References

- `gates.md`
- 상위 `Projects/CLAUDE.md`
