---
name: project-pipeline
description: 최상위 오케스트레이터. /project-pipeline 하나로 현재 프로젝트 상태를 점검하고 다음에 실행할 스킬을 위에서부터 순서대로 실행하거나 추천한다. 개별 스킬을 외우지 않아도 된다. 사람 승인 게이트에서는 멈춘다.
---

# project-pipeline

## 목적
사용자가 개별 스킬을 기억하지 않아도 되도록, 현재 상태를 점검하고 다음 스킬을 결정·실행/추천하는 단일 진입점.

## 핵심 원칙 (제0지침)
- 실제 앱 코딩을 바로 시작하지 않는다. **먼저 상태를 읽고 판단한다.**
- 모르면 모른다고 한다. 산출물이 없으면 없다고 한다.
- 추론은 "가정"으로 표시한다.
- 모든 판단은 **파일 존재 여부와 문서 내용**에 근거한다. 가짜 완료 상태 금지.
- 사람 승인 게이트에서는 반드시 멈춘다.
- 보안·릴리즈·배포·데이터 삭제·대규모 코드 변경은 자동 진행하지 말고 승인 요청 후 멈춘다.
- 커뮤니티/블로그는 단서로만, 중요한 판단은 공식 문서·내부 산출물 우선.

## 읽어야 할 파일
- `.project-state.md` (없으면 생성)
- README.md, CLAUDE.md
- brief/, research/, planning/, adr/, tests/, security/, release/, ops/
- `.claude/rules/workflow.md`, `docs/workflow/gates.md`

## 업데이트할 파일
- `.project-state.md` (실행 전후)

## 절차
1. **위치 확인** — 현재 위치가 `Projects/` 루트인지, 특정 프로젝트 폴더인지 확인한다.
   - 루트면: 어떤 프로젝트를 다룰지 묻거나, 새 프로젝트 정보가 주어졌으면 `new-project`로 시작.
2. **상태 파일 확인** — `.project-state.md`가 있는지 확인한다.
3. **없으면 생성** — 템플릿 형식으로 만들되 **현재 확인 가능한 내용만** 채운다. 모르는 값은 Unknown.
4. **산출물 스캔** — README.md, CLAUDE.md, brief/, research/, planning/, adr/, tests/, security/, release/, ops/ 의 존재 여부와 핵심 내용을 확인한다.
5. **현재 gate 판정** — 위에서부터 첫 번째로 충족 안 된 gate를 현재 gate로 한다 (Gate 0~12).
6. **다음 스킬 결정** — `decide-next-skill`로 다음 스킬(또는 멈춤/질문)을 정한다.
7. **실행 가능하면 실행** — 자동 진행 가능한 스킬이면 실행한다.
8. **승인 필요하면 멈춤** — Gate 5(planning 승인), 릴리즈/배포, 보안 변경, 대규모 변경, 데이터 삭제는 실행하지 않고 승인 요청.
9. **상태 갱신** — 실행 후 `.project-state.md`를 실제 증거(파일 경로)와 함께 갱신한다.
10. **요약** — 현재 gate, 한 일, 증거, 다음 추천 스킬, 승인 필요 여부를 요약한다.

## 새 프로젝트 시작 입력 (이 형식이 오면 new-project부터)
```text
프로젝트 이름: ...
프로젝트 아이디어: ...
타깃 사용자: ...
목표: ...
프로젝트 유형: [SaaS / 웹앱 / 모바일 앱 / 재미용 사이트 / 내부 도구 / 프로토타입]
선호 기술 스택: [없으면 추천]
```

## 게이트 순서 (요약)
Gate 0 미생성→new-project / 1 intake→new-project·run-discovery / 2 research→run-discovery / 3 planning→run-planning / 4 redteam→run-redteam / 5 **승인(멈춤)** / 6 build→run-build / 7 review→run-review / 8 qa→run-qa / 9 security(Tier2+)→run-security-review / 10 docs→sync-docs / 11 release→prepare-release / 12 ready→다음 목표 질문
(상세 판정 조건: `decide-next-skill`)

## 출력 형식
1. 현재 위치 (루트/프로젝트)
2. 현재 Gate (번호+이름) + 판정 근거(증거 파일)
3. 이번에 실행한 스킬 (없으면 "없음 — 이유")
4. `.project-state.md` 갱신 요약
5. 다음 추천 스킬 / 멈춤 사유
6. 사람 승인 필요 여부

## 멈춰야 하는 지점
- Gate 5(planning→build 승인), 릴리즈/배포, 보안 변경, 데이터 삭제·마이그레이션, 대규모 코드 변경.
- 판정 근거가 불충분하면 추측하지 말고 질문한다.

## 레퍼런스 규칙
`.claude/rules/workflow.md`, `docs/workflow/gates.md`, `reference-policy.md`를 따른다.
