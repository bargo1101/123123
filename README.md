# Solana Token Launchpad

A **browser-based Solana SPL token launchpad** that lets you create and launch a new token directly from your wallet using **Phantom**, with optional on-chain metadata via **Metaplex Token Metadata**.

⚠️ **Devnet by default. Mainnet uses real SOL.**  
Do not use mainnet unless you understand Solana rent, transaction fees, and irreversible blockchain actions.

---

## ✨ Features

- 🔗 Phantom wallet connection (robust detection)
- 🌐 Switch between **Devnet** and **Mainnet**
- 🪙 Create a new SPL token mint
- 📦 Mint full supply to your wallet
- 🏷️ Create Metaplex metadata account (name, symbol, image, description)
- 🔒 Automatically **revokes mint authority** (fixed supply)
- 🚀 One-click launch from the browser (no backend required)

---

## 🧱 Tech Stack

- **Solana Web3.js**
- **@solana/spl-token**
- **Metaplex mpl-token-metadata**
- Vanilla HTML, CSS, and JavaScript (no framework)
- Runs entirely client-side

---

## 🖥️ Demo / Usage

1. Open `index.html` in a browser  
   > Recommended: Phantom’s in-app browser or Chrome with Phantom installed

2. Connect your **Phantom wallet**

3. Choose network:
   - **Devnet** (safe for testing)
   - **Mainnet** (⚠️ real SOL will be spent)

4. Fill in token details:
   - Token Name
   - Symbol (≤ 8 characters)
   - Total Supply (integer)
   - Image URL (optional)
   - Description (optional)

5. Click **Launch Token**

Once complete, your mint address opens in Solana Explorer.

---

## 🧪 Devnet vs Mainnet

| Network | Cost | Purpose |
|------|------|--------|
| Devnet | Free (airdrop SOL) | Testing & experimentation |
| Mainnet | Real SOL | Production tokens |

You will be warned before switching to mainnet.

---

## 🏷️ Metadata Notes (Important)

- This launchpad **supports embedded data URIs** for quick testing.
- **Production tokens should NOT use embedded metadata.**

### Recommended for Production:
Host your metadata JSON on:
- **IPFS**
- **Arweave**

Then update the `uri` in the code to point to that hosted file.

Why?
- On-chain metadata URIs are size-limited
- Indexers & marketplaces expect HTTP/IPFS URLs
- Embedded URIs may break compatibility

---

## 🔐 Token Behavior

By default, the launchpad:

- ✔️ Mints the full supply to your wallet
- ✔️ Creates an associated token account
- ✔️ Sets you as update authority
- ❌ **Revokes
