---
title: "uBlock filters"
---

# uBlock filters

Here is a collection of all my [uBlock Origin](https://github.com/gorhill/uBlock) filters.

Total blocked:

- 311510 Network Filters
- 236046 Cosmetic Filters

## Recommended lists

- [DandelionSprout's Lists](https://github.com/DandelionSprout/adfilt/blob/master/Wiki/General-info.md#-english):
  - Anti-'Functionality Removal' List
  - Anti-'Weeb boob games on Steam' List
  - Anti-'Religious Insanity' List
  - Anti-racism List
  - GDPR 451 list of websites who hates privacy rights
  - I don't want to download your browser
  - Imperial units remover
  - ClearURLs for uBlock (unofficial)
- AdGuard - Ads
- EasyList
- EasyPrivacy
- Online Malicious URL Blocklist
- Phishing URL Blocklist
- PUP Domain Blocklist
- Dan Pollock's hosts file
- Peter Lowe's Ad and tracking server list
- AdGuard - Annoyances (all lists)
- Easylist - Annoyances (all lists)
- Fanboy - Anti-facebook
- uBlock filters - Annoyances
- fi: Adblock List for Finland
- fr ca: AdGuard Francais
- [fuckfuckadblock](https://github.com/bogachenko/fuckfuckadblock) (all lists)

## Custom filters

```
# Remove tracking data in URL parameters
||ebay.*^$removeparam=amdata
||aliexpress.*^$removeparam=/.*=/

# Github
github.com###dashboard .js-feeds-tabs #feed-next
github.com###dashboard tab-container div[aria-labelledby="feed-next"]
github.com##aside .dashboard-changelog.mb-4
github.com##.js-notice
github.com##.js-profile-editable-replace img.achievement-badge-sidebar:upward(div.border-top)

# Google Search
www.google.*###rcnt > div:first-of-type:not([id]) > div:has(g-more-link,g-scrolling-carousel,g-img)
www.google.*###rso:has(> div:nth-of-type(6)) > div:has(g-more-link,g-section-with-header)
www.google.*###rso:has(> div:nth-of-type(6)) > div:has(div[role="heading"]+g-scrolling-carousel)
www.google.*###kp-wp-tab-overview > div:has(g-more-link,g-section-with-header,#media_result_group)
www.google.*###rso div.related-question-pair:upward(div[jscontroller])
www.google.*###botstuff #bres
www.google.*###rso div.g div[jscontroller][id^="eob_"]
www.google.*##div.isv-r[data-rfg]

# Hacker News
news.ycombinator.com##html:style(filter:invert(100%) hue-rotate(180deg))
news.ycombinator.com##body:style(background: #e6e6e6)
news.ycombinator.com##tbody:style(background: #e6e6e6)
news.ycombinator.com###hnmain:remove-attr(bgcolor)
news.ycombinator.com##:matches-path("/item") tbody:style(background: #dbdbdb)
news.ycombinator.com##div.toptext:style(color: black)
news.ycombinator.com###hnmain td[bgcolor="#000000"]

# YouTube
www.youtube.com##ytd-guide-renderer a.yt-simple-endpoint path[d^="M10 14.65v-5.3L15 12l-5 2.65zm7.77-4.33"]:upward(ytd-guide-entry-renderer)
www.youtube.com##ytd-mini-guide-renderer a.yt-simple-endpoint path[d^="M10 14.65v-5.3L15 12l-5 2.65zm7.77-4.33"]:upward(ytd-mini-guide-entry-renderer)
www.youtube.com##ytd-browse[page-subtype="home"] .ytd-thumbnail[href^="/shorts/"]:upward(ytd-rich-item-renderer)
www.youtube.com##ytd-browse[page-subtype="subscriptions"] .ytd-thumbnail[href^="/shorts/"]:upward(ytd-grid-video-renderer,ytd-rich-item-renderer)
www.youtube.com##ytd-search .ytd-thumbnail[href^="/shorts/"]:upward(ytd-video-renderer)
www.youtube.com##ytd-browse[page-subtype="subscriptions"] ytd-video-renderer .ytd-thumbnail[href^="/shorts/"]:upward(ytd-item-section-renderer)
www.youtube.com##ytd-browse[page-subtype="trending"] .ytd-thumbnail[href^="/shorts/"]:upward(ytd-video-renderer)
www.youtube.com##ytd-search .ytd-thumbnail[href^="/shorts/"]:upward(ytd-video-renderer)
www.youtube.com##ytd-rich-shelf-renderer[is-shorts]
www.youtube.com##ytd-rich-shelf-renderer[is-shorts].ytd-rich-section-renderer:upward(ytd-rich-section-renderer)
www.youtube.com##ytd-reel-shelf-renderer
m.youtube.com##ytm-reel-shelf-renderer
m.youtube.com##ytm-pivot-bar-renderer div.pivot-shorts:upward(ytm-pivot-bar-item-renderer)
m.youtube.com##ytm-browse ytm-item-section-renderer ytm-thumbnail-overlay-time-status-renderer[data-style="SHORTS"]:upward(ytm-video-with-context-renderer)
m.youtube.com##ytm-browse ytm-item-section-renderer ytm-thumbnail-overlay-time-status-renderer[data-style="SHORTS"]:upward(ytm-compact-video-renderer)
m.youtube.com##ytm-search ytm-thumbnail-overlay-time-status-renderer[data-style="SHORTS"]:upward(ytm-compact-video-renderer,ytm-video-with-context-renderer)
m.youtube.com##ytm-single-column-watch-next-results-renderer ytm-thumbnail-overlay-time-status-renderer span:has-text(/^(0:\d\d|1:0\d)$/):upward(ytm-video-with-context-renderer)
youtube.com##ytd-rich-grid-row, #contents.ytd-rich-grid-row:style(display:contents !important;)
```

## Creating your own filters

Ressources:

- [DandelionSprout's cheatsheet](https://github.com/DandelionSprout/adfilt/blob/master/Wiki/SyntaxMeaningsThatAreActuallyHumanReadable.md)
- [uBlock Origin documentation](https://github.com/gorhill/uBlock/wiki/Static-filter-syntax)
