# company-scout (Codex 플러그인)

회사명 하나를 입력하면 **공개 자료만으로** 그 회사를 `회사 → 제품 → 고객 → 재무신호 → 문제 → 관련회사`로 구조화하고, 초심자도 이해할 수 있는 **출처 검증 보고서**를 만듭니다.

## 무엇이 다른가

모든 사실 주장에 공개 출처를 강제하고 출처에 등급(A/B/C)을 매깁니다. 확인하지 못한 것은 지어내지 않고 **"가설"** 또는 **"근거 부족"** 으로 분리해 남깁니다. 그래서 결과물을 그대로 믿는 대신, 어디까지가 검증된 사실인지 눈으로 확인할 수 있습니다.

- A: 공식·표준·벤더·논문·법령·공시
- B: 평판 있는 기술 매체·공식 블로그
- C: 커뮤니티·개인·유튜브·위키 — **단서로만** 사용

## 구조

```
company-scout/
├── .codex-plugin/
│   └── plugin.json                  # 매니페스트 (name/version/description/skills)
├── skills/
│   └── company-scout/
│       └── SKILL.md                 # 분석 방법론·출처 규칙·출력 스키마
└── README.md
```

`SKILL.md`는 few-shot 예시로 `examples/` 아래의 골든 예시를 참조합니다. 이 저장소에는 실제 회사 분석 보고서를 공개하지 않으므로 그 폴더가 비어 있습니다. 예시 없이도 동작하지만, 직접 한 번 실행해 만족스러운 결과를 `examples/`에 넣어 두면 이후 출력 품질이 안정됩니다.

## 설치와 사용

이 폴더를 통째로 복사한 뒤 Codex에 플러그인으로 등록하고, 스킬을 호출해 회사명을 입력하면 됩니다. 설치 방법은 Codex 버전에 따라 다르므로 공식 문서를 따르세요 — https://developers.openai.com/codex/plugins/build

결과 보고서는 `out/<회사명>-dossier-YYYYMMDD.md`로 저장하도록 지시되어 있습니다.

## 한계 (알고 쓰세요)

- **공개 자료만** 다룹니다. 비공개 내부 데이터가 필요한 판단은 하지 못합니다.
- 한국 기업 기준으로 만들어졌습니다. 공시(DART)·국내 매체를 전제한 서술이 있어 해외 기업에는 그대로 맞지 않을 수 있습니다.
- 출처 수집은 실행하는 에이전트의 웹 접근 능력에 의존합니다.
- `SKILL.md`와 예시에는 이 도구가 만들어진 계기였던 공모전(AX 인재전쟁) 관련 서술이 `(선택)` 표시와 함께 남아 있습니다. 범용으로 쓸 때는 무시해도 됩니다.

## References

- OpenAI — Codex: Build plugins: https://developers.openai.com/codex/plugins/build
- 출처 등급·인용 규칙: [`../../claude-code/docs/reference-policy.md`](../../claude-code/docs/reference-policy.md)
