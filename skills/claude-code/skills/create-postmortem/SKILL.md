---
name: create-postmortem
description: 운영 중 장애가 발생한 후 사용. postmortem-template을 복사해 비난 없는(blameless) 포스트모템을 작성하고 액션 아이템을 정리한다.
---

# create-postmortem

## 목적
장애의 원인·영향·타임라인·재발 방지책을 사실 기반으로 기록한다.

## 읽어야 할 파일
- ops/postmortem-template.md, ops/incident-log.md, ops/runbook.md
- 관련 로그·모니터링 기록

## 업데이트할 파일
- ops/postmortem-<slug>.md (새 파일)
- ops/incident-log.md (링크 연결)

## 절차
1. 템플릿을 복사한다.
2. 요약·영향·타임라인을 사실대로 채운다.
3. 근본 원인을 분석한다 (추측은 가정으로 표시).
4. 잘된 점·부족한 점·액션 아이템·재발 방지책을 정리한다.
5. incident-log에 포스트모템 링크를 연결한다.

## 출력 형식
- 포스트모템 경로, 근본 원인, 액션 아이템 표, References

## 멈춰야 하는 지점
- 원인이 불확실하면 단정하지 말고 가정으로 표시하고 추가 조사 항목으로 남긴다.

## 레퍼런스 규칙
비난 없이 사실 기반으로. 모니터링 근거를 첨부한다.
