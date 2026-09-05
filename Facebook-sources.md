# Facebook / Meta / Instagram DNS inventory

Updated 2026-09-05 from the ML profile's stored DNS query history.

- UTC window: 2026-08-29T05:25:31.819Z through 2026-09-05T05:25:31.819Z.
- Scanned 1,911 distinct profile domains, without a result-row limit.
- Matched 988 distinct domains across 7,427 requests.
- 72 non-Netseer hostnames were observed. Preserved all 16 existing entries.
- 916 rotating Netseer names are covered by `xy.fbcdn.net` and `xz.fbcdn.net`; unique probe identifiers are not published.
- Final list: 76 entries; 60 additions, no removals. Every matched hostname is covered by an exact or parent rule under NextDNS denylist semantics.

## Selection and scope

Selected exact names or subdomains of Facebook, Instagram, Messenger and Meta service suffixes: facebook.com, facebook.net, fbcdn.net, fbsbx.com, instagram.com, cdninstagram.com, messenger.com, m.me, fb.me, meta.com, threads.net, threads.com, meta.ai, workplace.com and accountkit.com. Also included the exact observed `meta-ohttp-relay-prod.fastly-edge.com` host, whose Meta association is inferred from its service-specific name, and considered the existing Instagram static Akamai hostname family. No shared Fastly or Akamai parent domains are blocked. WhatsApp is outside this list's scope.

This is a service-blocking inventory, not an ads-only list. Observed traffic includes allowed and blocked requests; observation alone does not establish that a domain is necessary for DMs. The snapshot covers collected ML traffic, not every domain used worldwide or any uncollected query.

Parent rules cover subdomains when NextDNS-Pro imports them into NextDNS's denylist. Exact-match-only DNS blockers may need wildcard configuration for the two Netseer parents. Parent entries intentionally cover future names in these dedicated namespaces.

The custom Facebook / Meta list remains disabled on ML after refresh. Existing Facebook parental-control filtering remains independent, including gateway.facebook.com. No denylist or allowlist changes are part of this inventory update.
