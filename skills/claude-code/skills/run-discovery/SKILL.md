---
name: run-discovery
description: 리서치(discovery) 단계를 실행할 때 사용. research-analyst로 사실을 수집하고 research-brief와 source-log를 작성한다. 출처 없는 사실을 만들지 않는다.
---

# run-discovery

## 목적
부족한 정보를 식별하고 공신력 있는 출처로 채워 research-brief/source-log를 작성한다 (Gate 2).

## 읽어야 할 파일
- README.md, brief/*
- `docs/00-principles/reference-policy.md`, `.claude/rules/research.md`
- 기존 research/* (있으면)

## 업데이트할 파일
- research/research-brief.md
- research/source-log.md
- research/competitor-comparison.md (필요 시)

## 절차
1. research-analyst 에이전트를 사용한다.
2. 열린 질문을 만든다.
3. 공식 문서부터 조사하고 모든 출처를 source-log에 등급과 함께 기록한다.
4. 사실/가정/의견을 분리해 research-brief에 정리한다.
5. 근거 부족 부분은 "근거 부족"으로 명시한다.

## 출력 형식
- 핵심 발견, 사실/가정/의견, 열린 질문, 추천 방향, References

## 멈춰야 하는 지점
- 사실을 단정할 출처가 없으면 추측하지 말고 확인 필요로 남긴다.

## 레퍼런스 규칙
`reference-policy.md`, `.claude/rules/research.md` 준수.
