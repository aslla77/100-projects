# 개발 일지 (devlog)

100 Projects 시리즈의 각 프로젝트를 **어떤 문제에서 출발해, 무엇을 어떻게 만들었고, 무엇을 배웠는지** 기록합니다.

이 일지는 실제 소스코드·자격증명·계정 정보·상용 데이터를 포함하지 않습니다.
게이트 기반 워크플로우(intake → research → planning → build → release)를 따라
"만드는 과정 자체"를 남기는 것이 목적입니다.

| # | 프로젝트 | 분야 | 상태 | 일지 |
|---|---|---|---|---|
| 001 | company-scout | 리서치 도구 / AI 에이전트 | MVP | [보기](./001-company-scout.md) |
| 002 | Daily Relic (하루 한 점) | iOS · Android · Flutter · 문화유산 | iOS · Android 출시 (업데이트 심사 중) | [보기](./002-daily-relic.md) |
| 003 | Weather Woof (날씨멍) | iOS · Flutter · 날씨 | 출시 실패 · 개인 사용 | [보기](./003-weather-woof.md) |
| 004 | Islet | iOS · Swift · 생산성 | App Store 출시 | [보기](./004-islet.md) |
| 005 | 무럭무럭 (Mureok) | iOS · Android · Flutter · 라이프스타일 | iOS · Android 출시 (1.1.5 심사 중) | [보기](./005-mureok.md) |
| 006 | Readable Name | 데스크톱 앱 · Rust · 파일명 복구 | 중단 (구현 전) | [보기](./006-readable-name.md) |
| 007 | 스튜디오 사이트 | 웹 · 정적 사이트 | 라이브 | [보기](./007-studio-site.md) |
| 008 | 언제했지 (When'd I) | iOS · Android · Flutter · 기록 | iOS · Android 출시 (v2.x · 10개 언어) | [보기](./008-when-did-i.md) |
| 009 | Adaptive Upskill | AI 에이전트 스킬 · 학습 시스템 | 공개 (v0.3) | [보기](./009-adaptive-upskill.md) |
| 010 | 바로앨범 (BaroAlbum) | iOS · Android · Flutter · 카메라 | iOS · Android 출시 | [보기](./010-baro-album.md) |
| 011 | 홍보 쇼츠 파이프라인 | 영상 · 마케팅 자동화 · Python | 실험 중 | [보기](./011-promo-shorts.md) |
| 012 | 쉼호흡 (Breathest) | iOS · Android · Flutter · 웰니스 | iOS 출시 · Android 심사 중 | [보기](./012-breath-bell.md) |
| 013 | 총괄센터 (Studio HQ) | 데이터 · Python · 로컬 대시보드 | MVP 가동 중 | [보기](./013-studio-hq.md) |

## 공통 제작 방식

모든 프로젝트가 같은 "프로젝트 공장" 규칙을 공유합니다.

- **게이트 기반 진행** — 각 단계(리서치·기획·레드팀·빌드·리뷰·QA·보안·릴리즈) 사이에 승인 지점을 둔다.
- **위험도 등급(Tier 0~3)** — 로컬 실험(Tier 0)과 결제·계정이 걸린 앱(Tier 2)에 다른 무게의 절차를 적용한다. 과설계 금지.
- **출처 원칙** — 사실 주장에는 공개 출처를 붙이고, 근거가 부족하면 "근거 부족"으로 표시한다.
- **문서 우선** — ADR(아키텍처 결정 기록), brief, planning, release 문서를 코드와 함께 남긴다.
