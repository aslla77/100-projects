---
name: write-adr
description: 중요한 기술/아키텍처 결정을 기록할 때 사용. adr/0000-template.md를 복사해 선택지·트레이드오프·출처가 담긴 ADR을 작성한다.
---

# write-adr

## 목적
되돌리기 어렵거나 영향이 큰 결정을 ADR로 남긴다.

## 읽어야 할 파일
- adr/0000-template.md, 기존 adr/*
- planning/*, docs/architecture/architecture-overview.md

## 업데이트할 파일
- adr/000N-<slug>.md (다음 번호)
- architecture-overview.md (링크 추가)

## 절차
1. 템플릿을 복사해 다음 번호로 만든다.
2. 배경·결정·검토한 선택지·결과·재검토 조건을 채운다.
3. 각 선택지에 출처(공식 문서 우선)를 단다.
4. 상태(제안/승인/폐기/대체)를 명시한다.

## 출력 형식
- 작성한 ADR 경로, 결정 요약, References

## 멈춰야 하는 지점
- 결정이 불확실하면 "제안됨" 상태로 두고 사람 검토를 요청한다.

## 레퍼런스 규칙
공식 문서·표준 우선. Nygard ADR 형식 준수.
