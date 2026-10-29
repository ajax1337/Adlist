# Remaining six-domain review — 2026-10-29

These entries are attributed to their providers using vendor documentation, first-party integrations, vendor-authored code, or direct DNS aliases. Attribution does not establish harmful traffic. Functional endpoints remain in separate service inventories. Existing entries are preserved.

Advertising and analytics inventories can include affiliate redirects, measurement, and engagement functions. Service inventories include ordinary shopping, healthcare, subscriptions, and content delivery. Review the purpose before enabling a list.

## Advertising-tracking-inventory.txt

- `trk.pxlnow.in`: Add only observed trk host to existing disabled advertising/tracking inventory. Code proves affiliate-conversion measurement despite generic financial-dashboard login at root. No legal-operator claim, malware allegation, inference that the historical ML request carried all fields, parent wildcard, script execution or collector POST.
  - [Direct public script HTTP200: defines https://trk.pxlnow.in/jspix endpoint; on mtq track commands serializes goal_id, offer_id, click_id, sale_amount and timestamp, sent using sendBeacon with JSON Blob or POST fallback. Also loads webanalytics.space/unicard.js and initializes a Uni client. Full source and SHA256 retained; read as text only.](https://trk.pxlnow.in/js/tkpa/40.js)
  - [Existing public capture HTML retrieved successfully (not response/API bypass): www.uni.cards initiated exact /js/tkpa/40.js; that script initiated /jspix and webanalytics.space/unicard.js. This independently corroborates a deployed merchant tracking integration.](https://urlscan.io/result/01a12380-3a14-773a-aab4-570a43e691f9/)
  - [Blame traced pxlnow.in tracking-server rule to original April17 2026 maintainer addition. It is supporting history; classification now rests on direct implementation, not the filter-list label.](https://github.com/easylist/easylist/commit/bb8526851f172804f1896f83ecf87849c7ffae86)

## Boundaries

No broad shared-cloud, certificate, payment-platform, or unrelated merchant roots were added. Brand-like names without sufficient ownership proof remain excluded. Vendor-family attribution is distinguished from an exact documented endpoint in the notes above. These files are inventories, not a declaration that all traffic to each provider is advertising or malicious.
