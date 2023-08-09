---
title: 'uBlock filters'
---

# uBlock filters

Here are a collection of all my [uBlock Origin](https://github.com/gorhill/uBlock) filters.

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
```
