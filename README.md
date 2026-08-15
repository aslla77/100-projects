# 100 Projects

> **100개의 프로젝트를 만들어 가는 개인 프로젝트 시리즈입니다. (진행 중)**
>
> 각 프로젝트는 아이디어 → 리서치 → 기획 → 검증 → 구현 → 릴리즈로 이어지는
> 게이트 기반 워크플로우로 만들어집니다. 이 저장소에는 **각 프로젝트의 개발 일지(devlog)** 를 공개합니다.
> 실제 소스·자격증명·계정 정보 등은 공개하지 않으며, 여기 담긴 것은 "무엇을 왜 어떻게 만들었는가"의 기록입니다.

## 진행 상황

| 항목 | 값 |
|---|---|
| 목표 | 프로젝트 100개 |
| 진행 | **8개** (#001~#009, 일지 공개 8개) |
| 상태 | 🚧 Work in Progress |

## 프로젝트 인덱스

| # | 프로젝트 | 한 줄 소개 | 상태 | 개발 일지 |
|---|---|---|---|---|
| 001 | **company-scout** | 회사명 하나로 공개 자료만 써서 기업을 6개 축으로 구조화하는 출처 검증 리서치 도구 | MVP | [devlog](./devlog/001-company-scout.md) |
| 002 | **하루 한 점 (Daily Relic)** | 매일 박물관 3D 유물 한 점을 감성 해설과 함께 감상하는 iOS 앱 | App Store 출시 | [devlog](./devlog/002-daily-relic.md) |
| 003 | **Weather Woof (날씨멍)** | 날씨에 맞춰 옷 입은 시바견 캐릭터가 오늘 날씨를 브리핑하는 iOS 날씨 앱 | 출시 실패 · 개인 사용 | [devlog](./devlog/003-weather-woof.md) |
| 004 | **Islet** | 할 일을 다이나믹 아일랜드·잠금화면에 고정하고 Notion과 연동하는 iOS 생산성 앱 | App Store 출시 | [devlog](./devlog/004-islet.md) |
| 005 | **무럭무럭 (Mureok)** | 물주기와 사진을 기록하면 기기 안에서 성장 타임랩스가 만들어지는 식물 기록 앱 | 심사 중 | [devlog](./devlog/005-mureok.md) |
| 006 | **Readable Name** | 무의미한 문서 파일명을 문서 안의 제목으로 바꿔 주는 로컬 데스크톱 앱 — 홀드아웃 43.8%를 보고 구현 전에 접었다 | 중단 | [devlog](./devlog/006-readable-name.md) |
| 007 | **스튜디오 사이트** | 프레임워크 없이 만든 정적 사이트 — 스토어 심사 요구에서 출발했다 | 라이브 | [devlog](./devlog/007-studio-site.md) |
| 008 | _진행 중_ | — | 작업 중 | — |
| 009 | **Adaptive Upskill** | 가르치기 전에 먼저 실력을 측정하고, 아는 건 건너뛰고 모르는 것부터 가르치는 AI 학습 스킬 | 공개 (MIT) | [devlog](./devlog/009-adaptive-upskill.md) |
| 010–100 | _예정_ | — | 계획 중 | — |

## 스킬 가져다 쓰기

프로젝트를 만들면서 실제로 쓰고 있는 **AI 에이전트 스킬**을 [`skills/`](./skills/)에 따로 모아 공개합니다. MIT 라이선스이니 자유롭게 복사해서 쓰세요.

| 폴더 | 대상 | 내용 |
|---|---|---|
| [`skills/claude-code/`](./skills/claude-code/) | Claude Code | 게이트 기반 프로젝트 파이프라인 (스킬 17 · 서브에이전트 9 · 규칙 11) |
| [`skills/codex/company-scout/`](./skills/codex/company-scout/) | OpenAI Codex | 회사 1곳을 공개 자료만으로 구조화하는 플러그인 |
| [aslla77/adaptive-upskill](https://github.com/aslla77/adaptive-upskill) ↗ | Agent Skills 호환 전반 | 가르치기 전에 실력을 먼저 측정하는 학습 스킬 (#009). 갱신이 잦아 **별도 저장소**에 두고 여기서는 링크만 겁니다 |

## 공통 원칙 (제0지침)

모든 프로젝트는 다음을 따릅니다.

1. 모르면 모른다고 한다. 섣부른 추론을 하지 않는다.
2. 사실 주장에는 공개 출처를 붙인다. 근거가 부족하면 "근거 부족"으로 표시한다.
3. 사실 · 가정 · 의견 · 추천을 구분해서 작성한다.
4. 위험도 등급(Tier 0~3)에 맞는 절차만 적용한다 — 과설계 금지.

## 워크플로우

```
intake → research → planning → redteam → (사람 승인) → build → review → qa → security → sync-docs → release → ops
```

---

각 프로젝트의 자세한 이야기는 [`devlog/`](./devlog/) 를 참고하세요.
