# Rule: 워크플로우 & 상태 체크

## 단계 순서
intake → research → planning → redteam → (사람 승인) → build → review → qa → security → sync-docs → release → ops

## 게이트 (충족 못 하면 멈춤)
상세: `docs/workflow/gates.md`. 핵심: 각 게이트는 다음 단계 전 산출물을 강제한다.

## 상태 체크 규칙 (project-pipeline 용)
- 모든 단계 판단은 **파일 존재 여부와 문서 내용**에 근거한다. 기억·추측 금지.
- 산출물이 없으면 "없다"고 말한다. 가짜 완료 상태를 만들지 않는다.
- 추론이 필요하면 "가정"으로 표시한다.
- 작업 시작 전 `.project-state.md`를 읽고(없으면 생성), 현재 gate를 판단한다.
- 단계 완료 후 `.project-state.md`를 실제 증거(파일 경로)와 함께 갱신한다.
- 단계를 건너뛰지 않는다. 위에서부터 순서대로 진행한다.

## 사람 승인 게이트 (자동 진행 금지, 멈춤)
- planning → build 전환 전 (Gate 5)
- 릴리즈 / 배포 직전
- 보안 변경, 데이터 삭제·마이그레이션, 대규모 코드 변경, 비용 발생 작업

## 위험도 등급
Tier 0~3에 따라 절차 무게 조절. 과설계 금지. 상위 `Projects/CLAUDE.md` 참조.

## References
- `docs/workflow/gates.md`
- `docs/workflow/project-lifecycle.md`
