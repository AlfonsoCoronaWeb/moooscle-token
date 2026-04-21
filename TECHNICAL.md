# 🧩 Moooscle (MSCL) — Technical Documentation

This document provides a complete technical overview of the Moooscle (MSCL) token
smart contract deployed on Polygon PoS.  
It covers the contract architecture, standards implemented, security guarantees,
and on-chain behavior.

---

## 📌 Contract Overview

**Network:** Polygon PoS  
**Standard:** ERC‑20  
**Contract Address:**  
`0xB7D7AFcfFbb32B619e32597f2DeBaBF4F783F13A`

The Moooscle token is a fully immutable ERC‑20 implementation with no minting,
no burning, no owner privileges, and no upgradeability.  
The contract is verified on PolygonScan and reconstructed in this repository
exactly as published on-chain.

---

## 📁 Contract Architecture (7 files)

The contract is composed of **7 Solidity files**, matching the verified source:

1. **ERC20Asset.sol**  
   Main token contract. Connects all modules and defines the MSCL token.

2. **Ownable.sol**  
   Ownership module required by the original architecture.  
   *Note: The owner has no privileged functions.*

3. **ERC20.sol**  
   Standard ERC‑20 implementation (balance tracking, transfers, allowances).

4. **Initializable.sol**  
   Initialization helper used in the original modular structure.

5. **ERC20Base.sol**  
   Core logic of the token.  
   Contains transfer logic, allowance handling, and internal mechanics.

6. **IERC165.sol**  
   ERC‑165 interface for contract introspection.

7. **IERC7572.sol**  
   Interface for metadata standardization.

---

## 🔧 Standards Implemented

### ✔️ ERC‑20  
The contract follows the ERC‑20 standard:

- `totalSupply()`
- `balanceOf(address)`
- `transfer(address,uint256)`
- `allowance(address,address)`
- `approve(address,uint256)`
- `transferFrom(address,address,uint256)`

### ✔️ ERC‑165  
Used for interface detection.

### ✔️ ERC‑7572  
Metadata standardization interface.

---

## 🔒 Security Properties

The Moooscle contract is intentionally designed to be **simple, immutable, and safe**.

### ✔️ No mint  
No function exists to increase supply.

### ✔️ No burn  
No function exists to destroy tokens.

### ✔️ No blacklist  
No address can be blocked or restricted.

### ✔️ No owner privileges  
The `Ownable` module exists but **does not control any sensitive function**.

### ✔️ No upgradeability  
The contract is fully immutable after deployment.

### ✔️ No external dependencies  
No external calls, no oracles, no proxies.

---

## 🧮 Token Supply

- **Total Supply:** 1,000,000,000,000 MSCL  
- **Decimals:** 18  
- **Supply is fixed and cannot change.**

---

## 🔍 On‑Chain Behavior

- Transfers follow standard ERC‑20 logic.  
- Allowances follow standard ERC‑20 logic.  
- No fees, taxes, or custom mechanics.  
- No hidden logic or privileged pathways.  
- Gas usage is consistent with standard ERC‑20 implementations.

---

## 🧪 Verification

The contract is fully verified on PolygonScan:  
https://polygonscan.com/address/0xB7D7AFcfFbb32B619e32597f2DeBaBF4F783F13A

This repository mirrors the verified source code exactly.

---

## 📘 License

The contract uses the **Apache‑2.0** license, as declared in the original source.

---

🐮 **Moooscle — simple, transparent, immutable.**
