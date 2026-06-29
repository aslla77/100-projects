---
name: capture-session-learnings
description: 생산적인 세션이 끝나거나 같은 실수가 반복될 때 사용. 교훈을 분류해 CLAUDE.md/rules/skills/docs 중 알맞은 곳에 반영 제안한다. 수정 전 승인을 받는다.
---

# capture-session-learnings

## 목적
세션에서 얻은 규칙·절차·교훈을 운영체계에 반영한다.

## 읽어야 할 파일
- CLAUDE.md, `.claude/rules/*`, `.claude/skills/*`
- docs/operations/session-learnings.md (없으면 생성)

## 업데이트할 파일
- 분류에 따라: CLAUDE.md / rules / skills / docs
- docs/operations/session-learnings.md

## 분류 기준
- 항상 지킬 짧은 규칙 → CLAUDE.md
- 특정 경로/기술 규칙 → `.claude/rules/`
- 반복 절차 → `.claude/skills/`
- 배경 지식 → docs/
- 검증 안 됨 → session-learnings.md "검토 필요"

## 절차
1. 관련 문서를 읽고 중복·충돌을 확인한다.
2. 새 교훈을 분류한다.
3. 반영 위치와 이유를 제안한다.

## 출력 형식
- 새 교훈, 반영 위치 추천, 반영 이유, 반영하지 말 것, 수정 제안 diff/요약

## 멈춰야 하는 지점
- 실제 파일 수정 전 반드시 제안만 먼저 보여주고 승인을 받는다.

## 레퍼런스 규칙
검증되지 않은 내용은 규칙화하지 않고 "검토 필요"로 남긴다.
