# Block PopPop 개인정보처리방침 (한국어)

**시행일: 2026-07-14 · 최종 개정일: 2026-10-26**

solmiir(이하 "개발자")는 Block PopPop(이하 "앱", Google Play Android 앱 `com.casualgamefactory.blockpoppop` 및 토스 미니앱 `block-pop`) 이용자의
개인정보를 중요시하며, 「개인정보 보호법」 등 관련 법령을 준수합니다.

## 1. 수집하는 정보

앱은 별도 회원가입 없이 이용 가능합니다. 개발자가 작성한 아래 A/B 이벤트에는 이름·사용자 ID·광고 ID·기기 ID를 추가하지 않습니다.
광고 및 분석 플랫폼이 자체적으로 처리하는 정보는 별개이며, 이 앱 전체가 개인정보를 처리하지 않는다는 의미는 아닙니다.

### 1.1 자동 수집 정보 (Google Play/AdMob)
- 기기·계정 식별자 (Android 광고 ID, 앱 세트 ID 등)
- 기기 정보 (모델, OS 버전, 언어, 화면 크기)
- IP 주소 (대략적 위치 추정에 쓰일 수 있음)
- 앱 상호작용 정보 (앱 실행, 탭, 동영상 조회, 광고 노출·클릭)
- 진단 정보 (앱·SDK 성능: 실행 시간, 응답 없음 비율, 에너지 사용량)

위 항목은 Google Mobile Ads SDK가 광고 게재, 분석, 사기 방지를 위해 자동으로 수집·Google과 공유합니다. 광고 ID 수집은 이용자가 Android 설정에서 재설정·삭제할 수 있습니다.

### 1.2 기기 내 저장 정보 (외부 전송 없음)

이용하는 플랫폼과 제공 기능에 따라 다음 정보가 저장됩니다.
- 게임 진행 상태(무한/데일리 진행도), 점수, 설정(사운드·음악·햅틱), 코인/부스터/스킨 보유 현황,
  시즌 포인트, 스트릭 일수, 데일리 챌린지·데일리 보상 기록, 첫 안내 완료 여부, 블록 테마 진행 상태
- 위 데이터는 이용자의 기기에만 저장되며 개발자 서버로 전송되지 않습니다.
- A/B 배정 값, 등록 여부, 이벤트별 기록 여부, 최초 안내 노출 UTC 날짜도 로컬에 저장합니다. 이 저장 레코드 자체는 전송하지 않으며, 아래 허용 목록의 이벤트만 조건부 전송합니다.

### 1.3 토스 인앱 광고

토스 미니앱은 하단 배너, 전면형, 보상형 광고를 제공할 수 있습니다. 광고 요청·노출·클릭 등의 정보는 토스 광고 플랫폼과 해당 광고 제공자가 처리하며, 구체적인 처리 범위는 각 제공자의 정책에 따릅니다. 이 정보는 아래에서 설명하는 개발자의 A/B 분석 항목과 별개입니다.

광고 표시 및 크기 정보는 화면의 광고 공간을 관리하는 데 사용합니다. A/B 분석의 첫 광고 노출은 실제 광고 노출 이벤트를 기준으로 기록합니다. 보상형 광고의 보상은 광고 제공자가 시청 완료를 알린 경우에 지급합니다.

### 1.4 토스 첫 안내 A/B 분석 (기능 활성화 시)

실험 `first_hint_v1`, 버전 `1`은 첫 안내 문구 A/B만 비교합니다. 배정은 로컬 무작위 값으로 저장하며, 점수·손패·난도·콤보 테마 보상·광고 빈도는 바꾸지 않습니다. 최초 안내를 아직 완료하지 않은 설치가 등록 대상입니다.

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

### 1.5 로컬 알림 (Android 13+ 권한 필요, 2026-09-24 추가)

앱은 Android 공식 Mobile Notifications 패키지로 기기 내 예약 알림(스트릭 위험·데일리 챌린지 대기 등)을 보냅니다. 서버로 전송되는 데이터는 없습니다 — 알림 문구와 발송 시각은 §1.2에서 이미 기기 내에만 저장된다고 설명한 스트릭 일수·데일리 챌린지 완료 여부에서 전적으로 로컬로 계산합니다. Android 13 이상에서는 알림 권한을 요청하며, 앱 실행 시가 아니라 이용자가 첫 게임을 완료한 직후 1회만 요청합니다. 권한을 거부해도 다른 기능에는 영향이 없습니다.

### 1.6 분석 SDK (기본 비활성 — 활성화 시에만 적용)

현재 배포본은 분석 데이터를 어디에도 전송하지 않는 무동작(no-op) 분석 구조만 포함하고 있으며, Firebase 등 실 분석 SDK는 이 저장소에 포함되어 있지 않습니다. 향후 별도 절차로 활성화되면 최초 실행·최초 소거·게임 종료 점수·광고 노출/보상·데일리 챌린지 완료·보드 전체 클리어 등의 이벤트가 Google로 전송될 수 있으며, 이 경우 본 방침을 갱신해 고지합니다.

### 1.7 인앱 구매 (Google Play 결제)

앱은 선택형 인앱 구매(광고 제거, 코인 묶음 등)를 Google Play 결제(Google Play Billing)로 제공합니다. 결제는 전적으로 Google Play가 처리하며, 개발자는 카드번호 등 결제 수단 정보를 받지 않고 저장하지도 않습니다. 앱은 구매 상태와 주문 기록(주문·거래 ID, 상품 ID, 처리 상태, 시각)을 **기기 안에만** 저장하며, 이 기록은 구매한 항목을 지급하고, 같은 구매의 중복 지급을 막고, 구매 복원을 처리하는 데에만 사용합니다. 앱은 Google Play가 서명한 구매 정보를 기기에서 서명 검증합니다. 환불과 구매 관리는 Google Play(Play 스토어 앱의 결제 및 정기 결제 메뉴)를 통해 이루어집니다. 기기 내 구매 기록은 앱을 삭제하거나 앱 데이터를 지울 때까지 기기에 남습니다.

### 1.8 Google Play 게임즈 서비스 (랭킹, Google Play 버전)

Google Play 버전의 앱은 랭킹(리더보드) 기능을 위해 Google Play 게임즈 서비스를 사용합니다. 이용자가 Play 게임즈에 로그인하면 Google이 **플레이어 ID와 닉네임(프로필 이름)**을 앱에 제공하고, 앱은 이용자의 **점수(클래식 최고 점수, 달성한 최고 레벨)**를 Google Play 게임즈 서버로 보내 순위를 계산하고 보여 줍니다. 리더보드에서는 닉네임과 점수가 다른 플레이어에게 보일 수 있습니다. 이 정보의 수집·저장·공개는 Google의 정책(https://policies.google.com/privacy)에 따르며, 개발자는 이 기능을 위해 점수 외의 개인정보를 따로 받거나 저장하지 않습니다. 로그인은 선택 사항이며, 로그인하지 않아도 게임의 모든 내용을 이용할 수 있습니다. Play 게임즈 프로필과 점수는 이용자의 Google 계정과 Google Play 게임즈 설정에서 관리·삭제를 요청할 수 있습니다. 토스 버전에는 이 기능이 포함되어 있지 않습니다.

## 2. 제3자 서비스

앱은 배포 플랫폼과 활성화 설정에 따라 다음 서비스를 사용합니다:

| 서비스 | 제공자 | 개인정보처리방침 |
|---|---|---|
| AdMob | Google LLC | https://policies.google.com/privacy |
| Google Play 결제 (Google Play Billing) | Google LLC | https://policies.google.com/privacy |
| Google Play 게임즈 서비스 (랭킹) | Google LLC | https://policies.google.com/privacy |
| 토스 인앱 광고·분석 | Apps in Toss / 토스 | [토스 개인정보처리방침](https://privacy.toss.im/privacy-policy) 및 해당 광고 제공자의 정책 확인 |

Google의 광고 데이터 사용 방식: https://policies.google.com/technologies/partner-sites

## 3. 정보 이용 목적

- 배너/전면/보상형 광고 게재 및 광고 성과 측정
- 인앱 구매 처리·구매 항목 지급·구매 복원(§1.7)
- 앱 안정성 개선 (충돌 정보)
- 토스 첫 안내의 이용 편의성 비교: 첫 배치·소거·메뉴 이용·게임 종료·다음 날 복귀 비율 분석(§1.4 활성화 조건 적용)

## 4. 보유 및 파기

- Android 설치 앱의 로컬 데이터는 앱 데이터 삭제 또는 앱 제거로 삭제할 수 있습니다.
- 구매 상태와 주문 기록은 기기에만 저장되며 앱을 삭제하거나 앱 데이터를 지울 때까지 남습니다. Google Play 쪽 결제·환불 기록은 Google의 정책에 따릅니다(§1.7).
- 토스 미니앱은 토스 내 저장 공간을 사용합니다. 데이터 삭제 방법과 범위는 토스 앱의 도움말 또는 아래 문의처를 통해 확인해 주세요. 미니앱을 닫는 것과 데이터를 삭제하는 것은 다릅니다.
- 광고 SDK 수집 데이터: 각 제공자의 정책에 따릅니다.
- 토스 광고·분석 데이터의 보유 및 삭제는 플랫폼 정책에 따릅니다. 로컬 기록 삭제가 이미 플랫폼에 전달된 이벤트 삭제를 보장하지는 않습니다. 문의는 §8 연락처로 가능합니다.

## 5. 이용자의 권리

- **광고 식별자 재설정/삭제**: Android 설정 → Google → 광고
- **맞춤 광고 거부**: 위 설정에서 맞춤 광고를 제한할 수 있습니다.
- 게임 데이터 삭제 방법은 위 §4의 플랫폼별 안내를 확인해 주세요. 삭제 관련 문의는 §8로 연락할 수 있습니다.
- **구매 관리·환불**: Google Play(Play 스토어 앱의 결제 및 정기 결제 메뉴)에서 구매 내역 확인과 환불 요청을 할 수 있습니다. 앱 데이터를 지우면 기기 내 구매 기록도 삭제됩니다(§1.7).
- **Google Play/AdMob 배포**: Google 광고가 활성화된 경우 Google의 동의 관리 서비스를 통해 동의 정보를 갱신하고, 필요한 경우 동의 양식을 표시한 뒤 광고 요청 가능 여부를 확인합니다. 동의가 필요한 지역(EEA·영국·스위스)에서는 앱 설정 → Privacy options(개인정보 옵션) 버튼으로 Google 동의 양식을 언제든 다시 열어 동의를 변경하거나 철회할 수 있습니다. 그 외 지역에서는 이 버튼이 표시되지 않습니다. 개인정보 관련 문의는 §8을 이용해 주세요.
- **토스 배포**: Google 광고 동의 관리와 별개이며, 플랫폼 개인정보 설정은 [토스 개인정보처리방침](https://privacy.toss.im/privacy-policy), 해당 제공자의 정책 및 토스 앱 내 도움말을 확인해 주세요.

## 6. 아동의 개인정보

앱은 만 14세 미만 아동을 주 대상으로 하지 않습니다.
아동 대상으로 서비스할 경우 개발자는 Google Play 가족 정책 및 COPPA를 준수하도록
광고 요청을 아동 대상 처리(TFCD/TFUA)로 설정합니다.

미성년자의 인앱 구매에는 법정대리인(보호자)의 동의가 필요합니다.

## 7. 개인정보처리방침의 변경

정책 변경 시 본 페이지를 통해 고지합니다.

## 8. 문의

- 개발자: solmiir
- 이메일: contact@solmiir.com

---

# Block PopPop Privacy Policy (English)

**Effective date: 2026-07-14 · Last revised: 2026-10-26**

solmiir ("we", "the developer") operates the Block PopPop mobile application
("the App", including the Google Play Android app `com.casualgamefactory.blockpoppop` and Toss mini-app `block-pop`). This page informs you of our policies
regarding the collection, use, and disclosure of information.

## 1. Information We Collect

The App does not require a separate registration. Our custom A/B payload does not add names,
user IDs, advertising IDs, or device IDs. This does not mean that the App or its advertising
and analytics platforms process no personal information.

### 1.1 Automatically Collected (Google Play/AdMob)
- Device and account identifiers (Android advertising ID, app set ID, and similar)
- Device information (model, OS version, language, screen size)
- IP address (may be used to estimate approximate location)
- App interactions (app launch, taps, video views, ad impressions and clicks)
- Diagnostics (app and SDK performance such as launch time, hang rate, energy use)

The Google Mobile Ads SDK collects these automatically and shares them with Google for advertising, analytics and fraud prevention. You can reset or delete the advertising ID in Android settings.

### 1.2 Stored Locally on Your Device (never transmitted to us)

The following information is stored according to the platform and features you use.
- Game progress (Endless/Daily), scores, settings (sound/music/haptic),
  coins/boosters/skin ownership, season points, streak days, daily-challenge and
  daily-reward records, first-hint completion status, block-theme progress
- This data stays on your device and is never sent to our servers.
- A/B assignment, enrolment, event flags and the exposure UTC date are stored locally. The stored record itself is not transmitted; the conditional events below use a separate fixed payload.

### 1.3 Toss In-App Advertising

The Toss mini-app may provide banner, interstitial and rewarded advertisements. Toss and the applicable advertising provider process ad requests, impressions and interactions according to their policies. This processing is separate from our custom A/B analytics fields described below.

Ad display and size information is used to manage advertising space. The first ad impression in our A/B analytics is recorded from an actual advertising impression event. Rewarded-ad benefits are granted when the advertising provider confirms completion.

### 1.4 Optional Toss First-Hint A/B Analytics

Experiment `first_hint_v1`, version `1`, changes only first-hint copy for installations that have not completed that hint. Local random assignment is retained; gameplay rules and ad frequency remain identical. The only custom fields are `log_name` (`bp_ab_<event>`), `experiment_id` (`first_hint_v1`), `variant` (`A`/`B`), `event`, and `version` (`1`). Allowed events are `exposure`, `first_place`, `first_clear`, `first_game_end`, `first_tool_open`, `first_ad_impression`, and `d1_return`. Each is recorded at most once per local installation after exposure. D1 means launch/foreground return on the next UTC calendar date, not proof of voluntary return or a 24-hour interval. Scores, location, free text and the local exposure date are not added to this payload.

These analytics are sent to the Toss analytics service only when the experiment and analytics features are enabled in the official Toss service. Disabling this analysis does not stop separate processing by advertising platforms.

Events are recorded to prevent duplicate transmission; failed transmissions are not retried. Reinstalling the app or clearing stored data may create a new assignment. Our custom analytics fields do not link individuals or their activity across devices.

### 1.5 Local Notifications (Android 13+ permission, added 2026-09-24)

The App uses the official Android Mobile Notifications package to post scheduled on-device reminders (e.g. streak-at-risk, daily-challenge-waiting). Nothing is sent to a server: the message and timing are computed entirely on-device from the streak-day and daily-challenge data already described as local-only in §1.2. On Android 13 and later the App requests the notification permission — never at app launch, only once, right after the player's first-ever completed round. Declining has no effect on any other feature.

### 1.6 Analytics SDK (off by default — applies only if enabled)

The current build ships only a no-op analytics structure that sends nothing anywhere; a real analytics SDK (such as Firebase) is not included in this repository. If it is enabled through a separate future procedure, events such as first launch, first line clear, game-over score, ad impressions/rewards, daily-challenge completion, and full-board clears may be sent to Google, and this policy will be updated to disclose that change.

### 1.7 In-App Purchases (Google Play Billing)

The App offers optional in-app purchases (for example removing ads or coin packs) through Google Play Billing. Google Play processes every payment; the developer does not receive or store card numbers or other payment details. The App stores purchase state and an order record (order/transaction ID, product ID, status, timestamps) **only on your device**, and uses it solely to deliver purchased items, prevent the same purchase from being delivered twice, and restore purchases. The App verifies the Google Play purchase signature on the device. Refunds and purchase management are handled through Google Play (the Payments & subscriptions menu of the Play Store app). Purchase records on your device remain until you uninstall the App or clear its data.

### 1.8 Google Play Games Services (Rankings, Google Play version)

The Google Play version of the App uses Google Play Games Services for its rankings (leaderboards). When you sign in to Play Games, Google provides your **player ID and nickname (profile name)** to the App, and the App sends your **scores (best Classic score and highest level reached)** to Google Play Games servers so your rank can be calculated and shown. On a leaderboard, your nickname and score can be visible to other players. Google's policies (https://policies.google.com/privacy) govern how this information is collected, stored and displayed; the developer does not receive or store personal information other than the score for this feature. Signing in is optional, and the whole game works without it. You can manage your Play Games profile and scores, and request their deletion, through your Google Account and Google Play Games settings. The Toss version does not include this feature.

## 2. Third-Party Services

The App uses the following services depending on distribution platform and enabled settings:

| Service | Provider | Privacy Policy |
|---|---|---|
| AdMob | Google LLC | https://policies.google.com/privacy |
| Google Play Billing | Google LLC | https://policies.google.com/privacy |
| Google Play Games Services (rankings) | Google LLC | https://policies.google.com/privacy |
| Toss in-app advertising and analytics | Apps in Toss / Toss | See the [Toss privacy policy](https://privacy.toss.im/privacy-policy) and the applicable advertising provider policy |

How Google uses data: https://policies.google.com/technologies/partner-sites

## 3. Purpose of Use

- Serving banner, interstitial, and rewarded advertisements; measuring ad performance
- Processing in-app purchases, delivering purchased items and restoring purchases (section 1.7)
- Improving app stability (crash information)
- Comparing first-hint usability through placement, clear, game-end, tool-open and next-day-return rates under section 1.4.

## 4. Data Retention & Deletion

- Local data in the Android app can be deleted by clearing its app data or uninstalling it.
- Purchase state and order records are stored only on your device and remain until you uninstall the App or clear its data. Payment and refund records held by Google Play follow Google's policies (section 1.7).
- The Toss mini-app uses storage within Toss. Consult help in the Toss app or contact us below for deletion methods and scope. Closing the mini-app does not mean its stored data has been deleted.
- Data collected by ad SDKs is retained according to each provider's policy.
- Toss advertising/analytics retention and deletion follow platform policies. Deleting local records does not ensure deletion of events already delivered to the platform; contact us through section 9 for enquiries.

## 5. Your Rights

- **Reset/delete advertising ID**: Android Settings → Google → Ads
- **Opt out of personalized ads** via the settings above.
- For game-data deletion, see the platform-specific information in section 4. Contact us through section 9 with deletion enquiries.
- **Manage purchases and refunds**: view purchase history and request refunds through Google Play (Payments & subscriptions in the Play Store app). Clearing app data also deletes the purchase records stored on your device (section 1.7).

## 6. Children's Privacy

The App is not primarily directed at children under 14.
If distributed in a children's category, we configure ad requests with
child-directed treatment (TFCD/TFUA) in compliance with Google Play Families Policy and COPPA.

In-app purchases by minors require the consent of a parent or legal guardian.

## 7. GDPR / CCPA Notice

- **Google Play/AdMob distribution**: when Google advertising is enabled, Google’s consent management service updates consent information and shows a form when required before requesting ads. This is not the consent flow for Toss.
- In regions where consent is required (EEA, UK, Switzerland), Settings → Privacy options reopens the Google consent form at any time so you can change or withdraw your consent. Elsewhere this button is hidden. For privacy enquiries, use section 9.
- **Toss distribution**: consult the [Toss privacy policy](https://privacy.toss.im/privacy-policy), the applicable provider policy, and help available in the Toss app for platform privacy settings.
- **California residents**: we do not "sell" personal information as defined by the CCPA;
  ad partners may process identifiers as described above. You may opt out of personalized ads
  via device settings.

## 8. Changes to This Policy

We may update this policy and will post changes on this page.

## 9. Contact

- Developer: solmiir
- Email: contact@solmiir.com
