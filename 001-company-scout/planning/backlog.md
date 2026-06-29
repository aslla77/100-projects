# 백로그

Gate 3. build 착수(사람 승인 후) 시 위에서부터.

## B1. 플러그인 스캐폴드 (Must)
- `src/.codex-plugin/plugin.json` (name: company-scout, version, description, "skills": "./skills/") [2]
- `src/skills/company-scout/SKILL.md` (name/description frontmatter + 절차 본문)
- `src/README.md` (제출 5문항 초안)

## B2. SKILL.md 본문 (Must)
- 5축 수집 절차, 검색 출발점, 출처 등급 규칙(A/B/C), 제0지침(공개자료만·근거부족 표기).
- 출력 스키마 정의(회사/제품/고객/문제/관련회사 + References + 근거부족).
- 문제 후보 형식(문제 한 줄 / 공개URL / Codex 적합성).

## B3. 출처-완전성 점검 (Should)
- SKILL.md 체크리스트로 우선 구현. 필요 시 작은 스크립트(문제 후보 URL 누락 검출).

## B4. 파일럿 검증 (Must)
- 마이리얼트립으로 1회 실행 → dossier가 `research/research-brief.md` 수준 품질·출처 충족 확인.
- 수락 기준(prd-lite) 체크.

## B5. (Could) 2번째 회사 시연 / 더미 데이터 예시

## 미해결(검증 후 확정)
- SKILL.md 권장 길이·섹션 컨벤션(OpenAI /codex/skills 문서 추가 확인).
- 공개 항공/상품 데이터 소스 가용성(필요 시).

## References
- [2] OpenAI Codex Build plugins: https://developers.openai.com/codex/plugins/build — A
- `planning/prd-lite.md`, `research/research-brief.md`
