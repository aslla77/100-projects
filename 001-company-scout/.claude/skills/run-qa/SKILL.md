---
name: run-qa
description: QA를 실행할 때 사용. test-qa로 test-plan과 qa-report를 작성하고 정상·예외·회귀 흐름과 기본 접근성을 검증한다. 테스트하지 않은 것을 테스트했다고 말하지 않는다.
---

# run-qa

## 목적
실제 사용자 흐름에서 기능이 동작하는지 검증한다 (Gate 5).

## 읽어야 할 파일
- CLAUDE.md, README.md
- planning/prd-lite.md, user-flows.md, feature-scope.md
- 기존 tests/test-plan.md, 테스트 코드, 최근 변경 코드

## 업데이트할 파일
- tests/test-plan.md
- tests/qa-report.md

## 절차
1. test-qa 에이전트를 사용한다.
2. test-plan을 작성/갱신하고 핵심 흐름별 케이스를 만든다.
3. 정상·예외 흐름, 빈/오류/로딩 상태를 검증한다.
4. UI면 기본 접근성을 확인하고 회귀 영역을 정리한다.
5. qa-report를 작성한다.

## 출력 형식
- 테스트 범위, 통과/실패, 재현 방법, 심각도, 수정 제안, release blocker 여부

## 멈춰야 하는 지점
- 미테스트 영역을 테스트했다고 말하지 않는다.

## 레퍼런스 규칙
`.claude/rules/testing.md` 준수. 실패는 숨기지 않는다.
