# Detailed-Guide-to-Bitz-Miner-CLI-on-Eclipse

# 🚀 Bitz Miner Setup Guide (For New Users)

This guide is for **complete beginners** who want to set up a Bitz mining node and **create a new Solana wallet**.

---

## ✅ Prerequisites

- No wallet yet? No problem! We’ll create one.
- **Linux Ubuntu Terminal**
- A **VPS or Local Machine** with minimal CPU  
  👉 Recommended VPS: [Buy from Contabo](https://www.tkqlhce.com/5k117cy63y5LNMNPTTSSSLNRMOOPST?sid=medium)
- You will need to **fund your wallet with ETH on the Eclipse Network**

---

## ⚙️ Step 1: Install Dependencies

```bash
sudo apt-get update && sudo apt-get upgrade -y
sudo apt install screen curl nano -y
```

---

## 🦀 Step 2: Install Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

- When prompted, type `1` and press Enter
- Then run:
```bash
source $HOME/.cargo/env
```

---

## ☀️ Step 3: Install Solana CLI

```bash
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```

- Close and reopen your terminal, then check:
```bash
solana --version
```

If it says `command not found`, run:

```bash
echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
solana --version
```

---

## 🔗 Step 4: Switch to Eclipse RPC

```bash
solana config set --url https://eclipse.helius-rpc.com/
```

---

## 🆕 Step 5: Create a New Solana Wallet

```bash
solana-keygen new
```

- When prompted for a passphrase, press Enter to skip (optional)
- Save your **Seed Phrase** and **Public Key** somewhere safe  
  ⚠️ **Do not share this seed phrase with anyone!**

To get your public address later:
```bash
solana address
```

---

## 📤 Step 6: Export Your Private Key (Optional but Useful)

1. Check where your wallet key is saved:
```bash
solana config get
```

2. View and copy your private key:
```bash
cat ~/.config/solana/id.json
```

✅ Use this if you want to import your wallet into Backpack, Phantom, etc.

---

## 🧪 Step 7: Fund Your Wallet

- Import your public key into **Backpack** or any other Solana wallet.
- Fund it with **ETH on the Eclipse Network**.

---

## ⛏️ Step 8: Install and Run Bitz Miner

### Install Bitz:
```bash
cargo install bitz
```

### Start Mining:
```bash
screen -S bitz
bitz collect
```

👉 Default uses 1 CPU core. To use more:
```bash
bitz collect --cores 4   # Change 4 to your system's available cores
```

---

## 🧰 Useful Screen Commands

- Minimize screen: `Ctrl + A + D`
- Return to screen: `screen -r bitz`
- Stop node: `Ctrl + C`
- List screens: `screen -ls`
- Kill screen: `screen -XS bitz quit`

---

## 💰 Wallet Commands

Run these **outside** the screen session:

- Check mining account:
```bash
bitz account
```

- Claim your Bitz rewards:
```bash
bitz claim
```

- Full command list:
```bash
bitz -h
```

---

## 🖥️ Need a VPS?

Use Contabo for a reliable and affordable VPS:  
👉 [Buy from Contabo](https://www.tkqlhce.com/5k117cy63y5LNMNPTTSSSLNRMOOPST?sid=medium)

---
```

