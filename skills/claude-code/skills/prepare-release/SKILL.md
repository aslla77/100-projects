---
name: prepare-release
description: 릴리즈를 준비할 때 사용. release-ops로 release-plan, rollback-plan, release-notes를 작성하고 (Tier 2+ SLO/runbook) release readiness를 판단한다. blocker가 있으면 릴리즈 가능이라 말하지 않는다.
---

# prepare-release

## 목적
릴리즈 전 문서·검증 절차를 준비하고 readiness를 판단한다 (Gate 6).

## 읽어야 할 파일
- CLAUDE.md, README.md, planning/*
- tests/qa-report.md, security/security-review.md
- 기존 release/*, ops/*

## 업데이트할 파일
- release/release-plan.md, release-notes.md, rollback-plan.md
- Tier 2+ : ops/slo.md, ops/runbook.md

## 절차
1. release-ops 에이전트를 사용한다.
2. release-plan / rollback-plan / release-notes를 작성한다.
3. Tier 2+ 면 SLO·runbook을 확인/작성한다.
4. sync-docs 실행 여부와 QA·보안 blocker 잔존을 확인한다.
5. 최종 release readiness를 판단한다.

## 출력 형식
- 릴리즈 가능 여부, 남은 blocker, 체크리스트, 롤백 조건, 배포 후 지표, References

## 멈춰야 하는 지점
- 실제 릴리즈·배포·마이그레이션은 자동 진행하지 말고 사람 승인 후.
- blocker가 있으면 릴리즈 가능이라 말하지 않는다.

## 레퍼런스 규칙
`.claude/rules/release.md` 준수.
