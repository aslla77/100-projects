# Rule: 릴리즈

- blocker가 있으면 "release ready"라고 말하지 않는다.
- 확인하지 않은 것을 확인했다고 말하지 않는다.
- 릴리즈·배포·마이그레이션은 자동 진행하지 말고 사람 승인 후 진행한다.
- 릴리즈 전 release-plan / rollback-plan / release-notes 필수.
- Tier 2 이상은 SLO·runbook 필수, 강한 릴리즈 게이트 적용.
- 릴리즈 전 sync-docs를 실행하고 QA·보안 blocker 잔존 여부를 확인한다.

## References
- `docs/workflow/gates.md` (Gate 6)
- `release/release-plan.md`
