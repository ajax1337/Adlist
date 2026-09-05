# JioHotstar service blocking

Reviewed 2026-09-05. Both formats contain the same domain set.

## Evidence and changes

- https://www.jiohotstar.com/ redirects to https://www.hotstar.com/ (checked 2026-09-05).
- https://raw.githubusercontent.com/v2fly/domain-list-community/master/data/hotstar lists hotstar.com, hotstar-cdn.net, hotstar-labs.com, hotstarext.com, hsprepack.akamaized.net and hses CDN hosts. Added the missing parent domains and copied existing CDN entries into the plain-domain format.
- https://secure-media.hotstar.com/debug/t1re.html is the first-party JioHotstar debugger; its live HTML was fetched from Mumbai on the review date. Extracted 30 additional first-party API, TV and SSAI streaming hostnames, including apix.hotstar.com, livingroom.hotstar.com and live11p-ssai-akt-ncw-mum.cdn.hotstar.com. Shared ExpressPlay DRM and third-party debugging hosts were excluded.
- Preserved the union of both existing repository lists, including legacy JioCinema/Voot endpoints. Added voot.com to cover the existing Voot endpoint family. Legacy entries are retained for compatibility, not represented as newly verified active hosts.

## Scope

Full service denial, not ad removal. NextDNS denylist parent entries cover subdomains, including changing API and CDN hostnames. The plain-domain file is applied through NextDNS-Pro custom adlists; raw-domain semantics can differ in other blockers.

No blanket jio.com, akamaized.net, cloudfront.net or shared CDN IP blocks are added. Existing legacy Jio TV/news/meet entries are retained from the previous list.

DNS policy only applies to clients using the profile. Existing connections and cached DNS may persist until clients reconnect; alternate resolvers or VPNs can bypass this profile. No claim of testing every app or playback path is made.
