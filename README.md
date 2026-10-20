# FC Trading Journal

A Windows desktop tracker for your EA SPORTS FC sales, purchase costs, profits and browser pack openings.

> **Use entirely at your own risk. This is an unofficial third-party tool, not approved by or affiliated with EA. Treat its use with the EA Web App as against EA’s Terms of Service. EA may restrict, suspend or ban your account. There is no guarantee of safety or continued compatibility. If you do not accept that risk, do not install or use it.** See [EA’s User Agreement](https://www.ea.com/legal/user-agreement).

## Start here

1. [Download the latest Windows release](https://github.com/BehindU/fc-trading-tracker-downloads/releases/latest).
2. Follow the [step-by-step setup guide](SETUP.md), including Tampermonkey and browser pairing.
3. Read [how your data stays local](PRIVACY.md).

**For full tracking of browser purchases, use BOTH the browser collector script and the desktop tracker.** Install the script in the browser where you actually buy cards, and pair it with the tracker on the same PC. The script captures confirmed purchase prices; the desktop app saves and displays them. The desktop app alone cannot reliably recover prices for purchases made in another browser or on console. Tracking starts after setup; missing older purchase prices cannot always be recovered.

The best setup is to keep the desktop app running and the EA Web App open with the script enabled while buying, selling or opening packs. Neither part can observe activity while its EA session is closed or disconnected. Console-only activity is not fully tracked.

## What it tracks

- Sales, purchase costs and profit after EA’s estimated 5% fee.
- Daily transfer-profit history and profit breakdowns by category and card type.
- Player statistics, repeat sales, inventory and relists.
- Confirmed browser pack openings, contents, ratings, rarity and available Holo information.
- Player picks by EA-provided type (such as 83+), offered options and confirmed chosen players, with separate performance statistics.
- Optional OP-list matching through your own Levelled Up Gaming membership.

Unknown purchase costs stay unknown rather than producing made-up profit. Cards categorized as Rewards or SBCs use zero purchase cost. EA leaderboard transfer profit is a separate measure from calculated sales profit. Sale dates reflect when the collector first observes a completed sale; late observation can put it on a later day.

## Privacy in plain language

**The tracker stores your journal on your local device. It does not upload your trading history, saved login details or pairing secrets to the developer, this repository or a tracker cloud service.** There is no tracker account or cloud database. Browser pairing connects the browser to the desktop app on the same PC.

EA still receives normal EA activity. GitHub serves downloads and updates. Optional OP-list access uses Levelled Up Gaming and Discord’s own sign-in pages. These services have their own privacy practices. The tracker does not read or save your Discord password; website session cookies remain in its local profile so OP refreshes can stay signed in. See [Privacy & local storage](PRIVACY.md) for details, backups and deletion.

## Updating

Updates are completely optional in version 0.8.2 and later. Open **Data & settings → App updates → Check for updates**. Checking does not download an installer. If a version is available, choose **Download update** only if you want it. After downloading, choose **Restart to update** when ready. There are no startup or scheduled update checks, automatic installer downloads, or installations when you close the app. You may ignore an available update and keep using your current version. Do not uninstall first; your local history and settings are retained.

Install 0.8.2 once to adopt this behavior. Older versions keep their previous update behavior until updated.

The browser collector is a separate component. Keep it up to date in Tampermonkey too. The [setup guide](SETUP.md#updating-the-app-and-script) explains both.

## Requirements and support

- A Windows 64-bit PC and access to the official EA FC Web App.
- For browser capture: a desktop browser with Tampermonkey. The guide uses Firefox.
- Internet access for EA, downloads, updates and optional OP lists.
- Paletools is optional; it is not required to install this tracker.

This is an unsigned preview. Windows may display a publisher warning. Only use downloads from this repository, check the release’s file name and checksum if unsure, and do not disable antivirus or other security protections.

If something is wrong, start with [Troubleshooting](SETUP.md#troubleshooting). You can report problems in [Issues](https://github.com/BehindU/fc-trading-tracker-downloads/issues), but never post passwords, pairing codes, cookies, tokens or full journal backups. Crop or blur personal information in screenshots.

This public repository contains downloads, update files and user documentation. The development source repository is private. A new installation starts with no personal trading history; **Explore demo** shows fictional examples only.
