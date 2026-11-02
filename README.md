
# Decentralized Stablecoin (DSC) 💰

A decentralised, crypto-collateralised stablecoin system developed using **Solidity and Foundry**. The project implements a stablecoin backed by cryptocurrency collateral, with mechanisms for collateral management, price-based valuation, minting, redemption and liquidation.

The system is designed around a decentralised stablecoin that maintains its backing through over-collateralisation rather than relying on a traditional centralised reserve.

## 📌 Project Overview

The Decentralized Stablecoin (DSC) project explores the architecture and implementation of a collateral-backed stablecoin protocol on Ethereum.

Users can deposit supported crypto assets as collateral and mint DSC tokens against the value of their deposited assets. The protocol uses external price feeds to calculate collateral value and monitor the health of user positions.

The system consists of two primary smart contracts:

- **DecentralizedStableCoin.sol:** Implements the stablecoin token.
- **DSCEngine.sol:** Manages collateral deposits, withdrawals, minting, redemption and liquidation logic.

## ✨ Features

- **Collateral-Backed Stablecoin:** DSC is backed by deposited cryptocurrency collateral.
- **Multiple Collateral Assets:** Supports WETH and WBTC as collateral.
- **Decentralised Architecture:** Core protocol operations are managed through smart contracts.
- **Price Feed Integration:** Uses Chainlink Price Feeds for collateral valuation.
- **Over-Collateralisation:** Requires collateral value to exceed the value of minted stablecoins according to protocol parameters.
- **Health Factor Monitoring:** Evaluates the collateralisation status of user positions.
- **Liquidation Mechanism:** Provides a mechanism to handle under-collateralised positions.
- **Automated Testing:** Uses Foundry for smart contract testing.

## 🏗️ Smart Contract Architecture

The system is primarily composed of two smart contracts.

### 1. DecentralizedStableCoin.sol

This contract represents the DSC token and manages its token-related functionality.

Responsibilities include:

- Implementing ERC-20 token functionality.
- Managing token minting and burning.
- Restricting privileged token operations to authorised protocol components.

### 2. DSCEngine.sol

This is the core contract responsible for managing the stablecoin protocol.

Responsibilities include:

- Accepting supported collateral deposits.
- Managing collateral withdrawals.
- Calculating collateral value using Chainlink Price Feeds.
- Minting DSC against deposited collateral.
- Redeeming DSC and withdrawing collateral.
- Calculating account collateralisation and health factors.
- Managing liquidation operations.

## 🔄 Protocol Workflow

1. A user deposits supported collateral (WETH or WBTC).
2. The DSCEngine records the deposited collateral.
3. Chainlink Price Feeds provide asset-price information.
4. The engine calculates the USD-equivalent value of the collateral.
5. The user can mint DSC within the protocol's collateralisation limits.
6. The protocol monitors the user's health factor.
7. If a position becomes under-collateralised, liquidation logic can be triggered according to the protocol rules.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Solidity | Smart contract development |
| Foundry | Development and testing framework |
| Forge | Compilation and automated testing |
| Anvil | Local Ethereum development network |
| Cast | Smart contract interaction |
| Chainlink Price Feeds | External price data |
| OpenZeppelin | Standard contract interfaces and libraries |
| Ethereum | Blockchain execution environment |

## 📂 Project Structure

```text
Decentralized-Stablecoin/
│
├── src/
│   ├── DSCEngine.sol
│   └── DecentralizedStableCoin.sol
│
├── script/
│   ├── DeployDSC.s.sol
│   └── HelperConfig.s.sol
│
├── test/
│   ├── unit/
│   └── fuzz/
│
├── lib/
├── foundry.toml
├── Makefile
└── README.md
```

*Note: Adjust the file and directory names to match your actual repository.*

## ⚙️ Installation and Setup

### Prerequisites

- Git
- Foundry
- Basic knowledge of Solidity and Ethereum

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/Decentralized-Stablecoin.git
cd Decentralized-Stablecoin
```

### 2. Install Dependencies

```bash
forge install
```

### 3. Build the Contracts

```bash
forge build
```

### 4. Run Tests

```bash
forge test
```

For detailed test output:

```bash
forge test -vvv
```

## 🧪 Testing

The project uses Foundry to validate smart contract functionality.

Important testing areas include:

- Collateral deposit and withdrawal.
- Collateral value conversion using price feeds.
- DSC minting and burning.
- Prevention of excessive minting.
- Health factor calculations.
- Liquidation conditions.
- Access control and invalid input handling.
- Fuzz testing of protocol invariants.

## 🔐 Security Considerations

The project explores several important smart contract security principles:

- Access control for privileged operations.
- Validation of collateralisation requirements.
- Safe handling of token transfers.
- External oracle integration.
- Protection against under-collateralised positions.
- Testing of edge cases and failure conditions.

## 🎯 Learning Outcomes

Through this project, the following concepts were explored:

- Decentralised Finance (DeFi) architecture.
- ERC-20 token implementation.
- Collateral-backed stablecoin mechanisms.
- Smart contract composition and inheritance.
- Chainlink Price Feed integration.
- Collateral valuation and accounting.
- Health factor calculations and liquidation.
- Unit and fuzz testing using Foundry.
- Smart contract security considerations.

## 🚀 Future Scope

- Extend support for additional collateral assets.
- Improve oracle failure handling.
- Conduct advanced security audits.
- Explore gas optimisation.
- Develop a frontend for user interaction.
- Deploy and evaluate the protocol on additional EVM-compatible networks.

## 👨‍💻 Author

**Aditya Yadav**

B.Tech – Computer Science and Engineering  
Central University of Jammu

GitHub: aadi087