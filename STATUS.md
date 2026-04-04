# CS2 Showcase — STATUS.md
> Updated: 2026-03-22 (11:20 EDT)

## What's Live
- ✅ **https://gary-yong.com/cs2** — clean URL now works (CloudFront Function applied 2026-03-21)
- ✅ **https://gary-yong.com/cs2/index.html** — direct URL also works
- ✅ Hero section: scroll-driven canvas animation (40 WebP frames, Apple-style scroll scrub)
- ❌ ~~api.gary-yong.com/cs2/~~ — removed (2026-03-14), nginx block deleted, EC2 files purged

## What Exists Locally
- `showcase.html` + `index.html` — deployed versions (identical, both up to date)
- `portfolio.html`, `v2.html`, `v3.html`, `v4.html` — older prototype iterations
- `inventory_data.json`, `inventory_full.json` — skin data (105 items)
- `~/clawd/cs-clips/` — 335 local clips with YouTube IDs
- `clips-web/` — 8 re-encoded 720p web clips (7–33MB each), deployed to S3

## Direction (Decided 2026-03-10)
**Personal CS2 passion showcase** — Gary's own profile site featuring:
- 🏆 Achievements + rank history
- 🎨 Skin collection (filterable by type)
- 🎬 Highlights reel (native video files)
- 👥 Wall of Fame (friends/squad)
- 📊 Stats + career summary

## Current State (2026-03-24)
- 🟢 **LIVE at gary-yong.com/cs2/index.html**
- Wall of Fame: all 9 friends complete with roles, remarks, match counts
- Arsenal: 26 items displayed
- Highlights: 8 clips — **native `<video>` tags, no YouTube** (full quality, hosted on S3)
- Design: black + gold (#FFD700), Orbitron font
- Gary's verdict: "Very happy with this initial version" ✅

## Highlights Reel (8 Clips — Deployed to S3 at /cs2/clips/)
| File | Title | Type |
|------|-------|------|
| 01-1v4-clutch.mp4 | One of the best 1v4 clutches | 1v4 Clutch |
| 02-1v4-knife.mp4 | Knife start, 1v4 finish | 1v4 Clutch |
| 03-awp-ace.mp4 | AWP ace | ACE |
| 04-spray-ace.mp4 | Spray down ace | ACE |
| 05-clutch-deny-ot.mp4 | Clutch to deny OT | 1v3 Clutch |
| 06-4k-push-ot.mp4 | 4K to push to OT | 4K |
| 07-1v3-clutch.mp4 | 1v3 clutch | 1v3 Clutch |
| 08-crisp-ace.mp4 | Crisp ace | ACE |

## Wall of Fame (All 9 Complete ✅)
| Name | Role | Remark | Matches |
|------|------|--------|---------|
| LGx Replay | AWPer | "The goat" | ~500 (since 2021) |
| Bulbasaur | Anchor | "Always reliable" | ~341 |
| Spam Musubi | Case Opener | "Always cracking cases" | ~300 |
| Thovex | Entry Fragger | "Entry god, never rages" | ~200 |
| RyanMehalic | Rifler / AWPer | "Ice-veined clutch king" | ~200 |
| Nelson (EB) | Support | "Heart of the squad" | ~300 |
| Ferg | Fragger | "The team's secret weapon" | ~250 |
| erzu | All-rounder | "Quiet but locked in" | ~150 |
| Tank | Rifler | "Headshot machine" | ~100 |

## Backlog / Next Actions
- [ ] Optional: Steam API key → add live K/D, wins, kills, hours stats
- [ ] Optional: Make Steam inventory public → live skin sync
- [ ] Optional: Swap/add more highlight clips (327 remaining in ~/clawd/cs-clips/)
- ~~Optional: Add link to gary-yong.com/projects.html~~ — **DECIDED: Keep off main site** (2026-03-16). CS2 is a gaming passion project, not professional portfolio material.

## Decisions
- Gold/black theme confirmed (2026-03-10)
- No Steam API key — using public endpoints + local JSON (2026-03-10)
- All 5 sections confirmed in scope (2026-03-10)
- Initial deploy to gary-yong.com/cs2 (2026-03-13)
- YouTube embeds → native video files (local clips re-encoded 720p H.264) (2026-03-14)
- Gary approved initial version: "very happy with this" (2026-03-14)

## Notes
- CS2 betting platform (casino) is a SEPARATE project — see `PersonalWebsite/STATUS-casino.md`
- Steam inventory returns null at count=5000 (rate limit or private); inventory_full.json (105 items) used instead
- YouTube IDs still embedded in clip filenames (format: `NNN - Title [YouTubeID].mp4`) for reference
- CloudFront can't GetDistribution (IAM gap) — clean URL fix requires Gary to grant cloudfront:CreateFunction or Gary to manually add a CF Function via console
