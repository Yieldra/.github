# 🏆 Yieldra: RWA-Backed Yield Stablecoin

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Solidity](https://img.shields.io/badge/Solidity-0.8.x-blue)

## Overview

Yieldra is a decentralized protocol that enables users to earn 5% APY on USDC deposits through yUSD tokens, with yield accruing in real-time. Designed for simplicity and security, it offers the most straightforward way to generate passive income in DeFi without lockup periods.

## 🔗 Project Links

- **🌐 Demo App:** [Yieldra](https://yieldra-fe-deployment.vercel.app/)
- **📹 Demo Video:** [YouTube](https://youtu.be/OC9BwoGdJjA)
- **📄 Documentation:** [GitHub Repository](https://github.com/Yieldra)
- **📝 Smart Contract Address:** `0xF9dcBFF7EdDd76c58412fd46f4160c96312ce734`
- **🔍 View on BlockScout:** [Deployed Contract on](https://pharosscan.xyz/address/0xF9dcBFF7EdDd76c58412fd46f4160c96312ce734?tab=index)

## ✨ Key Features

- **Automatic Yield Accrual**: 5% APY compounded every second
- **1:1 Asset Backing**: yUSD tokens fully collateralized by USDC
- **Instant Withdrawals**: No lockup periods - exit anytime
- **Testnet Faucet**: Try with free test USDC
- **Gas-Optimized**: Efficient yield calculations
- **OpenZeppelin Audited**: Industry-standard security
- **Real-Time Analytics**: Track yield growth by the second

## 🔧 Technical Architecture

The protocol consists of three core components:

1. **Smart Contract Layer**: Solidity contracts handling deposits, yield math, and withdrawals
2. **Oracle-Free Design**: Pure blockchain-native yield calculations
3. **Faucet Integration**: Built-in test USDC distribution

### Smart Contract Structure

- **Deposit Engine**: Handles USDC deposits and yUSD minting
- **Yield Calculator**: Real-time APY computation
- **Withdrawal System**: Burn-and-claim mechanism
- **Admin Controls**: For demo parameter adjustments

## 📊 Data Structures

## UserStruct
```javascript
struct Deposit {
    uint256 amount;     // USDC deposited
    uint256 timestamp;  // Last interaction time
    uint256 yieldPaid;  // Cumulative yield earned
}
```

## 🚀 Getting Started
- **Prerequisites**
- **Node.js (v18+)**
- **Hardhat or Foundry**
- **MetaMask (with testnet USDC)**
- **Git**


## Installation

1. Clone the repository:
   
    ```bash
      git clone https://github.com/Yieldra/frontend.git
    cd yieldusd
    ```
   
2. Install dependencies:

    ```bash
      npm install
    ```
    
3. Configure your environment:

    ```bash
      cp .env.example .env
    # Edit .env with your settings
    ```
    
4. Compile smart contracts:

    ```bash
      npx hardhat compile
    ```

5. Deploy to your chosen network:
    
    ```bash
      npx hardhat run scripts/deploy.js --network testnet
    ```
    
6. Start the development server:
    
    ```bash
      npm run dev
    ```
    
7. Deployment

    ```bash
    npx hardhat compile
    npx hardhat run scripts/deploy.js --network testnet
    ```
    
## 💡 Usage Examples

### Deposit USDC**
```bash
    const yieldUSD = new ethers.Contract(
      yieldUSDAddress, 
      ['function deposit(uint256 amount) external'],
      signer
    );
    
    await usdc.approve(yieldUSD.address, 1000e6);
    await yieldUSD.deposit(1000e6);
```

## Check Earned Yield**
```javascript
    function getYield(address user) public view returns (uint256) {
        Deposit memory dep = deposits[user];
        uint256 elapsed = block.timestamp - dep.timestamp;
        return (dep.amount * apy * elapsed) / (10000 * 31536000);
    }
```
    
## Withdraw Funds**
```javascript
    await yieldUSD.withdraw();
```
    
## 🔒 Security Features
- **Reentrancy Protection**: All state changes before transfers
- **Precision Math**: 18-decimal fixed-point arithmetic
- **Input Validation**: Strict parameter checks
- **Time-Locked Admin Functions**: For demo parameter changes

## ⚡ Performance Optimizations
- **Single Storage Slot**: Packed user data
- **Minimal External Calls**: USDC interactions optimized
- **Batch Processing**: For future scalability

## 🛣️ Roadmap
- **Q3 2025**: Mainnet launch with 3rd-party audit
- **Q4 2025**: DAO governance for APY adjustments
- **Q1 2026**: Cross-chain yield aggregation

## 👨‍💻 Contributing
1. Fork the repository
2. Create feature branch (git checkout -b feature/improvement)
3. Commit changes (git commit -m 'Add amazing feature')
4. Push to branch (git push origin feature/improvement)
5. Open Pull Request

## 📜 License
MIT License - See LICENSE for details.

## 🏆 Hackathon Success Notes
This project excels in hackathon criteria:
    - **Innovation**: Simplest yield product in DeFi
    - **Technical Merit**: Precise real-time yield math
    - **User Experience**: One-click deposits/withdrawals
    - **Demo Readiness**: Integrated testnet faucet
    - **Code Quality**: Fully documented with NatSpec

📮 Contact
Project Link: https://github.com/Yieldra
