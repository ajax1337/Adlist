# Adlist

Domain blocklists for Pi-hole, AdGuard Home, uBlock Origin, and similar ad/tracking blockers.

**Last Updated:** 2025-03-05

## Lists

| File | Services | Format |
|------|----------|--------|
| `Snapchat.txt` | Snapchat | Plain domains |
| `TV Ads.txt` | Samsung, LG, Roku Smart TVs | Plain domains |
| `hotstar-jiocinema.txt` | Hotstar, JioCinema, Voot | Plain domains |
| `hotstar-jiocinema` | Hotstar, JioCinema, Voot | uBlock/AdBlock |
| `Instagram` | Instagram | Plain domains |
| `ytdomains.txt` | YouTube (all domains) | Plain domains |
| `mxplayer.txt` | MX Player, Takatak | Plain domains |
| `Amazon.txt` | Amazon, Fire TV, Echo | Plain domains |
| `Apple.txt` | Apple ads, iAd, analytics | Plain domains |

## Sources

Domains are merged from the following community-maintained lists:

- **Snapchat:** [crpietschmann/pi-hole-blocklist](https://github.com/crpietschmann/pi-hole-blocklist), [kstrycharz/Pihole-Snapchat-Blocklist](https://github.com/kstrycharz/Pihole-Snapchat-Blocklist), [BrodyStone21/Block_Snapchat_Ads](https://github.com/BrodyStone21/Block_Snapchat_Ads)
- **TV Ads:** [Perflyst/PiHoleBlocklist](https://github.com/Perflyst/PiHoleBlocklist) (SmartTV.txt), [Comstarlive/blocklists](https://github.com/Comstarlive/blocklists) (rokublock.list), [mcrumm LG gist](https://gist.github.com/mcrumm/972070dfe67d44ed61c4247563cbf07c), [wassname Samsung gist](https://gist.github.com/wassname/b594c63222f9e4c83ea23c818440901b), [TimTheBig/pi-hole](https://github.com/TimTheBig/the_big_list_for_pi-hole)
- **Instagram:** [Sefinek blocklist](https://blocklist.sefinek.net)
- **YouTube:** [NextDNS services](https://github.com/nextdns/services)
- **Hotstar/JioCinema:** Web research, StevenBlack/hosts issues
- **Amazon:** [TimTheBig/pi-hole](https://github.com/TimTheBig/the_big_list_for_pi-hole), [Perflyst/AmazonFireTV](https://github.com/Perflyst/PiHoleBlocklist), [bloodhunterd/pi-hole-blocklists](https://github.com/bloodhunterd/pi-hole-blocklists)
- **Apple:** [TimTheBig/pi-hole](https://github.com/TimTheBig/the_big_list_for_pi-hole), [crazy-max/WindowsSpyBlocker](https://github.com/crazy-max/WindowsSpyBlocker)

## Limitations

- **YouTube:** `ytdomains.txt` lists all YouTube-associated domains. DNS blocking has limited effect on YouTube ads because ads are served from the same domains as content. For ad blocking on YouTube, use uBlock Origin or SmartTubeNext (Android TV).
- **Streaming:** Many streaming services serve ads from their own CDN, making DNS-level blocking less effective. Browser extensions or app-level blockers often work better.
- **Apple:** Blocking `metrics.icloud.com` may affect some iCloud features. Exclude if you experience issues.

## Usage

Add the raw file URLs to your Pi-hole adlist, AdGuard Home blocklist, or uBlock Origin custom filters. Plain-domain lists work with Pi-hole and hosts files; the `hotstar-jiocinema` file uses uBlock/AdBlock syntax (`||domain^`).
