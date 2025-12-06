# 🪙 MyToken (MTK) | ERC-20 Smart Contract Project

## 📖 Table of Contents
- [Project Overview](#-project-overview)
- [Token Specification](#-token-specification)
- [Understanding ERC-20](#-understanding-erc-20)
- [Features Implemented](#-features-implemented)
- [Deployment Guide](#-deployment-guide)
- [Usage Manual](#-usage-manual)
- [Testing Report](#-testing-report)
- [Learning Outcomes](#-learning-outcomes)

---

## 🔭 Project Overview
**MyToken (MTK)** is a decentralized digital asset built on the Ethereum blockchain. This project serves as a comprehensive "Hello World" into blockchain development, demonstrating the core logic that powers billions of dollars in the DeFi (Decentralized Finance) ecosystem. 

The smart contract handles the minting of the initial supply, secure transfer of funds between addresses, and the "approval" mechanism required for decentralized exchanges.

## 💎 Token Specification
| Parameter | Value | Description |
| :--- | :--- | :--- |
| **Token Name** | `MyToken` | The human-readable name of the asset. |
| **Symbol** | `MTK` | The ticker symbol used on exchanges. |
| **Decimals** | `18` | Precision standard (1 Token = $10^{18}$ units). |
| **Total Supply** | `1,000,000` | Fixed capped supply minted to creator. |
| **Network** | `Ethereum / Remix VM` | Compatible with any EVM chain. |

---

## 🧠 Understanding ERC-20
**What is it?**
ERC-20 (Ethereum Request for Comment 20) is the technical standard for fungible tokens. It defines a common interface—a set of rules—that a smart contract must follow.

**Why is it important?**
Before ERC-20, every token had unique code, making it impossible for wallets to support them easily. This standard ensures **Interoperability**. Because `MyToken` follows these rules, it is automatically compatible with:
* **Wallets:** MetaMask, Trust Wallet, Ledger.
* **Exchanges:** Uniswap, Binance.
* **Explorers:** Etherscan.

---

## ✨ Features Implemented
This contract allows for the following interactions on the blockchain:

1.  **Transfer Functionality:**
    * Direct peer-to-peer transfers.
    * Balances update instantly in the global state mapping.
2.  **Allowance System (Approve & TransferFrom):**
    * Allows token holders to authorize third parties (Spenders) to use their tokens.
    * This is the foundational logic for DApps and DEXs.
3.  **Event Logging:**
    * Emits `Transfer` and `Approval` events.
    * Allows off-chain applications (frontends) to track history.
4.  **Security Validations:**
    * **Zero-Address Check:** Prevents accidental burning of funds.
    * **Balance Check:** Prevents users from spending more than they own.
    * **Overflow Protection:** Utilizes Solidity 0.8.x built-in math safety.

---

## 🚀 Deployment Guide
**Tool Used:** [Remix IDE](https://remix.ethereum.org/) (Browser-based).

### Step-by-Step Instructions:
1.  **Setup:** Open Remix IDE and create a file named `MyToken.sol` in the `contracts/` folder.
2.  **Code:** Paste the Solidity source code provided in this repository.
3.  **Compile:** * Navigate to the **Solidity Compiler** tab.
    * Select Compiler version `0.8.26` (or any 0.8.x).
    * Click **Compile**.
4.  **Deploy:**
    * Navigate to **Deploy & Run Transactions**.
    * Environment: `Remix VM (Cancun)`.
    * **Important:** In the Deploy input box (Constructor), enter the supply with 18 zeros included:
    * Input: `1000000000000000000000000`
    * Click **Transact**.

---

## 💻 Usage Manual

### 1. Transferring Tokens
To send 50 MTK to a friend:
```solidity
// Note: You must add 18 zeros to the amount
transfer("0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2", 50000000000000000000)

### 2.Checking Balance

```solidity
balanceOf("0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2")
// Returns 0:
uint256: 15000000000000000000

```solidity
// User allows the "Spender" to use 100 tokens
approve("0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2", 5000000000000000000)

TransferFrom
```solidity
// Spender moves tokens from User to Recipient
transferFrom("0x5B38Da6a701c568545dCfcB03FcB875f56beddC4", "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2", 5000000000000000000)

