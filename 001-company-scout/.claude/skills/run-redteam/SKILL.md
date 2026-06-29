---
name: run-redteam
description: 코딩 전 계획을 공격할 때 사용. plan-redteam으로 불명확한 요구사항·과설계·누락 예외·리스크를 찾고, planner-architect가 계획을 한 번 수정한다.
---

# run-redteam

## 목적
build 전에 계획의 허점을 찾아 risk-register에 반영하고 계획을 강화한다 (Gate 3 마무리).

## 읽어야 할 파일
- README.md, brief/*, planning/*, adr/*

## 업데이트할 파일
- planning/risk-register.md
- planning/* (redteam 반영 수정)

## 절차
1. plan-redteam 에이전트로 계획을 공격한다.
2. 각 문제를 "문제→근거→영향→수정안"으로 정리한다.
3. risk-register에 반영한다.
4. planner-architect가 계획을 한 번 수정한다.
5. 마지막에 build 착수를 위한 사람 승인을 요청한다.

## 출력 형식
- 우선순위 리스크/수정안, 갱신된 계획 요약, 승인 요청

## 멈춰야 하는 지점
- 치명적 공백이 남으면 build로 넘어가지 말라고 권고한다.
- planning → build 전환은 사람 승인 게이트(멈춤).

## 레퍼런스 규칙
`reference-policy.md` 준수. 확실한 결함과 가능성을 구분한다.
