# TimTheBig big_block_list_pi-hole.txt – Analysis for Adlist

**Source:** https://raw.githubusercontent.com/TimTheBig/the_big_list_for_pi-hole/main/big_block_list_pi-hole.txt  
**List size:** ~27,700 lines | **Format:** Adblock Plus + plain domains  
**Analyzed:** 2025-03-05

---

## Summary by Service

| Service | Big list has | Your list | Recommendation |
|---------|--------------|-----------|----------------|
| **Samsung TV** | 25+ domains | Strong | Add 6–8 missing domains |
| **LG TV** | 15 domains | Strong | Your list is more complete |
| **Roku** | 2 domains | Strong | No changes needed |
| **Snapchat** | 4 entries | Strong | No useful additions |
| **Instagram** | Generic/ phishing | Strong | No changes needed |
| **Hotstar/JioCinema** | None | Strong | No changes needed |
| **MX Player** | None | Manual | No changes |
| **YouTube** | Element rules only | Different purpose | No changes |

---

## 1. Samsung Smart TV – Additions

These Samsung domains appear in the big list but not in your `TV Ads.txt`:

```
ads.samsung.com
ocfconnect-shard-na03-useast2.samsungiotcloud.com
ocfconnect-shard-eu02-euwest1.samsungiotcloud.com
osb-v2.samsungqbe.com
insights.samsung.com
nmetrics.samsung.com
log-ingestion-sa.samsungacr.com
devicelog.samsungcloudsolution.net
```

**Optional (may affect non-TV Samsung devices):**

```
diagmon-policy.samsungdm.com
diagmon-serviceapi.samsungdm.com
ew1.reg.bigdata.ssp.samsung.com
analytics.bigdata.samsung.com
```

---

## 2. LG Smart TV

Your list already includes:

- `lgtvcommon.com` (e.g. `us.rdl.lgtvcommon.com`, `eic.*.lgtvcommon.com`)
- `lgtvsdp.com` (e.g. `us.rdx2.lgtvsdp.com`, `smartshare.lgtvsdp.com`)
- `lgsmartad.com`, `lgappstv.com`, etc.

The big list uses `lgtvsdp.com` only and has a typo (`yumenet^works.com^`). No LG additions recommended.

---

## 3. Roku

Your list already covers:

- `ads.roku.com`
- `logs.roku.com` and many subdomains (amarillo, austin, benjamin, etc.)

No Roku additions needed.

---

## 4. Snapchat

Big list entries:

- `app-analytics.snapchat.com` – already in your list
- `app-analytics-v2.snapchat.com` – already in your list
- `login.mijnsnapchat.com.accountsettings.app` – likely phishing
- `snapchat-alert.com` – likely phishing

No Snapchat additions recommended.

---

## 5. Instagram

Big list entries are mostly:

- Generic Meta/Facebook (e.g. `graph.facebook.com`)
- Phishing/clone domains (e.g. `instagram-dm.pages.dev`, `instagram.vcorp.ir`)

Your Sefinek-based list is more focused on real Instagram domains. No additions recommended.

---

## 6. Hotstar / JioCinema / Voot

The big list has Disney/ESPN/ABC domains (`global.go.com`, `log.espn.com`, `log.go.com`) but nothing specific to Hotstar, JioCinema, or Voot. No changes needed.

---

## 7. MX Player / Takatak

No MX Player or Takatak domains in the big list. No changes.

---

## 8. YouTube

The big list only has element-hiding rules (`youtube.com#@#.video-ads`), not domain blocks. Your `ytdomains.txt` is for all YouTube domains, so no overlap. No changes.

---

## Recommended Actions

1. Add the 8 Samsung domains above to `TV Ads.txt` under the Samsung section.
2. Optionally add the 4 “optional” Samsung domains if you want broader Samsung blocking.
3. Add TimTheBig’s list as a source in `README.md` if you adopt these domains.
