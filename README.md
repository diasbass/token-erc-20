# DIO Token – ERC-20 Tutorial

This repository contains a **minimal, fully working** ERC-20 token written in Solidity 0.8. It is part of the Digital Innovation One (DIO) Blockchain course and demonstrates the complete workflow:

1. A **local blockchain** running on Ganache  
2. **MetaMask** signing and sending transactions  
3. **Remix IDE** compiling and deploying the contract through the injected provider  
4. Interacting with the token (`transfer`, `approve`, `transferFrom`)

* Token name: `DIO Token`  
* Symbol: `DIO`  
* Decimals: `18`  
* Initial supply: `10 DIO` minted to the deployer account

---

## Prerequisites

| Tool         | Recommended version | Notes                        |
|--------------|---------------------|------------------------------|
| **Node.js**  | ≥ 18                | Only required for Ganache CLI |
| **Ganache**  | UI 2.7 or CLI 7     | Local blockchain             |
| **MetaMask** | 11 or newer         | Browser extension            |
| **Remix IDE**| Web                 | https://remix.ethereum.org   |
| **Git**      | any                 | Clone the repository         |

---

## Quick start

### 1. Clone the project

```bash
git clone https://github.com/diasbass/token-erc-20.git
cd token-erc-20
```

### 2. Start a local blockchain

**Graphical interface**

1. Open **Ganache Desktop**  
2. Create a **Workspace** on port 7545 (`http://127.0.0.1:7545`)  
3. Copy the **private key** of the first account (it will deploy the contract)

**Command-line**

```bash
npm install -g ganache
ganache --wallet.seed dio --chain.networkId 5777 --server.port 7545
```

### 3. Connect MetaMask

1. Click the network selector › **Add network**  
2. **Network name:** Ganache  
3. **RPC URL:** `http://127.0.0.1:7545`  
4. **Chain ID:** `1337` (or `5777`, confirm in Ganache settings)  
5. Import the **private key** of the first Ganache account

### 4. Compile and deploy in Remix

1. Open <https://remix.ethereum.org> and enable **Solidity Compiler** and **Deploy & Run Transactions**  
2. Create `contracts/` and paste the `DIOToken.sol` code  
3. In **Solidity Compiler**  
   - Select compiler version **0.8.x**  
   - Click **Compile DIOToken.sol**  
4. In **Deploy & Run Transactions**  
   - *Environment:* **Injected Provider – MetaMask**  
   - Ensure the displayed account matches MetaMask  
   - Choose the `DIOToken` contract and click **Deploy**  
   - Confirm the transaction in MetaMask

After the transaction is confirmed, the contract address appears in Remix and in the Ganache transaction log.

### 5. Add the token to MetaMask

1. In MetaMask click **Import tokens**  
2. **Token contract address:** paste the contract address  
3. **Token symbol** and **Decimals** are auto-filled  
4. Click **Add custom token** › **Import tokens**

The deployer account now holds **10 DIO**.

### 6. Interact with the token

In Remix you can:

* **transfer** – send DIO to another account  
* **approve** + **transferFrom** – simulate a delegated spend (for example, a dApp)  
* Observe event logs in the Remix **Terminal**

---

## Repository structure

```
token-erc-20/
├── contracts/
│   └── DIOToken.sol
├── .gitignore
└── README.md
```

**Suggested `.gitignore`**

```
# Ethereum artifacts
artifacts/
cache/
*.json

# IDE settings
.vscode/
.DS_Store
```

---

## Next steps

* Migrate deployment to **Hardhat** with test scripts  
* Publish to **Sepolia** or **Base Sepolia** using Alchemy or Infura  
* Build a React front-end with **ethers.js**  
* Write unit tests with **Foundry** or **Hardhat**

---

## License

Distributed under the MIT License. See `LICENSE` for details.

If this repository helped you, consider leaving a star on GitHub.
