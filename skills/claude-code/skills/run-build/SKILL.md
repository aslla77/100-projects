---
name: run-build
description: 승인된 계획에 따라 build 단계를 실행할 때 사용. coder로 작은 단위로 구현하고 테스트를 추가한다. 사람 승인 후에만 시작한다.
---

# run-build

## 목적
승인된 범위를 작은 단위로 구현한다 (Gate 4).

## 읽어야 할 파일
- CLAUDE.md, README.md
- planning/prd-lite.md, feature-scope.md, backlog.md, adr/*
- `.claude/rules/coding.md`, `.claude/rules/testing.md`
- 현재 위험도 등급

## 업데이트할 파일
- src/* (구현)
- 테스트 파일
- backlog.md (진행 상태), README (동작 변경 시)

## 절차
1. **사람 승인이 있었는지 먼저 확인한다.** 없으면 멈춘다.
2. coder 에이전트로 backlog의 가장 작은 핵심 작업을 고른다.
3. 짧은 구현 계획 → 코드 수정 → 테스트 추가/수정 → 자체 점검.
4. 변경 파일·구현 기능·추가 테스트·남은 리스크·다음 작업을 요약한다.

## 출력 형식
- 변경 파일 목록, 구현 기능, 추가 테스트, 실행 검증, 남은 리스크, 다음 추천 작업

## 멈춰야 하는 지점
- 사람 승인 없으면 시작하지 않는다.
- 구현 후 release로 넘어가지 않고 멈춘다 (review/qa 대기).
- 대규모 변경·마이그레이션·보안 변경은 승인 후.

## 레퍼런스 규칙
`.claude/rules/coding.md` 준수. 비밀키 하드코딩 금지.
