# ML DNS and adlist review — 2026-09-28

Profile ML (`49f1d3`) was reviewed over the complete stored-log window from 2026-09-21T11:19:44.057Z through 2026-09-28T11:19:44.057Z (end exclusive). The window contains 36,205 queries and 1,867 distinct hostnames. This is stored DNS evidence, not proof of every device request or of an app launch. First-seen checks used the stored ML log history, not the incomplete `first_seen` ledger.

## Two different meanings of unclassified

- **Adlist coverage:** 1,576 hostnames (34,236 queries) matched one of the 17 existing logical GitHub lists by exact domain or parent-domain suffix. The other 291 hostnames (1,969 queries) did not. Coverage means list membership, not an active NextDNS block: several inventories are disabled.
- **App sessions:** Insights left 337 of 1,218 sessions without an app label. In 330 of those sessions, `apple.com` appeared even though Apple domains are already in existing lists and the candidate has a manual `system` category override. Seven roots appear across the unclassified sessions. App labeling and custom denylist membership are separate processes; adding DNS entries cannot by itself label those sessions.

No high-confidence missing entry was found in the 17 existing lists. In particular, Apple iAd and Amazon video telemetry names that looked absent in an older local checkout are present on current GitHub `main`. Existing source files and their live enabled states were preserved.

## Separate service inventories

The uncovered traffic included distinct services and shared SDK providers. New files hold only the observed hostname families and carefully selected stable parent domains. Each list remains disabled when registered as a NextDNS-Pro custom list. Counts below are newly covered hostnames and queries relative to the 17-list baseline; they are not incremental blocks.

| New file | Entries | Newly covered hosts | Queries |
|---|---:|---:|---:|
| `Firebase-telemetry-inventory.txt` | 3 | 3 | 961 |
| `Sentry-inventory.txt` | 8 | 7 | 107 |
| `Netflix-inventory.txt` | 30 | 26 | 84 |
| `Flo-inventory.txt` | 7 | 6 | 55 |
| `ChatGPT-inventory.txt` | 8 | 6 | 54 |
| `AppsFlyer-inventory.txt` | 9 | 8 | 54 |
| `Meesho-inventory.txt` | 8 | 7 | 46 |
| `Truecaller-inventory.txt` | 16 | 15 | 40 |
| `Microsoft-Clarity-inventory.txt` | 12 | 11 | 37 |
| `Razorpay-inventory.txt` | 7 | 7 | 29 |
| `Shopify-inventory.txt` | 9 | 7 | 27 |
| `Giphy-inventory.txt` | 7 | 6 | 21 |
| `Adjust-inventory.txt` | 2 | 1 | 17 |
| `Mixpanel-inventory.txt` | 3 | 2 | 14 |
| `Bugsnag-inventory.txt` | 3 | 2 | 11 |
| `Juspay-inventory.txt` | 3 | 2 | 10 |

Together these 16 lists cover 116 previously uncovered hostnames and 1,567 queries. The resulting GitHub inventory covers 1,692 of 1,867 observed hostnames and 35,803 of 36,205 queries. The remaining 175 hostnames account for 402 queries. These totals include overlap only once.

### Attribution boundaries

- Google owns [app-analytics-services.com](https://rdap.markmonitor.com/rdap/domain/app-analytics-services.com) and [app-measurement.com](https://rdap.markmonitor.com/rdap/domain/app-measurement.com); the [Firebase iOS SDK](https://github.com/firebase/firebase-ios-sdk/issues/15085) uses the former, and [Firebase measurement](https://github.com/firebase/firebase-ios-sdk/issues/5837) uses the latter. They are cross-app telemetry, so they belong in a Firebase provider list, not in whichever consumer app happened to make a nearby query. The third entry is an observed Crashlytics settings host.
- [Netflix Open Connect](https://openconnect.netflix.com/Open-Connect-Overview.pdf) serves Netflix video; registrar records identify Netflix for [nflxvideo.net](https://rdap.markmonitor.com/rdap/domain/nflxvideo.net) and [nflxso.net](https://rdap.markmonitor.com/rdap/domain/nflxso.net). The Netflix list contains functional streaming endpoints, not merely advertisements.
- [OpenAI's ChatGPT network guidance](https://help.openai.com/en/articles/9247338-network-recommendations-for-chatgpt-errors-on-web-and-apps) names `chatgpt.com`, `ios.chat.openai.com`, `oaistatic.com`, and the WebSocket host. The ChatGPT list includes exact observed `openai.com` subdomains, not a blanket `openai.com` parent.
- [Flo's terms](https://www.owhealth.com/terms_of_use.html) identify `owhealth.com` as Flo's domain. Insights also has a conflicting `icloud` signature for that root; the Flo list follows first-party ownership rather than that signature.
- [Microsoft Clarity's CSP guide](https://learn.microsoft.com/en-gb/clarity/setup-and-installation/clarity-csp) identifies `*.clarity.ms` and `c.bing.com`. The latter is listed exactly; the broader `bing.com` parent is not included.
- Meesho and Truecaller entries use their branded first-party host families. `meeshogcp.in` and `truecallerstatic.com` are held out because their ownership was not independently confirmed from a first-party source. Payment, shopping, and service lists contain functional endpoints and require explicit opt-in before blocking.

## New domains and unresolved traffic

Across the stored ML history, 25 root domains first appeared in this seven-day window. The largest were `px-cloud.net` (5 queries), `me-qr.com` (4), and `favpng.com` (4); the rest had at most 3 queries each. At hostname level, 1,015 of the 1,867 observed names first appeared in the window, largely rotating CDN names. None of the new roots had enough ownership evidence to add to an existing service list or enable a block automatically.

The 175 still-uncovered hostnames include shared CDNs (`cloudfront.net`, Akamai, Fastly), certificate-status services (`ocsp.digicert.com`, Sectigo), private/user-owned hosts, isolated merchant sites, and low-volume provider names. For example, `ocsp.digicert.com` had 29 queries and an opaque CloudFront hostname had 26. Neither is evidence of a missing app-specific block. Do not add broad `amazonaws.com`, `cloudfront.net`, `fastly-edge.com`, `akamaized.net`, or `akamaihd.net` parents to an app list, or assume that a matching time window proves app ownership. Sentry has its own disabled provider inventory instead.

This review does not change profile allowlists, native security/parental rules, schedules, or the active state of any custom list. The new files are service inventories, not curated ad-only lists. Enabling one can break a normal app, payment flow, or diagnostic service.
