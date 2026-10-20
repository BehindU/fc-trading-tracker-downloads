# Set up FC Trading Journal

[Back to the main page](README.md) · [Privacy & local storage](PRIVACY.md)

> **Use at your own risk.** This unofficial tracker is not approved by EA. Treat using it with the EA Web App as against [EA’s Terms of Service](https://www.ea.com/legal/user-agreement). Your EA account could be restricted, suspended or banned. Do not continue unless you accept this risk.

## Before you begin

You will install two things:

| Part | What it does |
| --- | --- |
| **FC Trading Journal** | The Windows desktop app. Saves your records and shows your statistics. |
| **Browser collector** | A small script managed by Tampermonkey. Captures purchases, sales and pack openings in your EA Web App browser tab. |

**You need the combination for full browser purchase-price tracking.** Install the script in the same browser and browser profile where you buy your cards. Pair it with the tracker on the **same PC**. Installing only the desktop app does not reliably capture purchases made in Firefox, Chrome or on console.

No coding, terminal commands or developer tools are needed. Paletools is optional. This guide uses Firefox; other browsers may have extra Tampermonkey permissions.

## 1. Install the desktop app

1. Open the [latest release](https://github.com/BehindU/fc-trading-tracker-downloads/releases/latest).
2. Under **Assets**, download the file named **FC-Trading-Journal-Setup-[version].exe**. The version is the release number. Do not choose Source code, `.blockmap` or `latest.yml`; those are not installers.
3. Open the downloaded installer and follow its instructions.
4. Launch **FC Trading Journal** from your desktop or Start menu.

The preview is unsigned, so Windows may show a publisher warning. Check that you downloaded from this repository. If you are unsure about a warning, stop rather than disabling security protections.

An empty journal is normal on first use. **Explore demo** is a preview with fictional data; exit it before checking your own records. You do not need to import a backup unless you already have one.

## 2. Install Tampermonkey

Tampermonkey is the browser extension that runs the collector. Install it in the browser you use for the EA Web App, not inside the desktop tracker.

1. In Firefox, visit the [official Tampermonkey website](https://www.tampermonkey.net/).
2. Choose its Firefox download and follow the link to the official browser add-on store.
3. Choose **Add to Firefox** and review the extension permissions.
4. Find Tampermonkey in Firefox’s extensions menu, usually the puzzle-piece button near the address bar. Pin it to the toolbar if helpful.

If you already have Tampermonkey, skip this step. Avoid private browsing for this setup; extension access and saved data can differ there.

## 3. Install the browser collector script

1. In the desktop tracker, open **Data & settings** on the left.
2. Find **Browser purchases** and click **Save browser collector**.
3. Save **fc-browser-collector.user.js** somewhere easy to find, such as Downloads. Do not rename it to `.txt`.
4. In Firefox, click Tampermonkey’s icon and open **Dashboard**.
5. Open the **Utilities** tab. Find **Import from file**, select the file you just saved, and confirm the import or installation when asked. Exact wording can vary by Tampermonkey version.
6. In Tampermonkey’s installed scripts, check that **FC Trading Journal Browser Collector** is enabled. Keep only one enabled copy of this collector.

Alternatively, the same script is available as **fc-browser-collector.user.js** under the latest release’s Assets. Download it and import it using the same steps.

Downloading the file alone does not install it. You must import it into Tampermonkey.

## 4. Pair your browser with the tracker

Pairing simply gives the script permission to send records to the app on your own PC. It is not an EA or Discord login.

1. Keep the desktop tracker open.
2. In **Data & settings → Browser purchases**, click **Create pairing code**.
3. Copy the entire code shown there. It expires after **5 minutes**. Keep it private.
4. In Firefox, open the [official EA FC Web App](https://www.ea.com/ea-sports-fc/ultimate-team/web-app/), sign in to EA, and enter Ultimate Team.
5. Reload the Web App after installing the script.
6. Look for the **Journal** button at the bottom-right of the EA page. Click it, paste the pairing code and confirm. You can also open Tampermonkey’s menu on the EA page and choose **Pair with desktop**.
7. If Tampermonkey asks whether the script may connect to **127.0.0.1**, allow that connection. This address means **your own PC**, not an internet server. No router setup or port forwarding is needed.
8. Wait a short while. The Journal button should show **Connected**, and the desktop app’s **Browser purchases** section should show a paired browser and a **Last saved** time after the first successful sync.

The script tries to send new records about every **10 seconds**. Some EA reads run less frequently, so not every statistic changes immediately. You normally pair once per browser profile; you do not need a fresh code every day. If the code expires, create a new one and repeat the pairing steps.

**The tracker’s separate Connect EA status is for its built-in EA window.** It can say the collector is stopped even when your paired Firefox browser is syncing successfully. For browser setup, check **Browser purchases → Last saved** and the browser’s **Journal** button.

## 5. Check that everything is working

1. Keep the app open, the PC awake, and the signed-in EA Web App tab open with the collector enabled.
2. Open your transfer list. Allow the collector time to read any visible completed sales.
3. On your next normal purchase in this browser, let EA confirm it. Keep the script running when you list and sell that card too.
4. In the tracker, select the correct **Club** and check **Sales** or **Players** for the recorded card and purchase cost.
5. On your next normal pack opening in this browser, check **Packs** for the opening and its contents.

There is no need to spend coins or open a paid pack just to test setup. Existing information may appear first; new purchase-price and pack records start from what the collector observes after installation.

## Optional: the app’s built-in EA window

If you want to use the EA Web App inside the desktop app, click **Connect EA**, sign in on EA’s page and enter Ultimate Team. Keep the app running; that EA window may be minimized.

This does not replace the browser script for purchases made in Firefox or another browser. You do not need to sign into both EA windows for browser pairing. If a second EA session disconnects your browser, use **Stop** for the built-in collector and continue with the paired browser.

EA leaderboard transfer profit is separate from calculated sales profit. If the built-in collector asks you to choose your leaderboard name, select **your own exact EA name** and click **Use this name**. Never select another player just to fill the chart.

The desktop window can remember its EA session locally. Optional **Remember EA login** settings provide Windows-encrypted local autofill. EA can still require sign-in or verification. This does not change your Firefox login.

## Optional: connect OP lists

You can track sales without OP-list access. Automatic OP matching needs access to the relevant [Levelled Up Gaming OP lists](https://www.levelledupgaming.com/op-lists/).

1. Open **Data & settings → OP list matching → Connect OP lists**.
2. Sign in through the website’s official Discord sign-in flow using your own eligible membership.
3. Return to the tracker and click **Refresh OP lists**. Check that the update time and list-entry count change successfully.

Logging into the website in Firefox does not automatically sign the tracker’s separate website window in. Discord handles its own login; the tracker does not read or save your Discord password. Website session cookies stay in the app’s local profile to keep refreshes signed in. They are not uploaded to the developer or GitHub.

Available linked lists refresh hourly while the app runs. If sign-in expires or the website is unavailable, the previous saved list is retained. A card must match the name, rating and version; being absent from the current lists can leave it **Uncategorized**. In **Sales**, use the category selector to choose **OP**, **Rewards**, **Investments** or **SBCs** manually when needed. Manual choices are preserved.

## Everyday use and limits

- Keep the collector enabled **before buying** and while using the EA Web App. Keep the desktop tracker open for regular saves.
- If the app is closed, the browser script queues observed records locally and sends them when the app reopens. Do not clear browser or extension data before syncing.
- The script cannot observe a closed browser, a disconnected EA session, or purchases made only on console. Some visible EA records may be recovered later, but complete history is not guaranteed.
- Let completed sales be recorded before clearing them. Already-cleared, unobserved sales may be unrecoverable.
- **Unknown purchase cost** means the app lacks reliable evidence. Enter a known cost manually in **Players → Sale details & card confirmation** if needed. Do not guess. Rewards and SBC categories use zero cost.
- Profit after tax is the sale price minus the estimated 5% fee and purchase cost. EA leaderboard transfer profit is different and may not equal the sum of tracked sales profits.
- Dates use your device’s local time. A sale’s date is when it is first observed as sold, not the date it was bought. If collection was offline overnight, an older sale may be recorded on the day it is next seen.
- Pack history starts with confirmed openings observed by the collector. Past or console openings, previews and failed openings are not reconstructed. Unknown card details remain unknown.
- The optional **Holo only** market switch filters the current page of EA search results. It does not search the entire market for Holos. An empty filtered page does not mean none exist; other result pages may contain them.
- New users have no category cutoff by default. **Category fresh start** is optional and personal to the selected club. Leave it alone unless you want to exclude older cards from category review.

## Updating the app and script

**Desktop app:** it checks at startup. For a manual check, open **Data & settings → App updates → Check for updates**. Let the update finish downloading, then choose **Restart to update**. Do not uninstall first. Local history and settings are retained; keeping a backup is still sensible.

**Browser script:** Tampermonkey can check for collector updates. Make sure the installed script is current too; updating the app alone does not replace the script in your browser. If necessary, use **Save browser collector** in the updated app and import it again through Tampermonkey. Accept the update to the existing script, avoid duplicate enabled copies, and reload the EA Web App. Pairing normally stays intact.

## Back up or move your history

1. Select the club you want to back up.
2. Open **Data & settings** and click **Download club backup**.
3. Keep the JSON file somewhere private. Repeat for each club you use.
4. To restore it, click **Import backup** at the top of the tracker and choose the file. Select the matching club afterward.

Backups include trading records and pack history, not saved EA passwords, login sessions or browser pairing. On a new PC, install the app and script and pair them again. There is no automatic cross-device cloud sync. If you want a backup to remain only on your device, choose a folder that is not synced to OneDrive, Dropbox or another cloud service.

## Troubleshooting

| What you see | What to try |
| --- | --- |
| No Journal button | Check Tampermonkey and the collector are enabled in the exact browser/profile you use for EA. Sign into the official Web App and reload it. In Chrome-based browsers, follow Tampermonkey’s [Allow User Scripts guidance](https://www.tampermonkey.net/faq.php#Q209) if prompted. |
| Script file opens as text | You downloaded it but have not installed it. Use Tampermonkey **Dashboard → Utilities → Import from file**. |
| Incorrect or expired pairing code | Keep the desktop app open, create a new code, copy all of it, and paste it within 5 minutes. |
| Offline / queued locally | Open the tracker on the same PC. Check the script has permission to connect to 127.0.0.1. Close duplicate tracker instances. Keep the browser data intact and retry. Do not expose the connection through your router or disable security protections. |
| No records in the app | Exit demo mode, select the correct club, check **Browser purchases → Last saved**, and keep the signed-in Web App open. Allow a few minutes for periodic EA reads. |
| Built-in collector says stopped | For Firefox capture, check the Journal button and Browser purchases status instead. The top status refers to the app’s separate EA window. |
| Bought price is missing | The script must be active where the purchase happens. Another browser/profile, console, a closed tab or an expired session can miss the price. Historical missing costs cannot always be recovered. |
| Names show as --- --- | Update both app and script, reload EA, and allow names to finish loading. Version 0.8.1 and later can repair placeholders from saved matching records or later observations. |
| Cards stay Uncategorized | Check OP website sign-in, membership, list update time, rating and card version. Refresh the lists or choose the correct category manually. |
| EA keeps disconnecting | Avoid competing EA sessions on console, Firefox and the app’s EA window. Stop the built-in collector if you are using the browser route. |
| Statistics differ from EA | Check missing purchase costs, the selected dates, category cutoff and whether you are comparing sales profit with EA leaderboard transfer profit. |

Still stuck? Open an [issue](https://github.com/BehindU/fc-trading-tracker-downloads/issues) with your app version, browser, collector version and the exact error text. Do not attach passwords, pairing codes, tokens, cookies or a full journal backup.
