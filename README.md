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

VerseOps has no account and no telemetry. It asks seven services, at the addresses it comes with:

| Service | For what |
| --- | --- |
| UEX (`api.uexcorp.uk`, with `api.uexcorp.space` as a second address) | Prices, terminals, the live game version |
| Star Citizen Wiki API (`api.star-citizen.wiki`) | Ships and parts; the game facts of an item when you open its sheet in the Item Finder; the Item Finder's game records, ore places and Wikelo exchanges; the mission list and a contract's details on the Missions page |
| RSI status page (`status.robertsspaceindustries.com`) | What RSI says about the game's services |
| Star Citizen Wiki pages (`starcitizen.tools`) | The community note of an item whose sheet you open in the Item Finder |
| Star Citizen Wiki pictures (`media.starcitizen.tools` and `cdn.star-citizen.wiki`) | The picture of an item whose sheet you open in the Item Finder |
| Cornerstone pictures (`cstone.space`) | The same, when the item's game record names a picture on Cornerstone's site instead. Of Cornerstone VerseOps takes the pictures alone. |
| GitHub (`github.com`, this page, and its file servers whose names end in `githubusercontent.com`) | Whether a newer VerseOps exists, and the setup file when you press to update |

- They are plain requests for public data, over https. No account, no key, and nothing about you or your game is sent. As with any web request, the service sees your internet address. The requests say that they come from VerseOps, with its version number and the address of this page.
- These are the addresses as shipped. The first four are in VerseOps' game numbers file (`game-config.json`, under `uex`, `shipData`, `serverStatus` and `itemFinder`), which you can edit; if you change one there, VerseOps asks that address instead. The picture hosts and GitHub are built into the app.
- When UEX or the Star Citizen Wiki API answers a request by pointing it to another address, VerseOps follows it, as a browser would: at most five times, over https only, and never to this PC or a local network. RSI's status page, the wiki's pages and the picture hosts are never followed to another host, and GitHub only to its own file servers.
- That is what VerseOps itself asks. If Windows is set to use a proxy, these requests go through it. WebView2, the part of Windows that draws the window, is Microsoft's, and VerseOps does not control it.
- These can be switched off in the app's Settings: the server status (**Server status > Check RSI's server status**: then RSI's status page is not asked at all), the check for updates (**Updates > Check for updates**: then VerseOps asks GitHub nothing by itself; **Check now** still asks once), item pictures (**Item Finder > Show item pictures**: then no picture is asked for) and community notes (**Item Finder > Show community notes from the Star Citizen Wiki**: then the wiki's pages are not asked).
- VerseOps does not read the game's memory or its network traffic, puts nothing into the game and sends it no input.

## Credits and thanks

VerseOps shows other people's work. Thank you to:

- **Prices:** [UEX](https://uexcorp.space) (uexcorp.space). Community reports: latest and ~15-day average.
- **Ship, item and mission data:** [Star Citizen Wiki API (api.star-citizen.wiki)](https://api.star-citizen.wiki). The data is for non-commercial use only.
- **Ship figures:** worked out with the rules of [ScDataDumper](https://github.com/octfx/ScDataDumper), the open data generator behind the Star Citizen Wiki API. Some of them are estimates, and the Ships page says which.
- **Hangar community timer reference:** [exec.xyxyll.com](https://exec.xyxyll.com) by Xyxyll (MIT licence).
- **Server status:** [RSI status page (status.robertsspaceindustries.com)](https://status.robertsspaceindustries.com). The status words and the notices VerseOps shows from it are RSI's own.
- **Item pictures:** Star Citizen Wiki ([starcitizen.tools](https://starcitizen.tools) and [star-citizen.wiki](https://star-citizen.wiki)) and Cornerstone ([cstone.space](https://cstone.space)), credited under each picture. The items shown are game content of Cloud Imperium Games.
- **Community notes:** Star Citizen Wiki ([starcitizen.tools](https://starcitizen.tools)), text under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/), quoted as its editors wrote it with the page and its edit date under each quote.
- **Where players find it:** community reports gathered and checked by VerseOps; each source is linked under its report.

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

VerseOps contains no RSI or CIG logos, and its look is its own. The one place that shows game art is the Item Finder's item sheet: the picture of an item, from the Star Citizen Wiki or Cornerstone, with its source under it.
