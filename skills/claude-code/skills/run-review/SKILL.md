---
name: run-review
description: 구현 결과를 코드 리뷰할 때 사용. code-reviewer로 정확성·유지보수성·테스트 커버리지를 점검하고 수정 우선순위와 release blocker를 정한다.
---

# run-review

## 목적
구현을 리뷰하고 수정 우선순위·blocker를 정한다 (Gate 5).

## 읽어야 할 파일
- CLAUDE.md, README.md, planning/*, adr/*
- 최근 변경 코드와 관련 테스트

## 업데이트할 파일
- (리뷰 결과 보고. 작은 수정은 제안/적용 가능, 큰 변경은 제안만)

## 절차
1. code-reviewer 에이전트를 사용한다.
2. 요구사항 일치·복잡도·구조·이름·중복·에러 처리·테스트·보안 위험을 점검한다.
3. 문제를 "반드시/권장/나중에"로 분류한다.

## 출력 형식
1. 전체 평가 2. 반드시 고칠 문제 3. 권장 4. 나중 5. 테스트 보강 6. 우선순위 7. release blocker 여부

## 멈춰야 하는 지점
- 큰 구조 변경은 적용하지 말고 제안으로 남긴다.
- blocker가 있으면 release ready라고 말하지 않는다.

## 레퍼런스 규칙
`.claude/rules/coding.md` 준수. 불확실한 것은 불확실하다고 표시.
