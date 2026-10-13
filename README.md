# VerseOps

An unofficial desktop companion for Star Citizen, for Windows.

**Get it:** open the [latest release](https://github.com/TheViper115/VerseOps/releases/latest) and download `VerseOps_<version>_x64-setup.exe`. That one file is all you need.

**Unofficial fan-made tool. Not affiliated with or endorsed by Cloud Imperium Games or Roberts Space Industries. Free, non-commercial.**

## What VerseOps is

- A small Windows app that runs beside Star Citizen.
- It counts down the Executive Hangar and the Ruin Station vault door, and alerts you before they open.
- It shows community prices, plans where to sell a hold, and works out trade and refining profit.
- It lets you try ship loadouts, with each gun's damage, shot speed, range and penetration distance.
- It can show the timers in a small overlay on top of the game.
- It shows what RSI's own status page says about the game's servers, and can tell you when they are back after a maintenance.

Timers are community-measured ("about"), prices are community reports, and the server status is only what RSI's status page says. Nothing in it is exact, and the app itself is not official.

## Install

VerseOps is for Windows 10 or 11 (64-bit).

1. Download `VerseOps_<version>_x64-setup.exe` from the [latest release](https://github.com/TheViper115/VerseOps/releases/latest) and run it.
2. The installer is not signed with a certificate, so Windows SmartScreen may warn about the file. If a blue window says "Windows protected your PC", choose **More info** and then **Run anyway**.
3. Windows asks whether the installer may make changes to this PC, and names an unknown publisher. Say yes.
4. Follow the installer. Keep the folder it suggests, `C:\Program Files\VerseOps`.

Why the installer needs administrator rights: VerseOps can be restarted as administrator so that its shortcuts work while the game is in front. A program that may run as administrator must lie where a program with normal rights cannot replace it, and `C:\Program Files` is such a place. VerseOps itself runs with normal rights unless you ask for more.

VerseOps draws its window with Microsoft's WebView2, which Windows 11 has. On a PC without it, the installer fetches it from Microsoft.

Closing or minimising the window sends VerseOps to the tray, so that timers and alerts go on. **Quit** is in the tray icon's menu.

## Updates

From version 1.2.0 on, VerseOps looks for a newer version by itself: about half a minute after it starts and then every 6 hours, also from the tray. When there is one it says "VerseOps <version> is available".

- Nothing is downloaded or installed until you press **Update now**. Windows then asks for permission, as it did for the first install, and VerseOps comes back by itself as the new version. Your timers, settings and loadouts are kept.
- **Later** puts the notice away for that version. **Settings > Updates** keeps offering it, and has **Check now**.
- What is asked: two small files of the latest release on this page, `latest.json` and `latest.json.sig`, over https from `github.com`. They hold the newest version number, a few words about it, and a signature. Nothing about you or your game is sent. As with any web request, GitHub sees your internet address.
- The download is the same setup file you see on the release page. VerseOps checks the list and the setup file against a key that is built into the app, and refuses anything that was not made with VerseOps' own key.
- To switch the check off: **Settings > Updates > Check for updates**. VerseOps then asks GitHub nothing by itself.

Version 1.1.0 and older do not update themselves: install 1.2.0 or newer by hand once, over the old one. Your data is kept (it lies in another folder). If the installer offers to uninstall the old version first and you let it, leave the uninstaller's box "Delete the application data" unticked.

## What this page holds

Only the released files and this text. Beside each setup file lie three small files for the app's updater (`.sig` files and `latest.json`); you do not need them.

## Your data and privacy, in short

VerseOps has no account and no telemetry. It asks four services, and nothing else:

| Service | For what |
| --- | --- |
| UEX (`api.uexcorp.uk`, with `api.uexcorp.space` as a second address) | Prices, terminals, the live game version |
| Star Citizen Wiki API (`api.star-citizen.wiki`) | Ships and parts |
| RSI status page (`status.robertsspaceindustries.com`) | What RSI says about the game's services |
| GitHub (`github.com`, this page) | Whether a newer VerseOps exists, and the setup file when you press to update |

The last two can be switched off in the app's Settings. VerseOps does not read the game's memory or its network traffic, puts nothing into the game and sends it no input.

## Credits and thanks

VerseOps shows other people's work. Thank you to:

- **Prices:** [UEX](https://uexcorp.space) (uexcorp.space). Community reports: latest and ~15-day average.
- **Ship and item data:** [Star Citizen Wiki API (api.star-citizen.wiki)](https://api.star-citizen.wiki). The data is for non-commercial use only.
- **Ship figures:** worked out with the rules of [ScDataDumper](https://github.com/octfx/ScDataDumper), the open data generator behind the Star Citizen Wiki API. Some of them are estimates, and the Ships page says which.
- **Hangar community timer reference:** [exec.xyxyll.com](https://exec.xyxyll.com) by Xyxyll (MIT licence).
- **Server status:** [RSI status page (status.robertsspaceindustries.com)](https://status.robertsspaceindustries.com). The status words and the notices VerseOps shows from it are RSI's own.

Fonts, each under the SIL Open Font License 1.1: Rajdhani, Inter, JetBrains Mono (from the Fontsource packages).

Libraries, with the licences their packages state:

| Library | Licence |
| --- | --- |
| Tauri, with its store, notification, global shortcut, single instance and opener plugins | Apache-2.0 OR MIT |
| React, React DOM, React Router | MIT |
| Motion | MIT |
| zustand | MIT |
| uFuzzy (`@leeoniya/ufuzzy`) | MIT |
| clsx | MIT |
| Lucide (`lucide-react`) | ISC |
| Tailwind CSS | MIT |
| Vite, Vitest, jsdom, Testing Library | MIT |
| TypeScript | Apache-2.0 |
| rodio, reqwest, url, serde, serde_json, base64, windows (Rust crates) | MIT OR Apache-2.0 |
| minisign-verify (Rust crate; it checks the signature of an update) | MIT |

VerseOps contains no RSI or CIG logos and no game art. Its look is its own.
