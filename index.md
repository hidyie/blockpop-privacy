# Block Pop! 개인정보처리방침 (한국어)

**시행일: 2026-07-14 · 최종 개정일: 2026-09-15**

GameFactory Studio(이하 "개발자")는 Block Pop!(이하 "앱", Android 설치 앱 및 토스 미니앱 `block-pop`) 이용자의
개인정보를 중요시하며, 「개인정보 보호법」 등 관련 법령을 준수합니다.

## 1. 수집하는 정보

앱은 별도 회원가입 없이 이용 가능합니다. 개발자가 작성한 아래 A/B 이벤트에는 이름·사용자 ID·광고 ID·기기 ID를 추가하지 않습니다.
광고 및 분석 플랫폼이 자체적으로 처리하는 정보는 별개이며, 이 앱 전체가 개인정보를 처리하지 않는다는 의미는 아닙니다.

### 1.1 자동 수집 정보 (Google Play/AdMob)
- 광고 식별자 (Google Advertising ID / Apple IDFA)
- 기기 정보 (모델, OS 버전, 언어, 화면 크기)
- 대략적 위치 정보 (IP 기반 국가/지역 수준)
- 광고 상호작용 정보 (노출, 클릭)

### 1.2 기기 내 저장 정보 (외부 전송 없음)

이용하는 플랫폼과 제공 기능에 따라 다음 정보가 저장됩니다.
- 게임 진행 상태(무한/어드벤처/데일리 진행도), 점수, 설정(사운드·음악·햅틱), 코인/부스터/스킨 보유 현황,
  시즌 포인트, 스트릭 일수, 데일리 챌린지·데일리 보상 기록, 첫 안내 완료 여부, 테마(클래식/우드/네온) 해금 상태
- 위 데이터는 이용자의 기기에만 저장되며 개발자 서버로 전송되지 않습니다.
- A/B 배정 값, 등록 여부, 이벤트별 기록 여부, 최초 안내 노출 UTC 날짜도 로컬에 저장합니다. 이 저장 레코드 자체는 전송하지 않으며, 아래 허용 목록의 이벤트만 조건부 전송합니다.

### 1.3 토스 인앱 광고

토스 미니앱은 하단 배너, 전면형, 보상형 광고를 제공할 수 있습니다. 광고 요청·노출·클릭 등의 정보는 토스 광고 플랫폼과 해당 광고 제공자가 처리하며, 구체적인 처리 범위는 각 제공자의 정책에 따릅니다. 이 정보는 아래에서 설명하는 개발자의 A/B 분석 항목과 별개입니다.

광고 표시 및 크기 정보는 화면의 광고 공간을 관리하는 데 사용합니다. A/B 분석의 첫 광고 노출은 실제 광고 노출 이벤트를 기준으로 기록합니다. 보상형 광고의 보상은 광고 제공자가 시청 완료를 알린 경우에 지급합니다.

### 1.4 토스 첫 안내 A/B 분석 (기능 활성화 시)

실험 `first_hint_v1`, 버전 `1`은 첫 안내 문구 A/B만 비교합니다. 배정은 로컬 무작위 값으로 저장하며, 점수·손패·난도·5콤보 테마 보상·광고 빈도는 바꾸지 않습니다. 최초 안내를 아직 완료하지 않은 설치가 등록 대상입니다.

| 커스텀 전송 필드 | 허용 값 |
|---|---|
| `log_name` | `bp_ab_<event>` |
| `experiment_id` | `first_hint_v1` |
| `variant` | `A` 또는 `B` |
| `event` | `exposure`, `first_place`, `first_clear`, `first_game_end`, `first_tool_open`, `first_ad_impression`, `d1_return` |
| `version` | `1` |

위 이벤트는 각각 첫 안내 표시, 첫 성공 배치, 첫 소거, 첫 게임 종료, 첫 도구 메뉴 열기, 실제 첫 광고 노출, 노출 다음 UTC 달력 날짜의 앱 실행/복귀를 뜻합니다. 노출 이후 각 이벤트를 로컬 설치당 최대 1회 기록합니다. D1은 자발적 재방문이나 정확한 24시간 경과를 뜻하지 않습니다. 이름·사용자 ID·광고 ID·기기 ID·점수·위치·자유 입력·로컬 노출 날짜를 커스텀 페이로드에 추가하지 않습니다.

이 분석은 토스에서 제공되는 정식 서비스에서 실험과 분석 기능이 활성화된 경우에만 토스 분석 서비스로 전송합니다. 분석 기능이 꺼져 있어도 광고 플랫폼의 정보 처리는 별도로 이루어질 수 있습니다.

각 이벤트는 중복 전송을 방지하도록 기록하며, 전송이 실패한 이벤트는 다시 전송하지 않습니다. 저장 데이터를 삭제하거나 앱을 다시 설치하면 새로운 안내 문구가 배정될 수 있습니다. 개발자의 커스텀 분석 항목으로 개인이나 여러 기기의 이용 이력을 연결하지 않습니다.

## 2. 제3자 서비스

앱은 배포 플랫폼과 활성화 설정에 따라 다음 서비스를 사용합니다:

| 서비스 | 제공자 | 개인정보처리방침 |
|---|---|---|
| AdMob | Google LLC | https://policies.google.com/privacy |
| 토스 인앱 광고·분석 | Apps in Toss / 토스 | [토스 개인정보처리방침](https://privacy.toss.im/privacy-policy) 및 해당 광고 제공자의 정책 확인 |

Google의 광고 데이터 사용 방식: https://policies.google.com/technologies/partner-sites

## 3. 정보 이용 목적

- 배너/전면/보상형 광고 게재 및 광고 성과 측정
- 앱 안정성 개선 (충돌 정보)
- 토스 첫 안내의 이용 편의성 비교: 첫 배치·소거·메뉴 이용·게임 종료·다음 날 복귀 비율 분석(§1.4 활성화 조건 적용)

## 4. 보유 및 파기

- Android 설치 앱의 로컬 데이터는 앱 데이터 삭제 또는 앱 제거로 삭제할 수 있습니다.
- 토스 미니앱은 토스 내 저장 공간을 사용합니다. 데이터 삭제 방법과 범위는 토스 앱의 도움말 또는 아래 문의처를 통해 확인해 주세요. 미니앱을 닫는 것과 데이터를 삭제하는 것은 다릅니다.
- 광고 SDK 수집 데이터: 각 제공자의 정책에 따릅니다.
- 토스 광고·분석 데이터의 보유 및 삭제는 플랫폼 정책에 따릅니다. 로컬 기록 삭제가 이미 플랫폼에 전달된 이벤트 삭제를 보장하지는 않습니다. 문의는 §8 연락처로 가능합니다.

## 5. 이용자의 권리

- **광고 식별자 재설정/삭제**: Android 설정 → Google → 광고 / iOS 설정 → 개인정보 보호 → 추적
- **맞춤 광고 거부**: 위 설정에서 맞춤 광고를 제한할 수 있습니다.
- 게임 데이터 삭제 방법은 위 §4의 플랫폼별 안내를 확인해 주세요. 삭제 관련 문의는 §8로 연락할 수 있습니다.
- **Google Play/AdMob 배포**: Google 광고가 활성화된 경우 Google의 동의 관리 서비스를 통해 동의 정보를 갱신하고, 필요한 경우 동의 양식을 표시한 뒤 광고 요청 가능 여부를 확인합니다. 현재 앱 설정에는 Google 동의 양식을 다시 여는 별도 기능이 없습니다. 개인정보 관련 문의는 §8을 이용해 주세요.
- **토스 배포**: Google 광고 동의 관리와 별개이며, 플랫폼 개인정보 설정은 [토스 개인정보처리방침](https://privacy.toss.im/privacy-policy), 해당 제공자의 정책 및 토스 앱 내 도움말을 확인해 주세요.

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

**Effective date: 2026-07-14 · Last revised: 2026-09-15**

GameFactory Studio ("we", "the developer") operates the Block Pop! mobile application
("the App", including the Android app and Toss mini-app `block-pop`). This page informs you of our policies
regarding the collection, use, and disclosure of information.

## 1. Information We Collect

The App does not require a separate registration. Our custom A/B payload does not add names,
user IDs, advertising IDs, or device IDs. This does not mean that the App or its advertising
and analytics platforms process no personal information.

### 1.1 Automatically Collected (Google Play/AdMob)
- Advertising identifiers (Google Advertising ID / Apple IDFA)
- Device information (model, OS version, language, screen size)
- Coarse location (country/region level, derived from IP)
- Ad interaction data (impressions, clicks)

### 1.2 Stored Locally on Your Device (never transmitted to us)

The following information is stored according to the platform and features you use.
- Game progress (Endless/Adventure/Daily), scores, settings (sound/music/haptic),
  coins/boosters/skin ownership, season points, streak days, daily-challenge and
  daily-reward records, first-hint completion status, theme (Classic/Wood/Neon) unlock status
- This data stays on your device and is never sent to our servers.
- A/B assignment, enrolment, event flags and the exposure UTC date are stored locally. The stored record itself is not transmitted; the conditional events below use a separate fixed payload.

### 1.3 Toss In-App Advertising

The Toss mini-app may provide banner, interstitial and rewarded advertisements. Toss and the applicable advertising provider process ad requests, impressions and interactions according to their policies. This processing is separate from our custom A/B analytics fields described below.

Ad display and size information is used to manage advertising space. The first ad impression in our A/B analytics is recorded from an actual advertising impression event. Rewarded-ad benefits are granted when the advertising provider confirms completion.

### 1.4 Optional Toss First-Hint A/B Analytics

Experiment `first_hint_v1`, version `1`, changes only first-hint copy for installations that have not completed that hint. Local random assignment is retained; gameplay rules and ad frequency remain identical. The only custom fields are `log_name` (`bp_ab_<event>`), `experiment_id` (`first_hint_v1`), `variant` (`A`/`B`), `event`, and `version` (`1`). Allowed events are `exposure`, `first_place`, `first_clear`, `first_game_end`, `first_tool_open`, `first_ad_impression`, and `d1_return`. Each is recorded at most once per local installation after exposure. D1 means launch/foreground return on the next UTC calendar date, not proof of voluntary return or a 24-hour interval. Scores, location, free text and the local exposure date are not added to this payload.

These analytics are sent to the Toss analytics service only when the experiment and analytics features are enabled in the official Toss service. Disabling this analysis does not stop separate processing by advertising platforms.

Events are recorded to prevent duplicate transmission; failed transmissions are not retried. Reinstalling the app or clearing stored data may create a new assignment. Our custom analytics fields do not link individuals or their activity across devices.

## 2. Third-Party Services

The App uses the following services depending on distribution platform and enabled settings:

| Service | Provider | Privacy Policy |
|---|---|---|
| AdMob | Google LLC | https://policies.google.com/privacy |
| Toss in-app advertising and analytics | Apps in Toss / Toss | See the [Toss privacy policy](https://privacy.toss.im/privacy-policy) and the applicable advertising provider policy |

How Google uses data: https://policies.google.com/technologies/partner-sites

## 3. Purpose of Use

- Serving banner, interstitial, and rewarded advertisements; measuring ad performance
- Improving app stability (crash information)
- Comparing first-hint usability through placement, clear, game-end, tool-open and next-day-return rates under section 1.4.

## 4. Data Retention & Deletion

- Local data in the Android app can be deleted by clearing its app data or uninstalling it.
- The Toss mini-app uses storage within Toss. Consult help in the Toss app or contact us below for deletion methods and scope. Closing the mini-app does not mean its stored data has been deleted.
- Data collected by ad SDKs is retained according to each provider's policy.
- Toss advertising/analytics retention and deletion follow platform policies. Deleting local records does not ensure deletion of events already delivered to the platform; contact us through section 9 for enquiries.

## 5. Your Rights

- **Reset/delete advertising ID**: Android Settings → Google → Ads / iOS Settings → Privacy → Tracking
- **Opt out of personalized ads** via the settings above.
- For game-data deletion, see the platform-specific information in section 4. Contact us through section 9 with deletion enquiries.

## 6. Children's Privacy

The App is not primarily directed at children under 14.
If distributed in a children's category, we configure ad requests with
child-directed treatment (TFCD/TFUA) in compliance with Google Play Families Policy and COPPA.

## 7. GDPR / CCPA Notice

- **Google Play/AdMob distribution**: when Google advertising is enabled, Google’s consent management service updates consent information and shows a form when required before requesting ads. This is not the consent flow for Toss.
- The current App settings do not provide a separate action to reopen the Google consent form. For privacy enquiries, use section 9.
- **Toss distribution**: consult the [Toss privacy policy](https://privacy.toss.im/privacy-policy), the applicable provider policy, and help available in the Toss app for platform privacy settings.
- **California residents**: we do not "sell" personal information as defined by the CCPA;
  ad partners may process identifiers as described above. You may opt out of personalized ads
  via device settings.

## 8. Changes to This Policy

We may update this policy and will post changes on this page.

## 9. Contact

- Developer: GameFactory Studio
- Email: grnamu@gmail.com
