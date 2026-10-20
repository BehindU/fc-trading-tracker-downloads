# Privacy & local storage

[Main page](README.md) · [Setup guide](SETUP.md)

## Your tracker records stay on your device

FC Trading Journal saves your journal locally. **It does not upload trading history, purchase prices, profits, pack contents, saved credentials or pairing secrets to the developer, GitHub or a tracker cloud service.** There is no tracker account, hosted journal database, or built-in cloud sync. The tracker has no built-in usage analytics or remote crash-reporting service.

The browser collector sends records to the desktop app through **127.0.0.1:17843**. This is a connection within the same computer. It is not a remote server or a connection to the developer. Pairing is required; the desktop listener binds only to the local computer.

## What is saved locally

| Data | Where it is kept |
| --- | --- |
| Sales, purchase costs, inventory, category choices and pack history | Your Windows user profile, normally `%APPDATA%\FC Trading Journal`. |
| Browser observations and records waiting to sync | The EA Web App’s local browser storage and Tampermonkey’s local script storage in the browser profile you use. |
| Browser pairing | A local token in Tampermonkey; a hashed token in the desktop app’s local profile. |
| EA sign-in session in the app | The app’s local EA browser profile; saved session-cookie copies use Windows-backed encryption when available. |
| Optional EA login autofill | Windows-encrypted local storage. Autofill is optional and targets EA’s official sign-in pages. |
| OP-list cache and website session | The app’s local files and a separate local website browser profile. |
| Exported JSON backups | The folder you choose when downloading a backup. |

Trading history is stored as ordinary local data; it is not all encrypted just because saved EA credentials are encrypted. Protect access to your Windows account and device.

## Discord and OP website login

Discord handles authentication on Discord’s own sign-in page. The tracker does not read or save your Discord password. Levelled Up Gaming handles access to its OP lists. The app keeps website session cookies locally so it can remain signed in for hourly refreshes. Those cookies and the cached lists are not uploaded to the developer or GitHub.

Do not interpret this as saying that Discord or the OP website receives no data: logging into those services communicates with them directly, under their own privacy policies.

## Internet connections that still happen

“Local journal storage” does not mean the software never uses the internet:

- **EA:** the official Web App signs in and communicates with EA normally. EA already handles your account and gameplay data. Optional saved EA credentials are used only to fill EA’s official login page; they are not sent to the developer or included in trading sync or backups.
- **GitHub and its download infrastructure:** installer downloads and manually requested app update checks/downloads use GitHub. Collectors before 0.8.2 can also use GitHub for Tampermonkey update checks; the 0.8.2 collector disables automatic update checks. Journal records are not attached to those requests. GitHub can receive ordinary connection information, such as your IP address, under its own policies.
- **Levelled Up Gaming and Discord:** optional OP-list access and sign-in communicate with those services. The tracker does not upload your journal with OP-list requests.
- **Your browser and extensions:** Tampermonkey and the browser are separate products with their own settings and privacy policies.

The local-storage statement describes this tracker’s behavior. It cannot control what EA, Discord, GitHub, your browser, your operating system, other extensions or your own backup software store.

## Keep it local when backing up or asking for help

Exported journal backups contain your records and club identifiers. They do not contain the app’s saved EA autofill password, EA sessions or pairing tokens. Keep them private.

If you save a backup into a cloud-synced folder, enable an external browser/profile backup, upload a screenshot or attach a file to an issue, that external service may store what you chose to share. For device-only storage, use a local folder outside cloud sync and avoid external profile/extension backups containing tracker data. Never post passwords, cookies, tokens, pairing codes or full journal backups in public issues.

## Stop collection or remove local data

- **Browser collection:** disable the collector in Tampermonkey. In the app, **Data & settings → Browser purchases → Disconnect browsers** revokes pairings; it does not erase the journal.
- **Built-in EA collection:** click **Stop** in the app’s Automatic collection section.
- **Saved EA login:** **Data & settings → Remember EA login → Forget saved EA login** removes the app’s saved EA credentials and remembered EA session without deleting your journal.
- **Remove the journal and app-held website sessions:** back up anything you want to keep, close the app completely, then remove its `%APPDATA%\FC Trading Journal` folder. This deletes local history and settings; it cannot be undone without a backup. Uninstalling the app alone intentionally keeps this folder.
- **Remove browser-held copies too:** remove the collector and its stored data through Tampermonkey, and clear EA Web App site data in the browser profile you used. This can sign you out of EA and remove other tools’ local data. Do not do it before syncing or exporting anything you want to retain.
- Delete any exported backup files separately if you no longer want those copies.

There is no developer-hosted journal copy to retrieve if you lose your local data and backups.

Documentation checked against version 0.8.2 on 20 October 2026.
