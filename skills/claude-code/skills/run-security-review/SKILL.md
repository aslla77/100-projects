---
name: run-security-review
description: 보안 리뷰를 실행할 때 사용. security-reviewer로 인증·권한·입력값·비밀키·데이터·의존성을 점검한다. Tier 2 이상은 threat-model과 dependency-review를 작성한다.
---

# run-security-review

## 목적
보안 리스크를 점검하고 release blocker를 정한다 (Gate 5, Tier 2+ 필수).

## 읽어야 할 파일
- CLAUDE.md, README.md, planning/*, adr/*
- 기존 security/*, 의존성 파일(package.json 등), 환경변수 예시
- 인증/권한/API/데이터 코드, 배포 설정
- `.claude/rules/security.md`, `reference-policy.md`

## 업데이트할 파일
- security/security-review.md
- Tier 2+ : security/threat-model.md, security/dependency-review.md

## 절차
1. 위험도 등급을 먼저 확인한다.
2. security-reviewer 에이전트로 13개 항목을 점검한다.
3. 코드에서 확인한 사실과 가능성 있는 리스크를 구분한다.
4. release blocker와 수정 우선순위를 정한다.

## 출력 형식
- security-review(.md), (Tier2+ threat-model, dependency-review), blocker 목록, 우선순위, References

## 멈춰야 하는 지점
- 보안 변경은 사람 승인 후. 심각한 취약점은 blocker로 처리하고 release ready라고 말하지 않는다.

## 레퍼런스 규칙
OWASP·CVE·NVD·벤더 문서 우선. 커뮤니티는 단서로만.
