# 004 · Islet — 할 일을 다이나믹 아일랜드에 고정하는 앱

> 할 일 목록을 **다이나믹 아일랜드·잠금화면**에 Live Activity로 고정하고,
> 앱을 열지 않고도 할 일을 완료하거나 메모를 남길 수 있는 iOS 생산성 앱.
> 원한다면 **Notion**과 연동한다.

- **분야:** iOS · Swift / SwiftUI · 생산성
- **위험도:** Tier 2 (외부 API 연동 · OAuth)
- **상태:** App Store 출시 — v1.2.x 업데이트 운영 중 (하루 시작 시간·세션 알람·iCloud 백업 등, 1.2.3 크래시 수정 제출)

## 왜 만들었나

할 일 앱의 가장 큰 마찰은 "**앱을 열어야 한다**"는 것이다.
할 일은 이미 머릿속에 있는데, 확인하고 체크하려면 앱을 켜고 목록을 찾아 들어가야 한다.
iPhone의 다이나믹 아일랜드와 잠금화면은 이미 늘 보이는 표면이다.
여기에 할 일을 **상시 고정**하면, 앱을 여는 마찰 자체가 사라진다.

## 무엇을 만들었나

- **Live Activity 고정** — 할 일 목록을 다이나믹 아일랜드와 잠금화면에 상주시킨다.
- **인앱 밖 상호작용** — 앱을 열지 않고 할 일을 완료 처리하거나 빠른 메모를 남긴다.
- **Notion 연동(선택)** — 공식 Notion API로 사용자의 Notion과 양방향 동기화.

기술적으로는:

- **네이티브 Swift / SwiftUI** — 서드파티 의존성 0.
- **StoreKit 2** 로 결제(Pro) 처리.
- **Notion 공식 OAuth** — 사용자가 자신의 Notion 워크스페이스를 직접 연결(공개 OAuth 플로우).
- **무상태 토큰 교환 프록시** — OAuth 코드↔토큰 교환만 담당하는 서버리스 프록시.
  **클라이언트 시크릿은 앱이 아니라 서버(프록시)에만 둔다.** 앱에는 공개 가능한 값만 담긴다.

## 만드는 과정

- **스파이크** — Live Activity와 Notion API 연동 가능성을 먼저 프로토타입으로 검증.
- **아키텍처 결정(ADR)** — OAuth 토큰 교환을 앱이 아니라 프록시로 옮기는 구조를 문서로 확정.
- **보안 리뷰** — 위협 모델링 + 토큰·시크릿 취급 점검(Tier 2 필수 절차).
- **릴리즈** — 릴리즈/롤백 플랜, 개인정보 처리방침·이용약관 준비 후 심사 제출.

## 배운 점

- **"앱을 안 열게 만드는 것"이 생산성 앱의 핵심 기능이다.** Live Activity는 화면이 아니라
  마찰 제거 장치다.
- **OAuth 시크릿은 절대 클라이언트에 두지 않는다.** 클라이언트 시크릿을 앱 번들에 넣으면
  누구나 추출할 수 있다. 무상태 프록시로 교환만 대행하고, 시크릿은 서버 시크릿 스토어에만 둔다.
  이 원칙 때문에 아키텍처를 프록시 구조로 새로 잡았다.
- **의존성 0의 값어치.** 서드파티 SDK 없이 StoreKit 2·Notion 공식 API만 쓰니
  보안 표면과 유지보수 부담이 크게 줄었다.
- **자격증명 위생.** 개발 중 쓰던 토큰은 릴리즈 전 반드시 폐기(revoke)하고,
  시크릿은 코드가 아닌 시크릿 스토어에만 둔다 — 이걸 릴리즈 체크리스트로 못 박았다.

## 출시 후

- **v1.2.3 — "가끔 강제 종료"를 잡았다.** 아일랜드에서 완료 버튼을 연타하거나 Notion 쪽 할 일을
  빠르게 지울 때 앱이 죽는다는 보고가 있었다. 원인은 동기화 큐였다. 큐를 위치 인덱스로 순회하며
  서버 호출을 `await`한 뒤 같은 인덱스로 항목을 지우고 있었는데, Swift actor는 데이터 경쟁은 막지만
  **재진입은 막지 않는다.** 두 flush가 겹치면 뒤의 것이 큐를 비운 뒤 앞의 것이 없는 인덱스를 지우려다
  죽었고, 부작용으로 같은 완료 요청이 두 번 나갔다. 원본 파일 그대로 macOS 단독 스크립트에
  지연 백엔드를 붙여 재현한 뒤, `await` 뒤에는 ID로 다시 찾아 지우고 겹치는 flush는 하나로 합치도록
  고쳤다. 동시 flush 테스트를 추가하고 1.2.3으로 제출했다.
- **배운 점 —** `await` 앞에서 잡아 둔 인덱스·개수·"비어 있지 않음" 같은 사실은 `await` 뒤에는
  전부 무효로 취급한다. actor라는 단어가 주는 안전감이 오히려 이 버그를 오래 숨겼다.
- **잠금화면의 물리적 한계.** 잠금화면 Live Activity 높이는 이미 한도 근처라 큰 글씨 설정에서는
  넘친다. 여백 압축과 행 수 축소 두 안을 목업으로 만들어 두고 결정을 미뤘다.

## 참고

- Apple — ActivityKit(Live Activities): https://developer.apple.com/documentation/activitykit
- Notion — Authorization / Public integrations: https://developers.notion.com/docs/authorization
- Apple — StoreKit 2: https://developer.apple.com/documentation/storekit
- Swift Evolution — SE-0306 Actors (재진입 절): https://github.com/swiftlang/swift-evolution/blob/main/proposals/0306-actors.md
- Apple HIG — Live Activities: https://developer.apple.com/design/human-interface-guidelines/live-activities
