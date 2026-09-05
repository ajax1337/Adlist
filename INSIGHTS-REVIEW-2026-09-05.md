# ML Insights adlist review — 2026-09-05

Reviewed all 17 logical lists (18 domain files including the Hotstar AdBlock companion) against 39,117 stored ML DNS queries and 1,961 distinct hostnames from 2026-08-29T16:12:21.737000+00:00 to 2026-09-05T16:12:21.737000+00:00. Also inspected all 252 Insights candidate roots active in that window, the verified app-signature ownership resolver, and category classifications. No query-row cap was used. This describes stored evidence, not proof that every device query was logged or that an app was opened.

## Results

| File | Before | Added entries | After | Observed hosts newly covered |
|---|---:|---:|---:|---:|
| `Amazon.txt` | 41 | 44 | 85 | 78 |
| `Apple-connectivity.txt` | 17 | 2 | 19 | 1 |
| `Apple-services-inventory.txt` | 84 | 151 | 235 | 16 |
| `Apple.txt` | 14 | 4 | 18 | 4 |
| `Duolingo.txt` | 11 | 1 | 12 | 0 |
| `Facebook.txt` | 76 | 5 | 81 | 0 |
| `Google-services-inventory.txt` | 55 | 53 | 108 | 44 |
| `Grammarly.txt` | 6 | 6 | 12 | 4 |
| `Instagram` | 88 | 15 | 103 | 8 |
| `Snapchat.txt` | 53 | 0 | 53 | 0 |
| `TV Ads.txt` | 218 | 0 | 218 | 0 |
| `WhatsApp.txt` | 47 | 0 | 47 | 0 |
| `Zoom.txt` | 1 | 0 | 1 | 0 |
| `hotstar-jiocinema.txt` | 145 | 4 | 149 | 0 |
| `mxplayer.txt` | 12 | 0 | 12 | 0 |
| `occult` | 11 | 10 | 21 | 8 |
| `ytdomains.txt` | 275 | 30 | 305 | 1 |

Added entries include explicit observed hosts already covered by an existing parent and additional dedicated parent domains. The last column counts observed hosts lacking any exact or parent match before this review; it is not the number of queries that were allowed. Other NextDNS rules may already block them. Counts can overlap across lists.

## Decisions and evidence

- Preserve every pre-existing entry. Do not treat the absence of a domain this week as evidence it is obsolete.
- Use Insights verified seed/manual/observed ownership as a starting point, not an unquestioned app attribution. In particular, its `jio.com` -> JioCinema seed and broad Meta -> Instagram assignment are too coarse. Do not add `jio.com` or `service9.sandesh.jio.com` to Hotstar from that classification alone.
- Apple service inventory gains observed Store, push, iCloud, Siri, Maps, media and dedicated roots. Apple connectivity gains only `amp-api-updates.apps.apple.com` and `bag.itunes.apple.com`; both Apple service lists remain disabled. Core Apple services and `mediaservices.cdn-apple.com` stay out of new TV Ads additions. Apple ads gains the observed iAd SDK family and `api-adservices.apple.com`, corroborated by ML native Apple blocking reasons. [Apple enterprise host documentation](https://support.apple.com/en-ie/101555) supports the separation between service access and advertising.
- Grammarly adds observed `grammarly.io` telemetry and its dedicated root, plus missing `grammarly.com` endpoints. [Grammarly network documentation](https://support.grammarly.com/hc/en-us/articles/5806184637325-Error-Can-t-connect-to-Grammarly-or-Something-went-wrong) documents those domain families.
- Amazon adds its observed retail, payments, advertising and Prime Video endpoints. Registrar RDAP identifies Amazon Technologies as registrant of [pv-cdn.net](https://rdap.markmonitor.com/rdap/domain/pv-cdn.net), [aiv-delivery.net](https://rdap.markmonitor.com/rdap/domain/aiv-delivery.net), and [a2z.com](https://rdap.markmonitor.com/rdap/domain/a2z.com). Rotating media/API/device labels are represented by stable parents; no device hashes are published. The entire `a2z.com` or cloud hosting domain is not added.
- Instagram gains its own observed API/CDN and explicitly Instagram-named encrypted chat hosts. Shared Meta hosts and dedicated Meta parent roots belong in the broader Facebook list. Existing Netseer parents cover rotating probes without publishing their identifiers.
- Google inventory gains observed Google APIs, analytics and static endpoints. Shared roots such as `googleapis.com`, `googleusercontent.com`, `gstatic.com`, `firebaseio.com`, `run.app` and `appspot.com` are not newly added as blanket roots. YouTube-specific endpoints go into the YouTube list.
- Hotstar adds four observed first-party hosts. The Jiostar-named `api-jiostar.bitdrift.io` is held for attribution confirmation. Its two list formats are identical in domain content.
- Occult adds observed AstroSage, AstroCAMP and Satyaanubhuti names plus dedicated roots. Insights classifies AstroCAMP as occult; the publishers describe [astrology services](https://www.astrocamp.com/), [AstroSage astrology](https://astrosage.com/astrology/), and [third-eye activation](https://satyaanubhuti.in/), independently supporting the topic match. No AI-only topic guess is sufficient by itself.
- Snapchat already covers both observed Snap hosts, including `sc-static.net`, which [Snap documents as its pixel host](https://developers.snap.com/marketing-api/Ads-API/snap-pixel). WhatsApp and Zoom also have no further observed gaps. No new TV-specific or MX-specific host was established.

## Deliberate exclusions and limits

- Do not add shared roots `cloudfront.net`, `amazonaws.com`, `on.aws`, `akamaihd.net`, `akamaized.net`, `fastly-edge.com`, `cloudflare.com`, `myshopify.com`, `github.io`, `githubusercontent.com`, `sentry.io`, `appsflyersdk.com` or `onelink.me` based on timing, hosting, or AI guesses.
- `wa.appsflyersdk.com` and `wa.onelink.me` remain unproven WhatsApp associations. `afs.ampaeservices.com`, `origin.amazon-ads-attestation.com`, opaque Akamai distributions and unrecognized CloudFront hosts need further attribution before inclusion.
- The existing MX list contains `mmx-ds.cdn.whatsapp.net` and a Zoom subdomain. Those legacy entries were preserved, but were not used to expand MX into all WhatsApp/Zoom domains. Other legacy shared third-party entries were not used to infer broad parent blocks.
- Netflix and other apps appear in Insights, but their list files do not exist in this repo. They were not silently folded into unrelated lists. The README inventory now reflects files that actually exist.
- No allowlist, parental-control, Gaming or schedule change is part of this review. Existing custom-list enabled profile memberships are preserved. Missing Amazon, Snapchat and Apple ads custom lists are registered disabled. The third-party UT1 lists are outside this repository and are left unchanged.

## Added entries

### Amazon.txt

```text
aax-eu-zaz.amazon.in
aax-events-cell02-cf.eu-south.ono.axp.amazon-adsystem.com
adkit-advertising.amazon
aes.eu-south.ono.axp.amazon-adsystem.com
aes.eu-west.ono.axp.amazon-adsystem.com
aiv-delivery.net
amazon.co.uk
amazon.com
amazon.eu
amazon.in
amazonvideo.com
api.amazon.co.uk
api.eu-west-1.aiv-delivery.net
api.in.3ds.websdk.amazon.dev
api.mshop.bdtelemetry.amazon
api.stores.eu-south-2.prod.paets.advertising.amazon.dev
api.stores.eu-west-1.prod.paets.advertising.amazon.dev
api.us-east-1.aiv-delivery.net
bob-dispatch-prod-eu.amazon.com
cf-timedtext.aux.pv-cdn.net
cf-trickplay.aux.pv-cdn.net
com-amazon-amazonin.triggers-v1.prod.mobile.weblab.a2z.com
completion.amazon.com
data.amazon.in
fls-eu.amazon.in
global.telemetry.insights.video.a2z.com
in.3ds.websdk.amazon.dev
logger-beta.aips.in-payments.amazon.dev
logger-prod.aips.in-payments.amazon.dev
media-amazon.com
prime.amazon.eu
prod-1.eu-west-1.mdcs.mshop.amazon.dev
pv-cdn.net
sponsored-ads.amazon.in
ssl-images-amazon.com
static.secure-fields.payments.amazon.dev
static.siege-amazon.com
ters-draper1.eu-west-1.aiv-delivery.net
ters-sgai1.eu-south-2.aiv-delivery.net
unagi-eu.amazon.com
unagi.amazon.in
us-east-1.prod.service.minerva.devices.a2z.com
www.amazon.com
zaz.api.amazonvideo.com
```

### Apple-connectivity.txt

```text
amp-api-updates.apps.apple.com
bag.itunes.apple.com
```

### Apple-services-inventory.txt

```text
0-courier2.push.apple.com
1-courier2.push.apple.com
10-courier2.push.apple.com
11-courier2.push.apple.com
12-courier2.push.apple.com
13-courier2.push.apple.com
14-courier2.push.apple.com
15-courier2.push.apple.com
16-courier2.push.apple.com
17-courier2.push.apple.com
18-courier2.push.apple.com
19-courier2.push.apple.com
2-courier.push.apple.com
2-courier2.push.apple.com
20-courier2.push.apple.com
21-courier2.push.apple.com
22-courier2.push.apple.com
23-courier2.push.apple.com
24-courier2.push.apple.com
25-courier2.push.apple.com
26-courier2.push.apple.com
27-courier2.push.apple.com
28-courier2.push.apple.com
29-courier2.push.apple.com
3-courier2.push.apple.com
30-courier2.push.apple.com
31-courier2.push.apple.com
32-courier2.push.apple.com
33-courier2.push.apple.com
34-courier2.push.apple.com
35-courier2.push.apple.com
36-courier2.push.apple.com
37-courier2.push.apple.com
38-courier2.push.apple.com
39-courier2.push.apple.com
4-courier2.push.apple.com
40-courier2.push.apple.com
41-courier2.push.apple.com
42-courier2.push.apple.com
43-courier2.push.apple.com
44-courier2.push.apple.com
45-courier2.push.apple.com
46-courier2.push.apple.com
47-courier2.push.apple.com
48-courier2.push.apple.com
49-courier2.push.apple.com
5-courier2.push.apple.com
50-courier2.push.apple.com
6-courier2.push.apple.com
7-courier2.push.apple.com
8-courier2.push.apple.com
9-courier2.push.apple.com
aaplimg.com
aidc.apple.com
amd-infra.itunes.apple.com
amp-account.itunes.apple.com
amp-api-edge.apps.apple.com
amp-api-search-edge.apps.apple.com
amp-api-updates.apps.apple.com
amp-api.apps.apple.com
amp-api.media.apple.com
amp.shazam.com
api-adservices.apple.com
api-edge.apps.apple.com
api-safari-aaps1b.smoot.apple.com
api-spotlight-aaps1a.smoot.apple.com
api-spotlight-aaps1b.smoot.apple.com
api.apps.apple.com
apple-relay.cloudflare.com
apple-relay.fastly-edge.com
apple.news
appleid.cdn-apple.com
applepay-ingestionservice-ext.apple.com
apps.itunes-nocookie.com
bag-cdn.itunes-apple.com.akadns.net
bag.itunes.apple.com
bpapi.apple.com
c.apple.news
ca.iadsdk.apple.com
cabana-config.cdn-apple.com
calendars.icloud.com
cdn-apple.com
cdn-h3.g.aaplimg.com
cf.iadsdk.apple.com
client-api.itunes.apple.com
cma.itunes.apple.com
cstat.cdn-apple.com
downloaddispatch.itunes.apple.com
entitlements.itunes.apple.com
fbs.smoot.apple.com
fpinit.itunes.apple.com
gsa-gpk.apple.com
gsp51-ssl.ls.apple.com
gsp53-ssl.ls.apple.com
gsp9-ssl.apple.com
gspe79-ssl-96.ls.apple.com
gspe85-ssl.ls.apple.com
help.apple.com
iadsdk.apple.com
inappcheck.itunes.apple.com
init.itunes.apple.com
init.push.apple.com
init.sandbox.push.apple.com
iosapps.itunes.apple.com
iphonesubmissions.apple.com
is1-ssl.mzstatic.com
itunes-nocookie.com
mask-api.icloud.com
mask.icloud.com
mediaservices.cdn-apple.com
metrics-config.icloud.com
metrics.icloud.com
ml.cdn-apple.com
musicstatus.itunes.apple.com
mzstatic.com
mzstorekit.itunes.apple.com
p120-sharedstreams.icloud.com
p56-buy.itunes.apple.com
p70-acsegateway.icloud.com
p70-caldav.icloud.com
p70-contacts.icloud.com
p70-escrowproxy.icloud.com
p70-fmf.icloud.com
p70-fmip.icloud.com
p70-fmipmobile.icloud.com
p70-mccgateway.icloud.com
p70-quota.icloud.com
partiality.itunes.apple.com
pd.itunes.apple.com
play.itunes.apple.com
profile.gc.apple.com
proxy.safebrowsing.apple
radio.itunes.apple.com
safebrowsing.apple
sandbox.itunes.apple.com
se-edge.itunes.apple.com
se2.itunes.apple.com
serverstatus.apple.com
setup.icloud.com
sf-api-token-service.itunes.apple.com
shazam-events.cdn-apple.com
shazam.com
silverbullet-external-ats.itunes.apple.com
tdms.apple.com
token.safebrowsing.apple
tr.iadsdk.apple.com
ts.itunes.apple.com
unlinkability.apple.com
weather-edge.apple.com
www.apple.com
xp.apple.com
```

### Apple.txt

```text
api-adservices.apple.com
ca.iadsdk.apple.com
iadsdk.apple.com
tr.iadsdk.apple.com
```

### Duolingo.txt

```text
duolingo.com
```

### Facebook.txt

```text
cdninstagram.com
facebook.com
facebook.net
fbcdn.net
fbsbx.com
```

### Google-services-inventory.txt

```text
analytics.google.com
appsgrowthpromo-pa.googleapis.com
clients.l.google.com
clienttracing-pa.googleapis.com
content-autofill.googleapis.com
content-push.googleapis.com
crashlyticsreports-pa.googleapis.com
fcmtoken.googleapis.com
feedback-pa.googleapis.com
firebase.googleapis.com
firebaseinstallations.googleapis.com
firebaselogging-pa.googleapis.com
firebaseremoteconfig.googleapis.com
gcs-us-00002.content-storage-download.googleapis.com
geller-pa.googleapis.com
google-analytics.com
google.co.in
googleadservices.com
googletagmanager.com
growth-pa.googleapis.com
gz.gstatic.com
jnn-pa.googleapis.com
lens-pa.googleapis.com
lens.usercontent.google.com
locationhistory-pa.googleapis.com
mail-attachment.googleusercontent.com
maps.googleapis.com
maps.gstatic.com
mobilemaps-pa-gz.googleapis.com
mobilemaps.googleapis.com
ogads-pa.googleapis.com
play.google.com
reach-pa.googleapis.com
readaloud.googleapis.com
searchlabspartnerservice-pa.googleapis.com
securetoken.googleapis.com
securitydomain-pa.googleapis.com
speechs3proto2-pa.googleapis.com
ssl.google-analytics.com
ssl.gstatic.com
storage.googleapis.com
streetviewpixels-pa.googleapis.com
t0.gstatic.com
t2.gstatic.com
t3.gstatic.com
translate-pa.googleapis.com
translate.google.com
translate.googleapis.com
www.google-analytics.com
www.google.co.in
www.googleadservices.com
www.googletagmanager.com
xgapromomanager-pa.googleapis.com
```

### Grammarly.txt

```text
f-log-mobile-ios.grammarly.io
gateway.grammarly.com
gnar.grammarly.com
grammarly.com
grammarly.io
ios.femetrics.grammarly.io
```

### Instagram

```text
gateway.instagram.com
graph-fallback.instagram.com
graph.instagram.com
i-fallback.instagram.com
instagram.fblr20-3.fna.fbcdn.net
instagram.fccj2-3.fna.fbcdn.net
instagram.fcok10-3.fna.fbcdn.net
instagram.fcok7-1.fna.fbcdn.net
instagram.fukk3-1.fna.fbcdn.net
instagram.fvga2-1.fna.fbcdn.net
payments-graph.instagram.com
scontent-blr1-1.cdninstagram.com
scontent-blr1-2.cdninstagram.com
z-p42-chat-e2ee-ig-fallback.facebook.com
z-p42-chat-e2ee-ig.facebook.com
```

### hotstar-jiocinema.txt

```text
hf-apix.hotstar.com
usersvc.hotstar.com
www.jiohotstar.com
www.voot.com
```

### occult

```text
ai.astrosage.com
akxml.astrosage.com
api2.astrosage.com
astrocamp.com
astrosage.com
japi.astrosage.com
japp.astrosage.com
satyaanubhuti.in
vartaapi.astrosage.com
www.astrocamp.com
```

### ytdomains.txt

```text
effects.usercontent.youtube.com
r1---sn-h5576nsz.googlevideo.com
r4---sn-gwpa-a3vk.googlevideo.com
r5---sn-gwpa-25ued.googlevideo.com
r5---sn-h5576nsd.googlevideo.com
rr1---sn-cnoa-jv36.googlevideo.com
rr1---sn-cnoa-jv3s.googlevideo.com
rr1---sn-h5576nsz.c.youtube.com
rr1---sn-h5576nsz.googlevideo.com
rr10---sn-cnoa-jv3s.googlevideo.com
rr2---sn-cnoa-jv36.googlevideo.com
rr2---sn-cnoa-jv3s.googlevideo.com
rr2---sn-h557sn6l.googlevideo.com
rr3---sn-ajh555-5b.googlevideo.com
rr3---sn-cnoa-jv3s.googlevideo.com
rr3---sn-h5576nee.googlevideo.com
rr3---sn-h557sn6z.googlevideo.com
rr4---sn-ajh555-54.googlevideo.com
rr4---sn-cnoa-jv3s.googlevideo.com
rr4---sn-h5576nsy.googlevideo.com
rr4---sn-h557sn6l.googlevideo.com
rr5---sn-cnoa-jv3s.googlevideo.com
rr5---sn-gwpa-h55ee.googlevideo.com
rr5---sn-h5576nsk.googlevideo.com
rr5---sn-h5576nss.googlevideo.com
rr6---sn-cnoa-jv3s.googlevideo.com
rr7---sn-cnoa-jv3s.googlevideo.com
rr8---sn-cnoa-jv3s.googlevideo.com
rr9---sn-cnoa-jv3s.googlevideo.com
yt3.googleusercontent.com
```
