---
name: new-project
description: 새 프로젝트를 시작할 때 사용. 템플릿을 복사해 Projects/<slug>/를 만들고 README와 brief를 채우며 위험도 등급을 지정한다. 아직 코딩하지 않는다.
---

# new-project

## 목적
아이디어를 받아 프로젝트 폴더와 intake 산출물을 생성하고 위험도 등급을 지정한다.

## 읽어야 할 파일
- 상위 `Projects/CLAUDE.md`
- `Projects/_shared/templates/PROJECT_CREATION_GUIDE.md`
- 사용자가 준 프로젝트 정보(이름/아이디어/타깃/목표/유형/기술 스택)

## 업데이트할 파일
- `Projects/<slug>/README.md`
- `Projects/<slug>/brief/product-brief.md`, `problem-definition.md`, `success-metrics.md`
- `Projects/<slug>/CLAUDE.md` (미션·위험도 등급)
- `Projects/<slug>/.project-state.md`

## 절차
1. `_templates/project-template/`를 `Projects/<NNN-slug>/`로 복사한다. 폴더명은 자동 넘버링(3자리)+slug 형식이다 (`_shared/scripts/new-project.sh <slug>`). 넘버링이 불필요하면 `--no-num`.
2. 사용자가 준 정보로 README와 brief를 채운다. 모르는 값은 "확인 필요"로 둔다.
3. 위험도 등급(Tier 0~3)을 근거와 함께 지정한다.
4. .project-state.md를 생성/갱신한다.
5. 부족한 정보를 열린 질문으로 정리한다.

## 출력 형식
- 생성한 파일 목록, 지정한 위험도 등급(근거), 열린 질문, 다음 추천 스킬(run-discovery)

## 멈춰야 하는 지점
- 코딩으로 넘어가지 않는다. intake까지만.

## 레퍼런스 규칙
사실을 지어내지 않는다. 모르면 "확인 필요". `reference-policy.md` 준수.
