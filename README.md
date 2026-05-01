# Roblox Manager

Multi-account Roblox manager and auto-rejoiner — store, organise, and launch dozens of accounts in parallel, then automatically grind a target item across your alts until everyone has it.

[![Download](https://img.shields.io/badge/download-latest-success?style=for-the-badge&logo=windows)](https://github.com/YungTedo/RobloxManager-Downloads/releases/latest/download/Roblox%20Manager.exe)
[![Latest release](https://img.shields.io/github/v/release/YungTedo/RobloxManager-Downloads?style=for-the-badge)](https://github.com/YungTedo/RobloxManager-Downloads/releases/latest)

---

## What it does

**Account Manager (free)**
- Store any number of Roblox accounts locally, encrypted with Windows DPAPI (cookies decrypt only on the same Windows user / PC)
- Add accounts three ways: paste cookie, paste many cookies at once, or sign in with username/password through a real browser window (you solve any CAPTCHA, the cookie is captured automatically)
- One-click import from Roblox Account Manager (RAM) — supports both DPAPI and master-password-protected files
- Group accounts by tag, search across username + alias + notes, sort by last used / name / status
- Edit alias / tag / color / notes inline
- **Bulk-edit:** select multiple accounts, change a field once, applied to all
- Launch any selected account into a specific game (Join Game) or follow a friend (Join User) with a stagger queue
- Built-in **saved-games library** — paste a place ID once, fetches the game name automatically, switch between games via dropdown
- Multi-instance is built in — no need to run RAM alongside

**Auto-Rejoiner (paid, license-gated)**
- Run N accounts simultaneously on a configured game (default 2 slots, configurable up to many)
- Roblox-presence-API health checks: detects when an account leaves the target game, server-hops, or hard-crashes — and relaunches just that account, not all of them
- Discord integration: bot watches a channel for item-capture / desired-stand messages and reacts (mark account done, swap in next, set RAM-style alias)
- Account rotation: when an account obtains the target item, it's marked done and the next account in your list takes its slot. After 3 failed launches, an account is flagged broken and skipped automatically.
- Auto split-screen window positioning
- Auto-import from RAM on first launch

---

## Download

[**Click here to download `Roblox Manager.exe`**](https://github.com/YungTedo/RobloxManager-Downloads/releases/latest/download/Roblox%20Manager.exe)

The link always points at the most recent release.

System requirements:
- Windows 10 or 11 (x64)
- ~200 MB free disk for the exe + Chromium (Chromium is downloaded automatically the first time you use browser-based account adding)

No installer — it's a single executable. Put it anywhere and double-click.

---

## First-launch setup

1. **Run `Roblox Manager.exe`.** No prompt — you go straight into the Account Manager.
2. **Add your accounts.** Click `+ Account/s` (top-left of the account list):
   - **Add account…** — single-account form. Cookie OR username + password, plus optional alias / tag / notes.
   - **Add via user:pass…** — paste many `username:password` pairs, one per line. A browser opens for each (you solve any CAPTCHA + click Log In; cookie captured automatically).
   - **Add by cookie(s)…** — paste many `.ROBLOSECURITY` cookies, one per line. No browser needed.
   - **Import from RAM…** — pulls every account from an existing RAM `AccountData.json`, including encrypted and password-protected files.
3. **Group your accounts.** Click an account → fill the **Tag** field on the right (e.g. `bridger`, `farming`, `bank`) → **Save changes**. The Groups column on the left auto-builds tabs for each unique tag.
4. **Add a game so you can launch into it.** Click `+ Game` → paste a place ID (the digits in the Roblox URL). The game name is fetched automatically.
5. **Launch:** select one or more accounts → pick a game in the **Game** dropdown → click **Join Game**.

---

## Using the auto-rejoiner

The auto-rejoiner is the **Roblox Alive** tab — the paid feature.

1. Click the **Roblox Alive** tab. A license dialog opens.
2. Paste the key you received after purchase (`RA-XXXX-XXXX-XXXX-XXXX`).
3. The rejoiner unlocks for the session.

Once unlocked:
- Pick a game from the dropdown at the top
- Use `→` to move accounts into the **Selected** list
- Set the slot count (how many accounts run at the same time)
- Pick detection mode (**Presence** recommended)
- Click **Start**

The rejoiner takes care of everything else — launches, watches each account's status, swaps in fresh accounts as ones complete, stops when the whole pool is done.

For Cerberus (or any tool that posts to Discord on item capture), open **Rejoiner Settings → Discord bot token / channel**, paste your bot's token + channel ID, and the rejoiner will read the channel directly to know when accounts complete.

---

## Updates

The app checks for updates on launch and prompts you to download the new version automatically. Just click **Yes** when offered.

---

## Troubleshooting

| Issue | Fix |
|---|---|
| **Windows Defender flags the exe** | Right-click the file → Properties → Unblock. Or temporarily disable real-time protection during first run. The app is unsigned (small dev) which Defender treats as suspicious by default. |
| **"License key not recognized"** | Check you copied the full key (`RA-XXXX-XXXX-XXXX-XXXX`) without trailing spaces. Contact the seller if it persists. |
| **An account keeps showing offline** | Roblox privacy setting. Open the account's **Account Settings → Privacy**, set "Who can see my online status" to **Friends** or **Everyone**. The rejoiner will trust hidden-place accounts as in-game by default, but explicit visibility is more reliable. |
| **Roblox refuses to open multiple instances** | Make sure RAM (or any other multi-instance tool) is not running at the same time. Roblox Manager handles multi-instance itself. |
| **Account marked "broken" after 3 launches** | The cookie is likely expired or Roblox is rate-limiting that user. Re-add the account via cookie paste or browser login. |
| **Slow first launch** | First-time exe extraction takes a few seconds; subsequent launches are faster. The auto-update check skips itself if it ran in the last 6 hours. |

---

## Support

Open an issue on this repo, or contact the seller via Discord.

---

*Roblox Manager is not affiliated with Roblox Corporation. Multi-instance + automation may violate Roblox's Terms of Service — use at your own risk.*
