> 치환본 — `docs/privacy_policy_template.md` 기반, `{{APP_NAME}}=Block Pop!` 등 플레이스홀더 치환 완료.
> 연락처 이메일 `grnamu@gmail.com` — 2026-07-18 사용자 승인으로 확정 치환 완료.
> ⚠️ 본 문서는 법률 자문이 아닙니다. 출시 전 법률 전문가 검토 필요.
> 부록(§10)에 Google Play 데이터 안전 폼 답변 매핑표(광고 미연결 현재 상태 vs AdMob 실 SDK 연결 후)를 포함합니다 — blockmochi와 달리 별도 파일로 분리하지 않고 이 문서 한 곳에 통합.

---

# Block Pop! 개인정보처리방침 (한국어)

**시행일: 2026-07-14**

GameFactory Studio(이하 "개발자")는 Block Pop!(이하 "앱", 패키지 `com.casualgamefactory.blockpop`) 이용자의
개인정보를 중요시하며, 「개인정보 보호법」 등 관련 법령을 준수합니다.

## 1. 수집하는 정보

앱은 회원가입 없이 이용 가능하며, 개발자는 이용자를 직접 식별할 수 있는 정보를 수집하지 않습니다.
다만 광고 제공을 위해 아래 제3자 서비스가 자동으로 수집하는 정보가 있습니다.

### 1.1 자동 수집 정보 (광고 SDK)
- 광고 식별자 (Google Advertising ID / Apple IDFA)
- 기기 정보 (모델, OS 버전, 언어, 화면 크기)
- 대략적 위치 정보 (IP 기반 국가/지역 수준)
- 광고 상호작용 정보 (노출, 클릭)

> **현재 상태**: 위 광고 SDK 수집 항목은 `Assets/Scripts/Game/FakeLocalAdService.cs`(로컬 전용,
> 실 SDK 미연결) 상태에서는 발생하지 않습니다. 실 AdMob SDK 연결 시점부터 유효해지며,
> 연결 즉시 §10 부록 표 기준으로 이 문서와 Play Console 데이터 안전 폼을 갱신해야 합니다.

### 1.2 기기 내 저장 정보 (외부 전송 없음)
- 게임 진행 상태(무한/어드벤처/데일리 진행도), 점수, 설정(사운드·음악·햅틱), 코인/부스터/스킨 보유 현황,
  시즌 포인트, 스트릭 일수, 데일리 챌린지·데일리 보상 기록, FTUE 완료 플래그, 테마(클래식/우드/네온) 해금 상태
- 위 데이터는 이용자의 기기(PlayerPrefs)에만 저장되며 개발자 서버로 전송되지 않습니다.

## 2. 제3자 서비스

앱은 광고 게재를 위해 다음 서비스를 사용합니다 (실 SDK 연결 시점부터 적용):

| 서비스 | 제공자 | 개인정보처리방침 |
|---|---|---|
| AdMob | Google LLC | https://policies.google.com/privacy |

Google의 광고 데이터 사용 방식: https://policies.google.com/technologies/partner-sites

## 3. 정보 이용 목적

- 배너/전면/보상형 광고 게재 및 광고 성과 측정
- 앱 안정성 개선 (충돌 정보)

## 4. 보유 및 파기

- 기기 내 저장 데이터: 앱 삭제 시 함께 삭제됩니다.
- 광고 SDK 수집 데이터: 각 제공자의 정책에 따릅니다.

## 5. 이용자의 권리

- **광고 식별자 재설정/삭제**: Android 설정 → Google → 광고 / iOS 설정 → 개인정보 보호 → 추적
- **맞춤 광고 거부**: 위 설정에서 맞춤 광고를 제한할 수 있습니다.
- 게임 데이터 초기화: 앱 삭제 또는 앱 내 설정 → 데이터 초기화

## 6. 아동의 개인정보

앱은 만 14세 미만 아동을 주 대상으로 하지 않습니다.
아동 대상으로 서비스할 경우 개발자는 Google Play 가족 정책 및 COPPA를 준수하도록
광고 요청을 아동 대상 처리(TFCD/TFUA)로 설정합니다.

## 7. 개인정보처리방침의 변경

정책 변경 시 본 페이지를 통해 고지합니다.

## 8. 문의

- 개발자: GameFactory Studio
- 이메일: grnamu@gmail.com

---

# Block Pop! Privacy Policy (English)

**Effective date: 2026-07-14**

GameFactory Studio ("we", "the developer") operates the Block Pop! mobile application
("the App", package `com.casualgamefactory.blockpop`). This page informs you of our policies
regarding the collection, use, and disclosure of information.

## 1. Information We Collect

The App can be used without creating an account. We do not directly collect personally
identifiable information. However, third-party advertising services automatically collect:

### 1.1 Automatically Collected (Ad SDK)
- Advertising identifiers (Google Advertising ID / Apple IDFA)
- Device information (model, OS version, language, screen size)
- Coarse location (country/region level, derived from IP)
- Ad interaction data (impressions, clicks)

> **Current status**: the above ad-SDK items do not occur while
> `Assets/Scripts/Game/FakeLocalAdService.cs` (local-only, no real SDK connected) is in use.
> They take effect once the real AdMob SDK is connected — at that point both this document
> and the Play Console Data Safety form must be updated per the §10 appendix table.

### 1.2 Stored Locally on Your Device (never transmitted to us)
- Game progress (Endless/Adventure/Daily), scores, settings (sound/music/haptic),
  coins/boosters/skin ownership, season points, streak days, daily-challenge and
  daily-reward records, FTUE completion flag, theme (Classic/Wood/Neon) unlock status
- This data stays on your device (PlayerPrefs) and is never sent to our servers.

## 2. Third-Party Services

The App uses the following service for advertising (once the real SDK is connected):

| Service | Provider | Privacy Policy |
|---|---|---|
| AdMob | Google LLC | https://policies.google.com/privacy |

How Google uses data: https://policies.google.com/technologies/partner-sites

## 3. Purpose of Use

- Serving banner, interstitial, and rewarded advertisements; measuring ad performance
- Improving app stability (crash information)

## 4. Data Retention & Deletion

- Local game data is deleted when you uninstall the App.
- Data collected by ad SDKs is retained according to each provider's policy.

## 5. Your Rights

- **Reset/delete advertising ID**: Android Settings → Google → Ads / iOS Settings → Privacy → Tracking
- **Opt out of personalized ads** via the settings above.
- Reset game data: uninstall the App, or use in-app Settings → Reset Data.

## 6. Children's Privacy

The App is not primarily directed at children under 13.
If distributed in a children's category, we configure ad requests with
child-directed treatment (TFCD/TFUA) in compliance with Google Play Families Policy and COPPA.

## 7. GDPR / CCPA Notice

- **Legal basis (EEA/UK)**: consent, collected via the Google UMP consent form on first launch.
- **EEA/UK users** may withdraw consent in-app (Settings → Privacy Options).
- **California residents**: we do not "sell" personal information as defined by the CCPA;
  ad partners may process identifiers as described above. You may opt out of personalized ads
  via device settings.

## 8. Changes to This Policy

We may update this policy and will post changes on this page.

## 9. Contact

- Developer: GameFactory Studio
- Email: grnamu@gmail.com

---

## 10. 부록 — Google Play 데이터 안전 폼 답변 매핑표 (Data Safety Form Mapping)

> Play Console 앱 콘텐츠 → 데이터 보안 섹션 작성용 근거 자료. 두 단계로 구분:
> **① 현재 상태**(이 빌드 — `FakeLocalAdService`, 실 SDK 미연결, 수집 0) vs
> **② AdMob 실 SDK 스왑 후**(사용자 승인 게이트 — 연결 시점에 이 표 기준으로 실제 Play Console 폼 갱신).
> 실제 제출은 Play Console UI에서 진행하며, 이 표는 답변 근거 자료일 뿐 그 자체가 제출물은 아닙니다.

### 10.1 현재 상태 (이 빌드 기준)

`Assets/Scripts/Game/FakeLocalAdService.cs` — 로컬 전용 fake 구현. 실 광고 SDK 호출 없음,
네트워크 전송 없음. 게임 진행/설정/코인/부스터/스킨/테마 등 전 데이터는 기기 내 `PlayerPrefs`에만 저장.

**"앱이 사용자 데이터를 수집 또는 공유합니까?" → 아니요 (No)**

| 데이터 유형 | 수집 여부 | 비고 |
|---|---|---|
| 위치 | 아니요 | — |
| 개인 정보 | 아니요 | 회원가입/로그인 없음 |
| 금융 정보 | 아니요 | IAP 미연결 (`IapCatalog.cs`/`FakeLocalIapService.cs`는 fake 상태) |
| 앱 활동 | 아니요 | 분석 SDK 미연결 |
| 앱 정보 및 성능 | 아니요 | 크래시 리포팅 SDK 미연결 |
| 기기 또는 기타 ID | 아니요 | 광고 식별자 미수집 (fake 서비스) |

기기 내 저장(전송 없음) 항목: 점수/레벨(무한·어드벤처·데일리), 설정(사운드·음악·햅틱 토글),
코인/부스터/스킨 보유 현황, 시즌 포인트, 스트릭 일수, 데일리 챌린지·보상 완료 여부,
테마(클래식/우드/네온) 해금 상태, FTUE 완료 플래그.

### 10.2 AdMob 실 SDK 스왑 후 (사용자 승인 게이트 — 연결 시점에 반영)

`FakeLocalAdService`의 광고 호출 본문을 실 AdMob SDK 호출로 교체하는 순간부터 아래 항목이
실제로 발생하며, Play Console 폼을 이 표대로 갱신해야 함.

| 데이터 유형 | 수집 여부 | 공유 여부 | 목적 | 필수/선택 |
|---|---|---|---|---|
| 기기 또는 기타 ID (광고 ID) | 예 | 예 (Google AdMob) | 광고 게재, 광고 성과 측정 | 선택(맞춤 광고 거부 가능) |
| 앱 활동 (광고 상호작용: 노출/클릭) | 예 | 예 (Google AdMob) | 광고 게재 및 성과 측정 | 필수(광고 지면 이용 시) |
| 대략적 위치 (IP 기반 국가/지역) | 예 | 예 (Google AdMob) | 지역별 광고 타겟팅 | 선택 |
| 앱 정보 및 성능 (충돌 로그) | 조건부 | Google(연결 시) | 안정성 개선 | 선택 |

- **암호화 전송**: AdMob SDK는 전송 구간 암호화(TLS) 사용 — Play 콘솔 "데이터가 안전하게
  전송됩니까?" → 예로 답변 가능(SDK 표준 동작 기준, 실 연결 후 재확인 필요).
- **삭제 요청 경로**: 앱은 서버에 사용자 데이터를 보유하지 않으므로 앱 자체 삭제 요청 메커니즘은
  불필요. 광고 식별자 삭제/재설정은 OS 설정(Android 설정 → Google → 광고)에서 이용자가 직접 수행.
- **데이터 보안 서약**: 제3자(Google AdMob)에 한해 업계 표준 보안 관행 준수 서약 적용.

### 10.3 향후 확장 시 갱신 필요 항목 (참고)

PRD_BLOCKPOP.md §5.2 IAP SKU(`remove_ads`/`coin_s·m·l`/`starter_pack`/`theme_pack`)가 실 결제로
전환될 경우 아래도 같이 갱신해야 함:
- IAP 실 결제 연동(Google Play Billing) → "금융 정보 · 구매 내역" 수집·공유 항목 추가.
- 데일리 챌린지 리더보드(후속) 도입 시 → "앱 활동" 수집 항목에 리더보드/클라우드 세이브 데이터 추가.

### 10.4 관련 문서

- 이 문서 §1~9: 개인정보처리방침 본문
- 광고 스왑 지점 주석: `apps/blockpop_unity/Assets/Scripts/Game/FakeLocalAdService.cs` 파일 헤더
- PRD: `design/portfolio/PRD_BLOCKPOP.md` §5(수익화 배치 지점)
