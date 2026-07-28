# Claude Code — 게이트 기반 프로젝트 파이프라인

아이디어 하나를 릴리즈까지 끌고 가는 워크플로우를, Claude Code의 스킬 · 서브에이전트 · 규칙 파일로 구현한 세트입니다.

```
intake → research → planning → redteam → (사람 승인) → build → review → qa → security → sync-docs → release → ops
```

핵심 아이디어는 **모든 판단을 파일 존재 여부와 문서 내용에만 근거한다**는 것입니다. 에이전트가 기억이나 추측으로 "다 됐다"고 말하지 못하게 하고, 각 단계가 정해진 산출물을 남겨야 다음 단계로 넘어갑니다.

## 설치

프로젝트 루트에서:

```bash
git clone --depth 1 https://github.com/aslla77/100-projects.git /tmp/100p
mkdir -p .claude
cp -R /tmp/100p/skills/claude-code/skills  .claude/
cp -R /tmp/100p/skills/claude-code/agents  .claude/
cp -R /tmp/100p/skills/claude-code/rules   .claude/
mkdir -p docs && cp -R /tmp/100p/skills/claude-code/docs docs/workflow
```

계정 전체에서 쓰려면 `.claude/` 대신 `~/.claude/`에 두면 됩니다. 스킬과 서브에이전트는 Claude Code가 이 경로를 자동으로 읽습니다.

`rules/`는 Claude Code의 내장 기능이 아니라 이 프로젝트의 관례입니다. 프로젝트 `CLAUDE.md`에서 상황별로 어떤 규칙 파일을 읽을지 가리켜 주면 동작합니다.

## 쓰는 법

개별 스킬 이름을 외울 필요 없이 하나만 실행하면 됩니다:

```
/project-pipeline
```

현재 상태(`.project-state.md` + 실제 파일)를 점검해 지금 어느 게이트에 있는지 판정하고, 다음에 실행할 스킬을 실행하거나 추천합니다. **사람 승인이 필요한 지점에서는 멈춥니다** — planning → build 전환, 릴리즈·배포 직전, 보안 변경, 데이터 마이그레이션, 비용 발생 작업.

## 스킬 목록

### 오케스트레이션
| 스킬 | 언제 쓰나 |
|---|---|
| `project-pipeline` | 최상위 진입점. 상태를 보고 다음 스킬을 결정·실행한다 |
| `decide-next-skill` | 현재 상태를 게이트에 매핑해 다음 스킬만 결정한다 |
| `new-project` | 새 프로젝트 폴더를 만들고 brief를 채우며 위험도 등급을 정한다 |

### 단계별 실행
| 스킬 | 언제 쓰나 |
|---|---|
| `run-discovery` | 리서치 — research-brief와 source-log를 만든다 |
| `run-planning` | 기획 — PRD-lite, 사용자 흐름, 기능 범위, 백로그, 리스크 |
| `run-redteam` | 코딩 전 계획을 공격해 허점을 찾는다 |
| `run-build` | 승인된 범위만 작은 단위로 구현한다 |
| `run-review` | 코드 리뷰 — 수정 우선순위와 release blocker를 정한다 |
| `run-qa` | test-plan과 qa-report를 만들고 정상·예외·회귀를 검증한다 |
| `run-security-review` | 인증·권한·입력값·비밀키·의존성을 점검한다 |
| `prepare-release` | release-plan / rollback-plan / release-notes를 만든다 |

### 문서·회고
| 스킬 | 언제 쓰나 |
|---|---|
| `write-adr` | 중요한 기술 결정을 선택지·트레이드오프·출처와 함께 기록한다 |
| `sync-docs` | 코드와 문서가 어긋나지 않게 맞춘다 |
| `optimize-claude-md` | 길어진 CLAUDE.md를 줄이고 skills/rules/docs로 나눈다 |
| `capture-session-learnings` | 세션에서 얻은 교훈을 알맞은 파일에 반영한다 |
| `create-postmortem` | 장애 후 비난 없는(blameless) 포스트모템을 쓴다 |

### 도메인
| 스킬 | 언제 쓰나 |
|---|---|
| `company-scout` | 회사 1곳을 공개 자료만으로 구조화해 출처 검증 보고서를 만든다 |

## 서브에이전트

`agents/`에 9개가 들어 있고, 위 스킬들이 이들을 불러 씁니다.

`research-analyst` · `planner-architect` · `plan-redteam` · `ui-designer` · `coder` · `code-reviewer` · `security-reviewer` · `test-qa` · `release-ops`

## 규칙

`rules/`의 `00-zero-principle.md`가 다른 모든 규칙보다 우선합니다. 나머지는 영역별로 나뉘어 있습니다 — `coding` · `testing` · `security` · `design` · `release` · `documentation` · `research` · `planning` · `workflow` · `reference-policy`.

## 위험도 등급

절차의 무게를 여기서 결정합니다. 과설계를 막는 장치입니다.

| 등급 | 기준 | 필수 절차 |
|---|---|---|
| Tier 0 | 장난감·실험·로컬·사용자 데이터 없음 | 최소 절차 |
| Tier 1 | 공개 데모·가벼운 사용자 입력 | 기본 QA, 기본 보안 점검 |
| Tier 2 | 로그인·사용자 데이터·외부 API·결제 가능성 | 보안 리뷰 + 테스트 + 릴리즈 플랜 |
| Tier 3 | 실제 서비스·민감 데이터·유료 SaaS | 위협 모델링 + 롤백 + 운영 문서 + SLO |

## 더 읽기

- [`docs/gates.md`](./docs/gates.md) — 각 게이트의 통과 조건
- [`docs/project-lifecycle.md`](./docs/project-lifecycle.md) — 전체 수명 주기
- [`docs/reference-policy.md`](./docs/reference-policy.md) — 출처 등급(A/B/C)과 인용 규칙
- [`docs/fact-assumption-opinion.md`](./docs/fact-assumption-opinion.md) — 사실·가정·의견·추천 구분법

## References

- Anthropic — Claude Code Skills: https://code.claude.com/docs/en/skills
- Anthropic — Claude Code Subagents: https://code.claude.com/docs/en/sub-agents
- Anthropic — Claude Code Memory (CLAUDE.md): https://code.claude.com/docs/en/memory
