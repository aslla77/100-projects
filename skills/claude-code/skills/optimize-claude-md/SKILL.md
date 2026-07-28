---
name: optimize-claude-md
description: CLAUDE.md가 길어졌을 때 사용. 짧고 강하게 줄이고 긴 절차는 skills, 경로 규칙은 rules, 설명은 docs로 옮긴다. 제0지침은 반드시 보존한다.
---

# optimize-claude-md

## 목적
CLAUDE.md를 200줄 이하로 유지하려 시도하고 중복·충돌을 제거한다.

## 읽어야 할 파일
- CLAUDE.md, `.claude/rules/*`, `.claude/skills/*`, docs/**

## 업데이트할 파일
- CLAUDE.md (초안)
- 이동 대상 rules/skills/docs

## 절차
1. CLAUDE.md와 관련 문서를 검토한다.
2. 긴 절차→skills, 경로 규칙→rules, 설명·의사결정→docs로 분류한다.
3. 중복·오래된·충돌 규칙을 식별한다.
4. **제0지침과 출처 정책은 보존한다.**
5. 최적화된 CLAUDE.md 초안을 만든다.

## 출력 형식
1. 삭제할 항목 2. 이동할 항목 3. 유지할 항목 4. 새로/업데이트할 파일 5. 최적화된 CLAUDE.md 초안 6. 위험한 변경 여부 7. 사람 승인 필요 여부

## 멈춰야 하는 지점
- 실제 수정 전 반드시 사람 승인을 요청한다.
- 제0지침을 삭제·약화하지 않는다.

## 레퍼런스 규칙
`.claude/rules/documentation.md` 준수.
