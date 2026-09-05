# WhatsApp DNS inventory

Updated 2026-09-05 using profile ML's stored DNS history.

- UTC window: 2026-08-29T16:05:13.375Z through 2026-09-05T16:05:13.375Z.
- Scanned 1,961 distinct profile domains, with no result-row limit.
- Found 44 WhatsApp hostnames across 3,054 queries, including allowed and blocked requests.
- Added 20 previously missing observed hosts and the two observed service roots, whatsapp.com and whatsapp.net.
- Preserved all 25 existing entries, including older regional CDN hosts absent from this window.
- Final list: 47 entries (22 additions, no removals).

Selection uses exact WhatsApp roots and their subdomains, including wa.me when observed (none in this window). Broad name matching also surfaced wa.appsflyersdk.com and wa.onelink.me, but their association with WhatsApp was not established; they and their shared provider roots are excluded. No shared Facebook, Fastly, Akamai, CloudFront or AppsFlyer root is added.

WhatsApp's first-party connection guidance identifies web.whatsapp.com and .whatsapp.net as network dependencies: https://faq.whatsapp.com/web/troubleshooting/cant-connect-to-whatsapp

This is a full-service blocklist rather than an ads-only filter. NextDNS parent denylist entries cover subdomains; semantics may differ for exact-match-only DNS blockers. The inventory covers collected ML traffic, not every domain WhatsApp uses worldwide.

The WhatsApp custom list remains disabled on ML after this update. No allowlist or standalone denylist changes are part of this inventory refresh. Existing parental-control and scheduled rules operate independently.
