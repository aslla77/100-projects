# 기능 범위 (MoSCoW)

Gate 3. 산출물 = Codex 플러그인 `company-scout`. Tier 0 — 최소 MVP.

## Must (이번 MVP)
- 공식 규격 스캐폴드: `src/.codex-plugin/plugin.json` + `src/skills/company-scout/SKILL.md` [2].
- SKILL.md에 5축(회사/제품/고객/문제/관련회사) 수집 절차 + 출처 등급(A/B/C) 규칙 + 출력 스키마.
- 문제 후보 ≥3건(각 문제·공개URL·Codex 적합성 메모).
- "근거 부족" 분리, 끝에 References(등급·확인일).
- **보고서 형식: 각 섹션/파트 끝에 꼬리질문 3개** 자동 첨부(다음 조사 방향 제시).
- **용어 설명 섹션**(맨 밑): 전문 용어 모아 본문 링크. 간단·중요 용어는 본문 인라인 1줄.
- 파일럿(마이리얼트립)으로 end-to-end 1회 검증.

## Should
- 관련 회사 표(관계유형 라벨).
- 출처-완전성 점검(문제 후보에 URL 누락 시 경고) — SKILL.md 체크리스트 또는 작은 헬퍼 스크립트.
- README.md(제출용: 무엇을·누가·작동방식·AI활용·검증 5문항 초안) [1].

## Could
- 더미 입력 데이터 예시(공개 항공/상품 피드 샘플).
- 다른 출제사(무신사 등) 1곳 추가 시연.

## Won't (이번에 안 함)
- 유료/비공개 API 실연동.
- 특정 회사 문제를 실제로 푸는 별도 플러그인.
- 웹 UI / 배치 / 그래프 시각화 / 자동화 스케줄.

## References
- [1] 예선 과제 원문: `ax-talent-war-preliminary-task.pdf`
- [2] OpenAI Codex Build plugins: https://developers.openai.com/codex/plugins/build — A (확인일 2026-06-28)
