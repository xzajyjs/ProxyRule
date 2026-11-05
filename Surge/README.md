# ProxyRule Surge Rules

Generated locally from `mac_server.surgeconfig` external rule-sets and `Shadowrocket_to_Surge_Mac.conf` inline rules.

## Merge Notes

Same-name policy merges across both configs:
- `🛑 广告拦截`: same policy name in both configs.
- `🎮 游戏平台`: same policy name in both configs.
- `🍎 苹果服务`: same policy name in both configs.

User-approved semantic merges:
- `📹 油管视频` -> `🎬 YouTube`
- `🎥 奈飞视频` -> `🎬 Netflix`
- `Ⓜ️ 微软云盘` -> `🔖 OneDrive`

Shadow compatibility policies merged into canonical rule-sets:
- `shadow_bahamut.list` (`📺 巴哈姆特`) -> `bahamut.list` (`🎬 巴哈姆特`)
- `shadow_bilibili.list` (`📺 哔哩哔哩`) -> `bilibili.list` (`🎬 B站港澳台`)
- `shadow_china_media.list` (`🌏 国内媒体`) -> `china_media.list` (`🌏 国内流媒体`)
- `shadow_direct.list` (`DIRECT`) -> `direct.list` (`🎯 全球直连`)
- `shadow_global_media.list` (`🌍 国外媒体`) -> `global_media.list` (`🌏 国外流媒体`)
- `shadow_microsoft.list` (`Ⓜ️ 微软服务`) -> `microsoft.list` (`🧩 微软服务`)
- `shadow_proxy.list` (`Proxy`) -> `global.list` (`🌏 国外网站`)
- `shadow_reject.list` (`REJECT`) -> `adblock.list` (`🛑 广告拦截`)

`👿 AI` is a rename of Shadowrocket policy `😈 AI`.
`🧲 OpenAI` was fully contained in `👿 AI`, so the standalone OpenAI rule-set was removed.

## De-duplication

Exact duplicate rules across files were removed using this priority: block/purify and explicit direct rules first, then specific service rule-sets, then media/category aggregates, then global catch-all rule-sets.
- Removed cross-file duplicates: 2323
- Promoted Steam download/CDN rules into `steam_us.list` and removed them from broader rule-sets.

Top files cleaned:
- `global_media.list`: 1051
- `global.list`: 635
- `china_media.list`: 245
- `china.list`: 138
- `microsoft.list`: 62
- `apple.list`: 60
- `hbomax.list`: 35
- `google.list`: 19
- `game.list`: 17
- `bilibili.list`: 15
- `chat.list`: 15
- `iqiyi.list`: 8

## Rule Files

| Policy | File | Rules |
|---|---:|---:|
| 🛑 广告拦截 | `adblock.list` | 1119 |
| 🍃 应用净化 | `app_purify.list` | 1020 |
| 🎯 全球直连 | `direct.list` | 906 |
| 🇺🇸 Steam下载服务 | `steam_us.list` | 33 |
| 💳 Wise | `wise.list` | 1 |
| 🇺🇸 Apple美区服务 | `apple_us.list` | 4 |
| 👿 AI | `ai.list` | 313 |
| Cloudflare | `cloudflare.list` | 76 |
| 📢 谷歌FCM | `google_fcm.list` | 35 |
| 📲 电报消息 | `telegram.list` | 11 |
| 🎶 网易音乐 | `netease_music.list` | 33 |
| 🗺 Speedtest | `speedtest.list` | 5 |
| 🎙 Discord | `discord.list` | 29 |
| 🎬 YouTube | `youtube.list` | 185 |
| 🎬 Netflix | `netflix.list` | 1156 |
| 🎬 DisneyPlus | `disney_plus.list` | 174 |
| 🎬 AppleTV+ | `apple_tv.list` | 8 |
| 🎬 巴哈姆特 | `bahamut.list` | 12 |
| 🎬 B站港澳台 | `bilibili.list` | 126 |
| 🎬 B站东南亚 | `bilibili_intl.list` | 1 |
| 🎬 爱奇艺 | `iqiyi.list` | 49 |
| 🎬 PrimeVideo | `prime_video.list` | 26 |
| 🎬 viuTV | `viutv.list` | 11 |
| 🎬 KKTV | `kktv.list` | 13 |
| 🎬 韩国媒体 | `korea_media.list` | 34 |
| 🎬 日本媒体 | `japan_media.list` | 160 |
| 🎬 HBOGO | `hbogo.list` | 63 |
| 🎬 HBOMAX | `hbomax.list` | 357 |
| 🎬 EMBY | `emby.list` | 91 |
| 🎬 Dazn | `dazn.list` | 16 |
| 🎵 Spotify | `spotify.list` | 30 |
| 🎵 AppleMusic | `apple_music.list` | 10 |
| 🎵 TIDAL | `tidal.list` | 4 |
| 🎵 Qobuz | `qobuz.list` | 33 |
| 🎶 TikTok | `tiktok.list` | 28 |
| 🎮 游戏平台 | `game.list` | 689 |
| 🔖 OneDrive | `onedrive.list` | 18 |
| 🔎 Bing | `bing.list` | 9 |
| 🔎 Yahoo | `yahoo.list` | 170 |
| ☁️ iCloud | `icloud.list` | 56 |
| 🍎 苹果服务 | `apple.list` | 1535 |
| 🔎 Google | `google.list` | 682 |
| 🧩 微软服务 | `microsoft.list` | 608 |
| 📪 邮件服务 | `mail.list` | 22 |
| 📲 聊天软件 | `chat.list` | 116 |
| 🌏 国内流媒体 | `china_media.list` | 181 |
| 🌏 国外流媒体 | `global_media.list` | 1286 |
| 🌏 国内网站 | `china.list` | 29560 |
| 🌏 国外网站 | `global.list` | 6399 |

## Cloudflare

`cloudflare.list` contains Cloudflare service and hosted-platform domain rules from [MetaCubeX/meta-rules-dat](https://github.com/MetaCubeX/meta-rules-dat/blob/meta/geo/geosite/classical/cloudflare.yaml). Five existing Cloudflare rules were moved from `global.list` into this file.

Add this rule after `ai.list` and before `global.list` to preserve the existing AI-specific Cloudflare routing:

```ini
RULE-SET,https://raw.githubusercontent.com/xzajyjs/ProxyRule/main/Surge/rules/cloudflare.list,Proxy
```

Replace `Proxy` with the desired policy name if needed. This list covers Cloudflare domains, including `pages.dev`, `workers.dev`, and `r2.dev`; it does not include shared CDN IP ranges.
