# SK하이닉스 — 공개자료 기반 기업 이해 보고서

- **작성일**: 2026-06-29
- **데이터 기준일**: 2026-06-29 (수집된 최신 공개자료 기준)
- **한 줄 정체**: 메모리 반도체(DRAM·NAND·SSD)를 만드는 한국의 대형 제조사로, 특히 AI 서버용 **HBM(고대역폭메모리)** 분야의 세계 선두 기업. [1][3]
- **방법론**: company-scout — 공개·검증 가능한 자료만 사용. 모든 사실에 출처 URL·등급(A/B/C)·확인일. 확인 못 한 것은 "가설" 또는 "근거 부족"으로 분리.

> **출처 등급**: A = 공식·표준·공시(회사 사이트·뉴스룸·IR·SEC·DART) · B = 평판 있는 매체/시장조사사 · C = 커뮤니티·집계사이트·블로그(단서 전용, 사실 단정 금지)

---

## 0. 요약 (먼저 읽으면 되는 부분)

SK하이닉스는 **컴퓨터·서버·스마트폰에 들어가는 "기억 장치(메모리 반도체)"를 만드는 회사**다. 메모리는 크게 두 종류 — 전원이 꺼지면 지워지는 빠른 임시기억(**DRAM**)과, 꺼져도 남는 저장기억(**NAND 플래시**, SSD가 여기 속함) — 인데, SK하이닉스는 이 둘을 모두 만든다. 최근 회사를 폭발적으로 키운 것은 **HBM**이라는 특수 DRAM으로, AI 계산을 하는 NVIDIA 같은 회사의 GPU 옆에 붙어 데이터를 초고속으로 나르는 부품이다. [1][3]

**핵심 숫자 (모두 출처 있음)**
- FY2025 매출 **97.1조 원**, 영업이익 **47.2조 원**(영업이익률 49%), 순이익 **42.9조 원** — 사상 최대. [4] (A)
- 직전 다운턴인 **FY2023엔 영업손실 7.73조·순손실 9.14조**로 적자였다 → AI 수요로 1년 만에 흑자전환·사상 최대로 급반전. [3][4][1] (A)
- 2026-06-19 시가총액 **약 2,000조 원** 첫 돌파, 6-22 **코스피 시총 1위**(25년 만에 삼성전자 추월) 보도. [7] (B, 시총·주가 정밀치는 재확인 필요)
- HBM 시장 점유율 **약 57~62%**(2025년, 조사기관·분기·기준에 따라 상이)로 1위. [1][10] (A 인용/B)
- 임직원 **약 46,863명**(FY2024 공식 Fact Sheet). [1] (A)

**이 보고서로 알 수 있는 것**: 회사가 무엇을 만들고 어떻게 돈 버는지, 누가 고객인지, 누구와 경쟁하는지, 재무 추세, 공개적으로 드러난 문제들.
**알 수 없는 것(경계)**: HBM 매출의 정확한 절대액·비중, CAPEX 정확 금액, HBM4 실제 수율(영업비밀), 일부 점유율의 단일 확정치 — 모두 7장과 "근거 부족 모음"에 모았다.

---

## 1. 회사

**무엇을 하는 회사인가.** SK하이닉스는 메모리 반도체 전문 제조사다. 회사 스스로를 "글로벌 AI 메모리 산업의 선구자이며 HBM과 기업용 SSD(eSSD)에서 강한 리더십을 가진다"고 정의한다. [1] (A) 삼성전자·마이크론과 함께 메모리 "빅3"로 불린다. [2] (C, 단서)

**연혁 (간단히).**
- 1983년 **현대전자**로 설립(반도체 사업 시작). [1] (A)
- 2001년 **Hynix Semiconductor**로 사명 변경. [1] (A)
- 2012년 **SK텔레콤이 최대주주가 되며 SK하이닉스로** 편입(SK그룹 계열사가 됨). [1] (A)

**본사·규모.**
- 본사: 경기 **이천**, 또 다른 핵심 거점 충북 **청주**. 생산거점 4곳, R&D 자회사 5곳, 영업거점 24곳. [1] (A)
- 임직원: **46,863명**(FY2024), 여성 비율 33.4%. [1] (A)
- 경영진: CEO **곽노정**(2022.3 선임), 공동대표 **박정호**(2021.3 선임). 단, 경영진 구성은 변동 가능 — 2026년 최신 변동은 추가 확인 권장. [1] (A)

**지배구조.** 최대주주는 **SK스퀘어(SK Square) 20.07%**(2025.12 기준)로, SK스퀘어는 2021년 SK텔레콤에서 분할된 투자전문회사다. [4(시장)][5(시장)] (A) 그 위 SK Inc.까지 이어지는 최상위 사슬은 1차 출처로 확정하지 못함 → **가정/확인 필요**.

> **꼬리질문 3**
> 1. SK스퀘어→SK Inc.로 이어지는 지주 구조에서 SK하이닉스의 의사결정 자율성은 어느 정도인가?
> 2. 이천·청주 외 용인 클러스터가 가동되면 인력·생산의 무게중심은 어떻게 이동하나?
> 3. 46,863명 중 R&D·소프트웨어/데이터 직군 비중은? (공개 미상)

---

## 2. 제품

SK하이닉스의 제품은 크게 **DRAM / NAND·SSD** 두 갈래다.

**2-1. DRAM (빠른 임시기억).**
- 서버·PC용 **DDR5**, 모바일용 **LPDDR**, 그리고 AI용 **HBM** 제품군 보유. [3] (A)
- 2024년 세계 최초 **321단 NAND** 양산, 2025년 세계 최초 **12단 HBM4 샘플** 출하 등 "세계 최초" 타이틀을 다수 보유. [1] (A)
- 현재 주력은 **HBM3E**, 차세대는 **HBM4**(양산 진입 단계). [3] (A)

**2-2. HBM이 왜 중요한가 (초심자 설명).**
HBM(High Bandwidth Memory)은 **DRAM 칩을 여러 장 수직으로 쌓아 GPU 바로 옆에 붙인 메모리**다. AI 계산은 어마어마한 양의 데이터를 빠르게 옮겨야 하는데, 일반 DRAM으로는 그 "통로(대역폭)"가 좁다. HBM은 통로를 크게 넓혀 이 병목을 푼다. 그래서 AI 붐과 함께 HBM 수요가 폭발했고, SK하이닉스 실적 급반등의 핵심 동력이 됐다. [1][3] (A)
> (주의) "칩을 쌓는다"는 기술 정의의 JEDEC 등 1차 표준 출처는 본 조사 범위 밖 — 회사 서술 기반 요약이다. [근거 부족]

**2-3. NAND·SSD (저장기억).**
- 기업용 **eSSD**에서 강한 리더십(자사 정의). [1] (A)
- **Solidigm**: 2020년 인텔의 NAND/SSD 사업을 약 90억 달러에 인수 합의 → 2021년 1단계 완료(미국 자회사 Solidigm 출범), 2025년 2단계(약 22.4억 달러) 지급으로 인수 완료. [5][6] (A/B) 이로써 SK하이닉스는 NAND에서 SK하이닉스 본체 + Solidigm 두 축을 갖는다.

**2-4. 파운드리(위탁생산)는 곁가지.**
메모리가 본업이고, 비메모리 파운드리는 자회사 **SK하이닉스시스템IC**(8인치 성숙공정: 전력반도체·DDI 등)와 **SK키파운드리**를 통한 보조 사업이다. 시스템IC 파운드리 지분 49.9%는 중국 우시산업발전집단으로 이전됐다. [4(시장 16)] (B) 단, 정확한 시점·지분율은 매체 단서 수준 → **확인 필요**.

> **꼬리질문 3**
> 1. HBM4가 HBM3E를 대체하는 양산 전환은 언제, 어느 수율에서 이뤄지나? (수율 비공개)
> 2. Solidigm 인수로 NAND 수익성은 실제로 개선됐나? (세그먼트 손익 미공개)
> 3. 파운드리 사업을 축소(지분 이전)하는 방향은 메모리 집중 전략의 신호인가?

---

## 3. 고객

**누가 SK하이닉스 메모리를 사는가.** 가장 중요한 고객층은 **AI 데이터센터를 짓는 회사들**이다.

- **NVIDIA** — 가장 핵심. SK하이닉스는 NVIDIA 차세대 **GB300(Blackwell Ultra) GPU**에 12단 HBM3E를 적용·전시했고, 2025년 HBM 물량을 이미 **완판(sold out)**했다. [SC25 전시: 2][HBM 완판/공급: 1] (A) NVIDIA가 GB300용 12단 HBM3E를 SK하이닉스가 **독점** 공급한다는 보도도 있으나 "reportedly(보도)"로 표기됨 — 독점은 미확정. [9] (B)
- **그 외 HBM 고객**: 회사의 2026 전망 문서에 **Google(TPU), AWS(자체 AI 칩)** 가 고객으로 거론. 주요 클라우드(AWS·Azure·Google·Meta)는 장기공급계약(LTA)으로 12~24개월치 HBM을 선확보 중이라는 보도. [1(A)][12(B)]
- **엔터프라이즈 SSD**: Solidigm 통합 후 HPE 같은 서버 업체에 기업용 SSD 공급(HPE Discover 2026 전시). [14] (B)
- **고객 밀착**: NVIDIA·Amazon·Microsoft 인근 미국 시애틀권에 사무소를 열어 공동설계 강화. [13] (B)

> (근거 부족) Apple·삼성 모바일·Dell 등 **스마트폰/PC OEM 개별 고객명**의 공식 공급 출처는 확보 못 함 → 확인 필요.

> **꼬리질문 3**
> 1. NVIDIA 한 곳에 대한 매출 의존도는 정확히 몇 %인가? (6장 참조 — 보도상 높음)
> 2. Google·AWS 등 "자체 AI 칩" 진영이 커지면 SK하이닉스에 기회인가 위협인가?
> 3. LTA(장기계약)는 다운턴 때 방패가 되나, 아니면 가격 하락 시 족쇄가 되나?

---

## 4. 재무 신호 (DART/공식 IR 기반)

> 출처: SK하이닉스 공식 뉴스룸·보도자료(A급). 단위 조 원, K-IFRS 연결 기준. **DART 정기보고서 원문과의 1:1 대조는 미수행 → 최종 인용 전 DART 교차확인 권장.**

**연간 추세 — "다운턴 적자 → AI로 사상 최대"의 드라마.**

| 회계연도 | 매출 | 영업이익 | 순이익 | 비고 | 출처 |
|---|---|---|---|---|---|
| FY2022 | 44.6조 | 7.0조 | 2.4조 | 하반기 다운턴 진입 | [a] (A) |
| FY2023 | 32.8조 | **-7.73조** | **-9.14조** | 메모리 다운턴 **적자** | [b][1] (A) |
| FY2024 | 66.2조 | 23.5조 | 19.8조 | 흑자전환·사상 최대 | [1] (A) |
| FY2025 | **97.1조** | **47.2조** (49%) | **42.9조** (44%) | 사상 최대 경신 | [4] (A) |

**최근 분기 — 회복의 가속.**

| 분기 | 매출 | 영업이익 | 순이익 | 출처 |
|---|---|---|---|---|
| 4Q24 | 19.8조 | 8.08조 | 8.01조 | [1] (A) |
| 1Q25 | 17.6조 | 7.44조 | 8.11조 | [c] (A) |
| 2Q25 | 22.2조 | 9.21조 | 7.00조 | [d] (A) |
| 3Q25 | 24.4조 | 11.38조 | 12.60조 | [4] (A) |
| 4Q25 | 32.8조 | 19.17조 (58%) | 15.25조 | [4] (A) |

**HBM 기여도 (공식 언급, 정확 금액은 비공개).**
- 4Q24: "HBM이 **DRAM 매출의 40% 이상**". [1] (A)
- FY2025: "HBM 매출이 전년 대비 **2배 이상** 증가, 실적에 크게 기여". [4] (A)
- → 정확한 HBM 매출 절대액·전사 비중은 **근거 부족**(비공개).

**재무 건전성.** 부채비율 31%(2024말)→25%(2025.6), 순차입금비율 12%→6%로 개선. 현금성자산 14.2조(2024말)→17조(2025.6). [1][d] (A) 주주환원(FY2025): 배당 약 2.1조 + 자사주 약 12.2조 소각 발표. [4] (A)

**투자(CAPEX).** 정확 금액은 공식 발표문에 비공개(**근거 부족**). 다만 청주 **M15X**, **용인 클러스터**(첫 팹 건설), 미국 인디애나 첨단 패키징 등 대규모 투자 진행이 공식 언급됨. [4] (A) 매체는 2026년 CAPEX를 35조~40조원대로 보도(편차 큼, 미확정). [12] (B)

> **꼬리질문 3**
> 1. 영업이익률 49~58%는 HBM 프리미엄에 기댄 것 — 경쟁 심화 시 이 마진은 지속 가능한가?
> 2. 매출이 4Q23 11조 → 4Q25 33조로 3배 — 이 성장의 몇 %가 물량 증가이고 몇 %가 가격 상승인가?
> 3. 사상 최대 이익이 대규모 CAPEX와 겹칠 때, 다운턴이 오면 2023년 적자가 재현되나?

---

## 5. 시장·경쟁 / 관련 회사

**시장 구조.** 글로벌 메모리 시장은 2025년 약 **2,000억 달러** 규모(DRAM 약 1,290억 + NAND 약 650억, Yole 추정 — 조사사별 편차 큼 $117B~$214B). [11] (B) AI가 HBM 수요를 끌어올리며 시장 전체가 슈퍼사이클에 진입했다는 게 업계 공통 서사다.

**경쟁 구도 (관계 라벨 + 점유율).** 메모리는 사실상 **3강 과점**이다.

| 회사 | DRAM (4Q25) | NAND (4Q25) | HBM (2025) | 관계 |
|---|---|---|---|---|
| **삼성전자** | 36% (1위) | 28% (1위) | 17% (2Q25) | **직접경쟁(전 분야)** |
| **SK하이닉스** | 32.1% (2위) | 22.1%*(SK그룹) | **57~62% (1위)** | — |
| **마이크론(Micron)** | 22.4% | 약 $3.0B | 21% (2Q25) | **직접경쟁(전 분야)** |
| **키옥시아(Kioxia)** | — | $3.3B | — | **직접경쟁(NAND) + SK의 지분 투자관계** |

(출처: DRAM/NAND/HBM 모두 TrendForce·Counterpoint, [6][8][10] B / *NAND는 SK하이닉스+Solidigm 합산. SK하이닉스 단독 %는 1차 미확인 → 근거 부족)

- **DRAM 순위는 분기마다 뒤집힌다**: 1Q25엔 SK하이닉스가 사상 처음 삼성을 제치고 1위였으나, 4Q25엔 삼성이 1위 탈환. [7(시장)][6] (B) → 박빙.
- **HBM은 SK하이닉스 우위가 뚜렷**하나(57~62%), 마이크론이 삼성을 제치고 2위로 올라서며 **HBM4로 경쟁축이 이동** 중. [10] (B/C) Goldman은 2026년에도 SK 50%+ 유지, UBS는 NVIDIA Rubin용 HBM4에서 약 70% 전망(둘 다 **의견/전망**). [1] (A 인용)

**관련 회사.**
- **Solidigm**: SK하이닉스 완전자회사(인텔 NAND 사업, 2장 참조). [5] (A)
- **SK하이닉스시스템IC / SK키파운드리**: 파운드리 자회사(2장 참조).
- **키옥시아**: NAND **경쟁사이면서 동시에** SK하이닉스가 2018년 베인 컨소시엄을 통해 투자한 **재무적 투자 대상**(직접 지분 7%+ 및 전환 시 ~15% 상당 CB 보유로 보도). 지분율은 보도마다 달라 **확인 필요**. [17] (B)
- **모회사**: SK스퀘어(최대주주 20.07%). [4(시장)] (A)

> **꼬리질문 3**
> 1. HBM에서 마이크론·삼성이 NVIDIA 인증을 늘리면 SK하이닉스 점유율은 얼마나 빠르게 깎이나?
> 2. 키옥시아는 경쟁사인가 우군(지분)인가 — 이해상충은 없나?
> 3. 범용 DRAM에서 중국 CXMT가 가격을 무너뜨리면, 3강 과점 구조 자체가 흔들리나? (6장 연결)

---

## 6. 문제 신호 → 이슈 가설

> **규칙**: [사실] = 공개 출처로 확인 / [가설] = 추정·예측("~일 가능성"). 둘을 절대 섞지 않는다.
> 각 문제에 **Codex 플러그인 적합성 3축**(입력데이터 공개가용성 / 문제경계 명확성 / 플러그인 표현가능성)을 상·중·하로 표기.

**문제 A. NVIDIA 고객 집중(의존도) 리스크**
- [사실] 1Q26 NVIDIA향 HBM 공급 약 7.78조원(전년比 +62.6%). NVIDIA 외 단일 고객이 처음 매출 10%선을 넘었다는 보도(미국 하이퍼스케일러 추정). [18] (C — 단서, 재확인 필요)
- [사실] SK하이닉스가 SEC F-1에 "빅테크 CAPEX 둔화 시 HBM 수요 악화", "고객 선주문 후 주문취소" 리스크를 직접 공시했다고 보도. 2025년 매출 지역의존도 미국 68.8%·중국 19.7%로 명시(보도 인용). [2(문제)] (B) / F-1 원문 [1(문제)] (A, **단 본 보고서가 직접 대조하지 못함 → 7장·근거부족 참조**)
- [가설] NVIDIA가 삼성·마이크론을 대체 소스로 인증하면 SK하이닉스의 협상력·마진이 약화될 가능성.
- **적합성**: 데이터가용성 **상** / 문제경계 **상** / 표현가능성 **상** → 분기 공시·뉴스에서 고객 집중 신호를 추출·구조화하는 도구로 표현 용이. **(최우선 후보)**

**문제 B. 미·중 수출규제 — 중국 공장 VEU 지위 철회**
- [사실] 미국 BIS가 2025-12-31부로 삼성·SK하이닉스·TSMC의 **검증된 최종사용자(VEU) 지위를 철회** → 중국 공장(우시 DRAM, 다롄 NAND)에 미국산 장비 반입 시 건별/연단위 라이선스 필요로 전환. [3(문제)][4(문제)] (B)
- [가설] 연단위 갱신 구조라 중국 공장 증설·업그레이드의 예측가능성이 떨어질 가능성. 갱신 불발 시 생산 차질.
- **적합성**: 가용성 **상** / 경계 **중**(승인 수량 비공개) / 표현 **중**.

**문제 C. 중국 메모리(CXMT/YMTC)의 범용 시장 잠식**
- [사실] CXMT가 세계 4위 DRAM(용량 약 11%)으로 구형 DDR4를 시장가 절반에 공급. YMTC는 2026 하반기 양산으로 NAND 3위 등극 가능성 보도. [5(문제)][8(문제)] (B)
- [가설] 한국 업체가 HBM4에 집중하는 사이 **범용 DRAM 가격이 압박**받아 비-HBM 수익성이 훼손될 가능성. CXMT 선단 노드는 약 3년 격차로 추정(미확정). [7(문제)] (B)
- **적합성**: 가용성 **상** / 경계 **상** / 표현 **상** → 경쟁사 가격·점유 신호 모니터링 도구로 적합. **(우선 후보)**

**문제 D. HBM 마진 정점(가격 지속가능성) 리스크**
- [사실] 2026년 HBM에서 마이크론이 일부 할당에서 삼성을 추월, **HBM4로 경쟁 격화**. [19] (C)
- [가설] Goldman이 2025년 중반 HBM 가격 지속가능성 우려로 2026 영업이익 기대 대비 약 19% 하락 가능성 제기(애널리스트 전망=가설). [20] (C, 원 리포트 미확인)
- **적합성**: 가용성 **중** / 경계 **중** / 표현 **중**.

**문제 E. HBM4 수율·첨단 패키징(하이브리드 본딩) 난제**
- [사실] SK하이닉스가 12단 하이브리드 본딩 HBM 검증 완료를 발표했으나 **수율은 비공개**. HBM4 16단은 JEDEC 높이 제한 내 적층 위해 웨이퍼 30μm 박막화 필요 등 공정 난도 상승. [9(문제)] (B)
- **적합성**: 가용성 **하**(수율=영업비밀) / 경계 **하** / 표현 **중** → 정량화 어려움, 기술 로드맵 정성 트래킹만 가능.

**문제 F. 대규모 CAPEX 부담 + 다운턴 적자 이력(재무 사이클 리스크)**
- [사실] FY2023 영업손실 7.73조·순손실 9.14조 기록(다운턴). [10(문제)][b] (A) 용인 클러스터 등 대규모 투자 진행(2장·4장). 매체상 2026 CAPEX 35~40조원대(미확정). [12(문제)] (B)
- [가설] 다운턴 재도래 시 큰 고정비·감가상각이 적자 폭을 키워 2023년 패턴이 재현될 가능성.
- **적합성**: 가용성 **상** / 경계 **상** / 표현 **상** → 실적·CAPEX 정형 데이터로 "사이클 민감도 대시보드" 표현 용이. **(우선 후보)**

**문제 G. 노무·안전(운영/ESG) 리스크**
- [사실] 2025년 임금교섭 10차례에도 합의 실패(노조: 영업이익 10% 전액 성과급 요구). [13(문제)] (B) 산재 승인 직원이 2026-06-25 사망, 고용부 중대재해 조사 중. 청주 공정 화재로 반도체 25곳 집중 안전점검. [14(문제)][15(문제)] (B)
- **적합성**: 가용성 **중** / 경계 **하**(단발 사건) / 표현 **중** → ESG 신호 수집 보조 수준.

**문제 H(기획 정합). AI·시장 인텔리전스 인력 수요 — 공식 JD 근거**
- [사실] SK하이닉스 공식 채용공고에 "데이터 분석 기반 AI·반도체 산업 **고난도 이슈 구조화**", "글로벌 AI 기술·시장 변화 분석" 업무, "데이터 기반 사업성 분석" 필수자격 명시. 신입 공채에 빅데이터/AI 직무·AI 영상면접 포함. [16(문제)][17(문제)] (A)
- [가설] 내부에 'AI·경쟁사·시장 리스크를 정형화해 의사결정에 공급'하는 인텔리전스 수요가 존재할 가능성 → **본 Codex 플러그인 기획의 직접 정당화 근거가 될 수 있음**(가설).
- **적합성**: 가용성 **상**(공식 JD) / 경계 **중** / 표현 **상** → 기획 정합성 매우 높음.

> **꼬리질문 3**
> 1. 위 8개 중 "공개 데이터만으로 분기마다 자동 갱신 가능한" 문제는 무엇인가? (A·C·F가 유력)
> 2. NVIDIA 의존도·중국 추격·CAPEX 사이클은 서로 어떻게 연결돼 한 화면에서 봐야 하나?
> 3. 수율(E)처럼 비공개 변수가 핵심인 문제는 플러그인 범위에서 빼야 하나?

---

## 7. 분석의 경계 (말할 수 있는 것 / 없는 것)

**말할 수 있는 것 (공개 출처로 확인)**: 회사 정체·연혁·거점·임직원, 제품 라인(DRAM/NAND/HBM/SSD), 핵심 고객(NVIDIA 등) 관계, 연간·분기 실적 추세, 3강 경쟁 구도와 분기별 점유율, 공개적으로 보도·공시된 리스크들.

**말할 수 없는 것 / 불확실**:
- **HBM 매출 절대액·전사 비중** — 비공개("DRAM의 40%+", "YoY 2배+"만 공개).
- **CAPEX 정확 금액** — 공식 발표문 미공개, 매체 추정만.
- **HBM4 실제 수율** — 영업비밀.
- **일부 점유율의 단일 확정치** — 조사기관(TrendForce/Counterpoint)·분기·기준(매출 vs 용량)에 따라 다름.
- **SEC F-1 원문** — 본 보고서가 직접 대조하지 못함. F-1을 통한 미국 상장 추진이라는 맥락은 중대한 주장이므로 **SEC EDGAR 원문으로 재확인 필요**. F-1 기반 수치(미국 의존 68.8% 등)는 매체 인용(B)으로만 취급.
- **시가총액·주가 정밀치** — 집계사이트 간 불일치($1.235T vs $1.43T 등), KRX 원자료 재확인 필요.

---

## (선택) 예선 5문항 초안 — Codex 플러그인 기획 입력용

공개 데이터로 분기마다 자동 갱신 가능하고 문제경계가 명확한 후보(A·C·F·H) 중심으로 제안한다. 모두 **가설/기획 제안**이며 채택 전 검증 필요.

1. **고객 집중도 모니터**: 분기 공시·뉴스에서 SK하이닉스의 NVIDIA 등 단일 고객 매출 비중 신호를 추출·구조화할 수 있는가? (문제 A)
2. **범용 메모리 가격 압박 추적**: CXMT/YMTC의 점유·가격 신호를 모아 SK하이닉스 비-HBM 부문 리스크를 정형화할 수 있는가? (문제 C)
3. **메모리 사이클 민감도 대시보드**: 실적·CAPEX·재고 신호로 다운턴 재현 위험을 조기 경보할 수 있는가? (문제 F)
4. **수출규제 영향 트래커**: BIS VEU/라이선스 규제 변화가 중국 공장에 주는 영향을 공개 규제문서 기반으로 구조화할 수 있는가? (문제 B)
5. **시장 인텔리전스 자동화**: 공식 JD가 요구하는 "AI·경쟁사·시장 이슈 구조화" 업무를 공개자료 수집·정형화로 보조할 수 있는가? (문제 H, 기획 자기정당화)

---

## References

> 등급·확인일(모두 2026-06-29). A=공식/공시, B=평판매체/시장조사, C=단서.

**회사·제품·재무 (공식 A 우선)**
- [1] SK hynix Fact Sheet (공식 뉴스룸) — https://news.skhynix.com/corporate/fact-sheet/ — A
- [2] SK Hynix, Wikipedia — https://en.wikipedia.org/wiki/SK_Hynix — C(단서)
- [3] SK hynix 뉴스룸 "2026 Market Outlook (HBM)" — https://news.skhynix.com/2026-market-outlook-focus-on-the-hbm-led-memory-supercycle/ — A(공식)/내부 인용 수치는 B
- [4] SK hynix 뉴스룸 — FY2025/3Q·4Q25 실적 — https://news.skhynix.com/sk-hynix-announces-fy25-financial-results/ — A
- [a] SK hynix 뉴스룸 — 2022/4Q22 실적 — https://news.skhynix.com/sk-hynix-reports-2022-and-fourth-quarter-financial-results/ — A
- [b] SK hynix 보도자료(PRNewswire) — 2023/4Q23 실적 — https://www.prnewswire.com/news-releases/sk-hynix-reports-financial-results-for-2023-4q23-302043921.html — A
- [c] SK hynix 뉴스룸 — 1Q25 실적 — https://news.skhynix.com/sk-hynix-announces-1q25-financial-results/ — A
- [d] SK hynix 보도자료(PRNewswire) — 2Q25 실적 — https://www.prnewswire.com/news-releases/sk-hynix-announces-2q25-financial-results-302512514.html — A
- [5] SK hynix — 인텔 NAND 인수 1단계 완료 — https://www.prnewswire.com/news-releases/sk-hynix-completes-the-first-phase-of-intel-nand-and-ssd-business-acquisition-301451672.html — A
- [6] Tom's Hardware — Intel-SK NAND 딜 종결 — https://www.tomshardware.com/pc-components/ssds/intel-and-sk-hynix-close-nand-business-deal-intel-gets-usd1-9-billion-sk-hynix-gets-ip-and-employees — B

**고객·시장·경쟁 (B 시장조사 위주)**
- [2(SC25)] SK hynix 뉴스룸 — SC25 AI 메모리 전시 — https://news.skhynix.com/sk-hynix-showcases-advanced-ai-memory-at-sc25/ — A
- [6(DRAM)] TrendForce — 4Q25 DRAM(삼성 1위 탈환) — https://www.trendforce.com/presscenter/news/20260226-12937.html — B
- [7(시장)] TrendForce — 1Q25 DRAM(SK 1위) — https://www.trendforce.com/presscenter/news/20250603-12603.html — B / KED Global — 시총 1위 — https://www.kedglobal.com/korean-chipmakers/newsView/ked202606220007 — B
- [8(NAND)] TrendForce — 4Q25 NAND — https://www.trendforce.com/presscenter/news/20260303-12943.html — B
- [9(독점보도)] TrendForce — GB300 12H HBM3E 독점 보도 — https://www.trendforce.com/news/2025/03/18/news-sk-hynix-reportedly-locks-in-exclusive-12h-hbm3e-deal-for-nvidias-gb300/ — B
- [10] Astute Group — HBM 2Q25 점유(SK 62%) — https://www.astutegroup.com/news/general/sk-hynix-holds-62-of-hbm-micron-overtakes-samsung-2026-battle-pivots-to-hbm4/ — B/C
- [11] Yole Group — 2025 메모리 시장규모 — https://www.yolegroup.com/press-release/memory-market-surges-beyond-expectations-almost-200-billion-in-2025-driven-by-hbm-ai/ — B
- [12] Tom's Hardware — AI 메모리 부족/LTA — https://www.tomshardware.com/tech-industry/artificial-intelligence/samsung-and-sk-hynix-warn-ai-driven-memory-shortages-could-last-until-2027-and-beyond-as-hbm-demand-explodes-customers-already-reserving-supply-years-ahead-while-the-wider-dram-market-begins-to-tighten — B
- [13] Tom's Hardware — 美 시애틀권 사무소 — https://www.tomshardware.com/pc-components/dram/sk-hynix-expands-us-footprint-with-seattle-area-office-near-nvidia-and-amazon — B
- [14] TechTimes — HPE Discover 2026 SSD — https://www.techtimes.com/articles/318703/20260619/sk-hynix-shows-its-full-ai-server-memory-stack-cxl-32-modules-hpe-discover.htm — B
- [16(우시)] KED Global — 우시 파운드리 지분(시스템IC 50.1%) — https://www.kedglobal.com/korean-chipmakers/newsView/ked202405090006 — B
- [17] Seoul Economic Daily — SK의 키옥시아 지분 가치 — https://en.sedaily.com/news/2026/03/03/kioxia-shares-surge-14-fold-boosting-sk-hynix-stake-value — B

**문제·리스크**
- [1(문제)] SK hynix Form F-1 (SEC) — https://www.sec.gov/Archives/edgar/data/0002120882/000119312526280172/d32785df1.htm — A (본 보고서 직접 대조 미수행)
- [2(문제)] 한국경제 — SK하이닉스 리스크(F-1 인용) — https://www.hankyung.com/article/202606257054g — B
- [3(문제)] 경향신문 — VEU 규제 — https://www.khan.co.kr/article/202512302047015 — B
- [4(문제)] 글로벌이코노믹 — VEU 철회 — https://www.g-enews.com/article/Global-Biz/2025/12/202512270733546665fbbec65dfb_1 — B
- [5(문제)] Nikkei Asia — CXMT/YMTC 확장 — https://asia.nikkei.com/business/tech/semiconductors/china-s-cxmt-and-ymtc-to-massively-expand-memory-output-amid-global-crunch — B
- [7(문제)] SemiAnalysis — CXMT — https://newsletter.semianalysis.com/p/chinas-cxmt-is-set-to-challenge-dram — B
- [8(문제)] DigiTimes — CXMT/YMTC — https://www.digitimes.com/news/a20260204PD205/cxmt-ymtc-dram-hbm-chip-shortage.html — B
- [9(문제)] TrendForce — 하이브리드 본딩 수율 — https://www.trendforce.com/news/2026/04/29/news-sk-hynix-reportedly-completes-12-high-hybrid-bonding-hbm-validation-works-to-raise-yields-for-mass-production/ — B
- [10(문제)] SK하이닉스 뉴스룸 — 2023 실적 — https://news.skhynix.co.kr/2023-business-results/ — A
- [12(문제)] Seoul Economic Daily — CAPEX 경쟁 — https://en.sedaily.com/finance/2026/01/01/samsung-sk-hynix-launch-massive-chip-capex-race-investment — B
- [13(문제)] 시사IN — 성과급 논란 — https://www.sisain.co.kr/news/articleView.html?idxno=57830 — B
- [14(문제)] 아주경제 — 산재 사망/중대재해 조사 — https://www.ajunews.com/view/20260626181818771 — B
- [15(문제)] 이투데이 — 업무상질병 사망 — https://www.etoday.co.kr/news/view/2597782 — B
- [16(문제)] SK Careers — 성장전략 경력 JD — https://www.skcareers.com/Recruit/Detail/R260930 — A
- [17(문제)] SK Careers — 신입 채용 — https://www.skcareers.com/Recruit/Detail/R260521 — A
- [18] BigGo Finance — NVIDIA 매출(보도) — https://finance.biggo.com/news/-cg1K54BNl__-4_Gd-0t — C
- [19] TweakTown — HBM4 경쟁 — https://www.tweaktown.com/news/109495/ — C
- [20] Korea Invest Insights — Goldman 전망 인용 — https://koreainvestinsights.com/post/sk-hynix-hbm-market-share-ai-memory-demand-2026/ — C

---

## 용어 설명

- **DRAM**: 전원이 켜져 있을 때만 데이터를 유지하는 빠른 임시기억 메모리. PC·서버의 "작업 공간". [1]
- **NAND 플래시**: 전원이 꺼져도 데이터가 남는 저장용 메모리. SSD의 핵심 부품. [1]
- **SSD / eSSD**: NAND로 만든 저장장치. eSSD는 데이터센터·서버용 기업급 SSD. [1]
- **HBM (고대역폭메모리)**: DRAM을 수직으로 쌓아 GPU 옆에 붙인 AI용 초고속 메모리. 세대: HBM3 → HBM3E → HBM4. [1][3]
- **파운드리**: 남의 설계를 받아 칩을 위탁생산하는 사업. SK하이닉스에선 비주력(자회사). [4(시장)]
- **CAPEX**: 설비투자. 공장·장비에 쓰는 대규모 자본 지출. [12(문제)]
- **VEU (검증된 최종사용자)**: 미국이 특정 기업의 중국 공장에 장비 반입을 포괄 허용하던 제도. 2025말 철회됨. [3(문제)]
- **LTA (장기공급계약)**: 고객이 수년치 물량을 미리 확보하는 계약. [12]
- **TrendForce / Counterpoint / Yole**: 반도체 시장 점유율·규모를 집계하는 시장조사사(B등급). 기관·분기별로 수치가 다를 수 있음.

---

## 근거 부족 모음 (확인 필요 — 단정 금지)

1. **DART 원문 1:1 대조 미수행** — 재무 수치는 SK하이닉스 공식 뉴스룸/보도자료(A)에 근거. DART 정기보고서와의 직접 대조는 미실시 → 최종 인용 전 교차확인 권장.
2. **HBM 매출 절대액·전사 비중** — 비공개("DRAM의 40%+", "YoY 2배+"만 공개).
3. **CAPEX 정확 금액** — 공식 미공개, 매체 추정(35~40조)만 존재.
4. **HBM4 실제 수율** — 영업비밀, 정량 단정 불가.
5. **SEC F-1 원문 및 미국 상장 맥락** — 본 보고서 직접 미대조. SEC EDGAR 원문 재확인 필요. F-1 기반 수치(미국 의존 68.8% 등)는 B로만 취급.
6. **점유율 단일 확정치** — DRAM 분기별 1위 교차(삼성↔SK), HBM 50~62% 편차, NAND는 SK하이닉스 단독 vs SK그룹 합산 차이. 출처·분기·기준 반드시 병기.
7. **시가총액·주가 정밀치** — 집계사이트 불일치, KRX 재확인 필요.
8. **키옥시아 정확 지분율** — 직접 7%+ vs 전환 시 ~15%, 보도별 상이.
9. **지배구조 최상위(SK Inc.) 사슬** — 1차 출처 미확정(가정).
10. **스마트폰/PC OEM 개별 고객명** — 공식 공급 출처 미확보.
11. **경영진 최신성** — 곽노정/박정호 체제의 2026년 변동 추가 확인 권장.
12. **NVIDIA 매출 비중 정확 %** — 보도(C) 기반, F-1 세그먼트로 정밀 확인 필요.
