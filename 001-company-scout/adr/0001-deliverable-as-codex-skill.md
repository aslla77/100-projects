# ADR 0001: 산출물 형태 = Codex 스킬(SKILL.md 주도) 플러그인

## 상태
제안됨 (날짜: 2026-06-28) — planning→build 사람 승인 대기

## 배경 (Context)
- 예선 제출물은 **Codex 플러그인**이어야 한다(`src/.codex-plugin/plugin.json` 필수). 플러그인은 skills·MCP servers·apps를 담을 수 있다 [1][2].
- `company-scout`의 핵심 가치는 "공개 출처 기반 회사 분석 방법론"이며, 이는 본질적으로 **에이전트 지시문(절차·규칙·스키마)** 으로 표현된다. 무거운 서버 로직이 필수는 아니다.
- Tier 0, 과설계 금지, 마감(2026-07-10) 압박.

## 결정 (Decision)
- MVP는 **SKILL.md 주도 스킬**로 구현한다: `src/skills/company-scout/SKILL.md`에 5축 수집 절차·출처 등급 규칙·출력 스키마를 담고, `src/.codex-plugin/plugin.json`이 `"skills": "./skills/"`로 가리킨다 [2].
- MCP 서버(`.mcp.json`)·헬퍼 스크립트는 **필요해질 때만** 추가(출처-완전성 점검 등). 처음부터 만들지 않는다.

## 검토한 선택지 (Options considered)
| 선택지 | 장점 | 단점 | 출처 |
|---|---|---|---|
| A (채택) SKILL.md 주도 | 규격 부합·최소 구현·방법론을 그대로 인코딩·빠름 | 복잡한 결정 로직은 지시문 한계 | [2] |
| B MCP 서버 중심 | 결정론적 수집·검증 로직 가능 | 과설계·구현/배포 비용·Tier0 부적합 | [2] |
| C 독립 스크립트(플러그인 외부) | 자유로움 | **예선 규격 위반**(플러그인 아님) | [1] |

## 결과와 영향 (Consequences)
- 긍정: 예선 포맷 연습 동시 달성, 빠른 end-to-end, 방법론 재사용.
- 트레이드오프: 출처-완전성 같은 결정론적 보장은 SKILL.md 체크리스트로 시작 → 약하면 작은 스크립트로 보강(B3).

## 되돌리거나 재검토할 조건
- SKILL.md 지시만으로 출처 누락·환각이 반복되면 → 헬퍼 스크립트/MCP로 검증 로직 이관.

## References
- [1] OpenAI Codex — Plugins(개요): https://developers.openai.com/codex/plugins — A (확인일 2026-06-28)
- [2] OpenAI Codex — Build plugins(구조·plugin.json·skills): https://developers.openai.com/codex/plugins/build — A (확인일 2026-06-28)
