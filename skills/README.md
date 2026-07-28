# skills — 공개 스킬 모음

이 폴더는 [100 Projects](../README.md) 시리즈에서 실제로 쓰고 있는 **AI 에이전트 스킬**을 누구나 가져다 쓸 수 있게 따로 모아둔 곳입니다.
비공개로 관리하는 작업 저장소에서 스킬 파일만 뽑아 온 것이며, 개인정보·비밀키·로컬 경로·실제 산출물은 포함되어 있지 않습니다.

## 무엇이 들어 있나

| 폴더 | 대상 | 내용 |
|---|---|---|
| [`claude-code/`](./claude-code/) | Claude Code | 게이트 기반 프로젝트 파이프라인 — 스킬 17개 + 서브에이전트 9개 + 규칙 11개 |
| [`codex/company-scout/`](./codex/company-scout/) | OpenAI Codex | 회사 1곳을 공개 자료만으로 구조화하는 플러그인 |

## 이 스킬들의 공통 원칙 (제0지침)

전부 같은 원칙 위에 세워져 있습니다. 스킬을 읽기 전에 이것부터 보면 이해가 빠릅니다.

1. 모르면 모른다고 한다. 아는 척하지 않는다.
2. 섣부른 추론을 금지한다. 추론이 필요하면 먼저 질문하거나 "가정"으로 표시한다.
3. 사실 주장에는 출처를 붙인다. 커뮤니티·블로그·유튜브·위키는 단서로만 쓴다.
4. 사실 · 가정 · 의견 · 추천을 구분해서 쓴다.
5. 가짜 완료 상태를 만들지 않는다. 검증한 것만 "했다"고 말한다.
6. 위험도 등급(Tier 0~3)에 맞는 절차만 적용한다 — 과설계 금지.

전문: [`claude-code/rules/00-zero-principle.md`](./claude-code/rules/00-zero-principle.md)

## 라이선스

MIT — [`LICENSE`](./LICENSE) 참고. 자유롭게 복사·수정해서 쓰세요.

## 알아두면 좋은 점

- 문서는 **한국어**로 작성되어 있습니다.
- 스킬 본문은 실제 사용 중인 원본 그대로입니다. 그래서 일부 문서에는 이 프로젝트가 시작된 계기였던 공모전(AX 인재전쟁) 관련 서술이 `(선택)` 표시와 함께 남아 있습니다. 범용으로 쓸 때는 무시하거나 지워도 됩니다.
- 스킬은 서로를 이름으로 참조합니다(`project-pipeline` → `decide-next-skill` → 각 `run-*`). 일부만 골라 쓰면 참조가 끊길 수 있으니, 세트로 가져간 뒤 필요 없는 것을 지우는 쪽을 권합니다.

## References

- Anthropic — Claude Code Skills: https://code.claude.com/docs/en/skills
- Anthropic — Claude Code Subagents: https://code.claude.com/docs/en/sub-agents
- Anthropic — Claude Code Memory (CLAUDE.md): https://code.claude.com/docs/en/memory
- OpenAI — Codex: Build plugins: https://developers.openai.com/codex/plugins/build
