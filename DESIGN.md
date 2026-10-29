---
version: alpha
name: "[서비스명] Design"
description: "흑백 캔버스 위에 파스텔 컬러 블록 네 가지를 '붙인' 디자인. 화면의 뼈대는 순수 흰색·검정·알약 버튼으로 조용하게 두고, 색은 서비스의 세 단계(공고 → 근거 → 과제)와 CTA에만 씁니다. 큰 400 굵기 헤드라인, 점선 = 빈칸이라는 시각 규칙, 근거 점수 8칸 막대가 핵심입니다."

colors:
  canvas: "#FFFFFF"
  ink: "#000000"
  ink-inverse: "#FFFFFF"
  block-lime: "#DCEEB1"     # 01 공고
  block-lilac: "#C5B0F4"    # 02 근거
  block-cream: "#F4ECD6"    # 03 과제
  block-coral: "#F3C9B6"    # CTA
  block-pink: "#EFD4D4"     # 검정 띠 위 '인정하지 않아요' 라벨
  success: "#1EA64A"        # 과제 완료 체크
  hairline-dark: "#333333"  # 검정 띠 안 구분선

typography:
  font-ko: "'Wanted Sans Variable', system-ui, sans-serif"
  font-latin: "Inter"
  stack: "'Inter', 'Wanted Sans Variable', sans-serif"
  display:
    fontSize: "clamp(48px, 7.4vw, 104px)"
    fontWeight: 400
    lineHeight: 0.98
    letterSpacing: -0.045em
  heading-1:
    fontSize: "clamp(40px, 6vw, 80px)"
    fontWeight: 400
    lineHeight: 1.0
    letterSpacing: -0.045em
  heading-2:
    fontSize: "clamp(36px, 5vw, 64px)"
    fontWeight: 400
    lineHeight: 1.05
    letterSpacing: -0.04em
  card-title:
    fontSize: 26px
    fontWeight: 500
    lineHeight: 1.3
    letterSpacing: -0.02em
  stat:
    fontSize: "clamp(88px, 9vw, 120px)"
    fontWeight: 300
    lineHeight: 0.9
    letterSpacing: -0.06em
  body-lg:
    fontSize: 20px
    fontWeight: 400
    lineHeight: 1.5
  body:
    fontSize: 15px
    fontWeight: 400
    lineHeight: 1.5
  label:
    fontSize: 15px
    fontWeight: 600
  caption:
    fontSize: 13px
    fontWeight: 400
  button:
    fontSize: 17px
    fontWeight: 400

rounded:
  check: 6px
  row: 8px
  card-inner: 16px
  block: 24px
  pill: 50px

spacing:
  container: 1280px
  gutter: 24px
  block-gap: 16px
  section-gap: 24px
  block-padding: 28px
  band-padding: "clamp(32px, 6vw, 72px)"

components:
  nav-bar:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    height: 68px
  button-primary:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.ink-inverse}"
    typography: "{typography.button}"
    rounded: "{rounded.pill}"
    minHeight: 52px
    padding: "0 28px"
  button-secondary:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    border: "1px solid {colors.ink}"
    rounded: "{rounded.pill}"
    minHeight: 52px
  button-nav:
    rounded: "{rounded.pill}"
    minHeight: 44px
    padding: "0 18px"
  color-block:
    rounded: "{rounded.block}"
    padding: "{spacing.block-padding}"
    minHeight: 380px
  requirement-row:
    backgroundColor: "{colors.canvas}"
    rounded: "{rounded.row}"
    padding: "11px 12px"
  requirement-row-missing:
    backgroundColor: transparent
    outline: "2px dashed {colors.ink}"
    outlineOffset: -2px
    rounded: "{rounded.row}"
  score-meter:
    cells: 8
    cellHeight: 14px
    cellGap: 4px
    cellBorder: "1.5px solid {colors.ink}"
    filled: "{colors.ink}"
    empty: transparent
  task-card:
    backgroundColor: "{colors.canvas}"
    rounded: "{rounded.card-inner}"
    padding: 18px
  task-toggle:
    rounded: "{rounded.pill}"
    minHeight: 48px
    off: "흰 배경 + 검정 테두리"
    on: "검정 배경 + 흰 글자, 체크박스 {colors.success}"
  inverse-band:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.ink-inverse}"
    rounded: "{rounded.block}"
    padding: "{spacing.band-padding}"
  cta-block:
    backgroundColor: "{colors.block-coral}"
    rounded: "{rounded.block}"
    padding: "{spacing.band-padding}"
---

# [서비스명] DESIGN.md

> 기준 시안: 캔버스의 **"✅ 최종 확정 — 05 Figma풍"** 아트보드  
> https://claude.ai/artifact/8HUZRaSVKZqrSfS8XyHQ6f  
> UI 작업 전에 이 파일을 먼저 읽고, 여기 없는 값은 새로 만들지 말고 물어볼 것.

## 1. 한 줄 콘셉트

**"빈칸이 보여야 채울 수 있어요."** 화면은 흑백으로 조용하게 두고, 색은 서비스의 세 단계에만 씁니다. 사용자는 색만 보고도 지금 공고 / 근거 / 과제 중 어디에 있는지 알 수 있어야 합니다.

## 2. 색 — 색에는 뜻이 있다

| 토큰 | 값 | 뜻 | 쓰는 곳 |
|---|---|---|---|
| `canvas` | #FFFFFF | 바탕 | 페이지, 카드 안쪽 행 |
| `ink` | #000000 | 글자·행동 | 모든 글자, 주 버튼, 검정 띠 |
| `block-lime` | #DCEEB1 | **01 공고** | 공고·요구사항 화면 |
| `block-lilac` | #C5B0F4 | **02 근거** | 준비도·근거 점수 화면 |
| `block-cream` | #F4ECD6 | **03 과제** | 하루 과제 화면 |
| `block-coral` | #F3C9B6 | 행동 유도 | 마지막 CTA 블록만 |
| `success` | #1EA64A | 완료 | 과제 완료 체크박스만 |

- 단계 색을 다른 뜻으로 쓰지 않아요. 예를 들어 라임은 항상 "공고"예요.
- 그라데이션, 그림자, 반투명 유리 효과는 쓰지 않아요. 깊이는 **색 블록끼리의 대비**로만 만들어요.
- 파스텔 블록 위 글자는 항상 `ink`(검정)예요. 흰 글자는 검정 띠 위에서만 써요.

## 3. 타이포그래피

- **한글:** 원티드 산스 (`Wanted Sans Variable`, SIL OFL 1.1)
- **영문·숫자:** Inter. 폰트 스택은 `'Inter', 'Wanted Sans Variable', sans-serif`로, Inter에 한글 글리프가 없어서 한글은 자동으로 원티드 산스로 내려가요.
- **모든 루트에 `word-break: keep-all`.** 한글이 단어 중간에서 끊기면 안 돼요.
- 헤드라인은 **크고 가볍게**(400)씁니다. 굵게(700+) 쓰지 않는 것이 이 디자인의 핵심이에요.
- 큰 숫자(준비도 %)는 Inter 300, 자간 -0.06em으로 씁니다.
- 원티드 산스는 가장 얇은 굵기가 400이에요. 한글에 300을 지정해도 400으로 보여요.

설치:

```bash
npm i wanted-sans
```

```ts
// 앱 진입점 (예: main.tsx)
import 'wanted-sans/fonts/webfonts/variable/split/WantedSansVariable.css';
```

Inter는 Google Fonts에서 불러와요(`family=Inter:wght@300..700`).

## 4. 모양과 간격

- **모서리:** 알약 50px(버튼) · 블록 24px · 카드 안 박스 16px · 요구사항 행 8px · 체크박스 6px. 이 다섯 값 외에는 쓰지 않아요.
- **레이아웃:** 최대 너비 1280px, 좌우 여백 24px. 블록 사이 간격 16px, 섹션 사이 간격 24px.
- **블록 그리드:** `repeat(auto-fit, minmax(300px, 1fr))`. 폰에서는 자동으로 한 줄에 하나씩 쌓여요.
- **큰 띠(검정·코럴) 안쪽 여백:** `clamp(32px, 6vw, 72px)`

## 5. 컴포넌트

### 버튼
- **주 버튼:** 검정 알약, 흰 글자, 높이 52px. 한 화면에 하나만 둬요.
- **보조 버튼:** 흰 알약, 검정 1px 테두리.
- **헤더 버튼:** 높이 44px(터치 최소 크기).

### 요구사항 행 — 점선 = 빈칸
- **근거 있음:** 흰 배경 행.
- **근거 없음:** 배경 없이 **2px 검정 점선 테두리**.
- 오른쪽 끝에는 항상 배점을 표시해요(자격 요건 `2점`, 우대 `1점`).
- 과제를 끝내면 점선 행이 흰 배경 행으로 바뀌어요. 이 전환이 서비스의 핵심 장면이에요.

### 근거 점수 막대 (score-meter)
- 8칸, 칸마다 검정 1.5px 테두리. 채운 칸은 검정, 빈 칸은 투명이에요.
- 칸 수 = 총점. 예시 공고는 자격 3개×2점 + 우대 2개×1점 = 8점이에요.
- 큰 숫자 %와 반드시 함께 쓰고, 아래에 `근거 점수 5 / 8`처럼 계산 근거를 적어요.

### 과제 카드 + 완료 토글
- 크림 블록 안의 흰 카드(16px)예요.
- 완료 전: 흰 알약 버튼 + 빈 체크박스, "과제 완료로 표시"
- 완료 후: 검정 알약 + 초록 체크박스, "완료! 근거로 등록됨"
- `aria-pressed`로 상태를 표시하고, 바뀌는 준비도 숫자에는 `aria-live="polite"`를 달아요.

### 검정 띠 / 코럴 CTA 블록
- 검정 띠는 원칙("링크 없으면 증거 아님.")을 말할 때만 써요.
- 코럴 블록은 페이지 맨 끝 CTA에만 한 번 써요.

## 6. 숫자 규칙 (기획서와 반드시 일치)

```
준비도 = 근거가 확인된 요구사항 배점 합 / 전체 배점 합
자격 요건 = 2점, 우대 사항 = 1점
링크로 확인되는 근거(커밋, PR, 배포 주소, 자소서 문단)만 인정
```

화면에 나오는 모든 %는 이 공식으로 계산돼야 해요. 예시 값은 5/8 = 63%, 과제(2점) 완료 후 7/8 = 88%예요. **근거 없는 숫자, 지어낸 통계, 가짜 후기는 넣지 않아요.**

## 7. 하지 말 것 (AI 티 방지)

- ❌ 가운데 정렬 히어로 + 알약 배지 + 그림자 카드 3장 조합
- ❌ 그라데이션 배경, 글로우, 반투명 유리 카드
- ❌ 이모지, 반짝이 아이콘
- ❌ 굵은(700+) 대형 헤드라인
- ❌ 정해진 다섯 값 밖의 모서리, 새로운 색
- ❌ 계산 근거 없는 숫자
- ❌ 한 화면에 검정 주 버튼 두 개 이상

## 8. 반응형

- 1440 데스크톱과 390 폰에서 모두 확인해요. 폰 너비에서 가로 스크롤이 생기면 안 돼요.
- 헤더는 `flex-wrap`으로 줄바꿈되고, 블록 그리드는 한 줄에 하나씩 쌓여요.
- 헤드라인과 큰 숫자는 `clamp()`로 줄어들어요.

## 9. AI 코딩 도구에게 줄 지시문

> 이 프로젝트의 UI는 루트의 DESIGN.md를 따른다. 색·폰트·모서리·간격은 DESIGN.md의 토큰만 쓰고, 새 값이 필요하면 만들지 말고 먼저 제안해라. 화면을 바꿀 때는 개선안을 먼저 제안하고, 승인한 항목만 하나씩 수정한다.
