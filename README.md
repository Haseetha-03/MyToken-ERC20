# MyToken ERC-20 Smart Contract

## Overview
MyToken is a complete ERC-20 token implementation on the Ethereum blockchain using Solidity. This project demonstrates understanding of the ERC-20 token standard and smart contract development.

## Token Details
- **Name:** MyToken
- **Symbol:** MTK
- **Decimals:** 18
- **Total Supply:** 1,000,000 tokens (1,000,000 × 10^18 smallest units)
- **Standard:** ERC-20 (Ethereum Request for Comments 20)

## What are ERC-20 Tokens?
ERC-20 is the technical standard used for creating fungible tokens on the Ethereum blockchain. It defines a set of rules that all tokens must follow to ensure compatibility with wallets, exchanges, and other applications. Every ERC-20 token represents equal value and is interchangeable.

## Implemented Features

### Core Functions
1. **transfer()** - Transfer tokens to another address
2. **approve()** - Approve a spender to use your tokens
3. **transferFrom()** - Transfer tokens on behalf of the owner
4. **balanceOf()** - Check token balance of an address
5. **allowance()** - Check approved spending amount
6. **totalSupply()** - Get total token supply

### Security Features
- Zero address validation to prevent accidental token burns
- Balance verification before transfers
- Allowance verification for delegated transfers
- Proper event emission for all transfers and approvals

## Deployment Instructions with RemixIDE

### Step 1: Access Remix IDE
1. Go to https://remix.ethereum.org/
2. Create a new file named `MyToken.sol`
3. Copy the smart contract code into the file

### Step 2: Compile Contract
1. Navigate to the Solidity Compiler (left sidebar)
2. Select compiler version 0.8.x or higher
3. Click "Compile MyToken.sol"
4. Verify no errors or warnings appear

### Step 3: Deploy Contract
1. Go to Deploy & Run Transactions (left sidebar)
2. Environment: Select "Remix VM (Shanghai)"
3. Click "Deploy"
4. The contract will be deployed to the virtual environment

### Step 4: Interact with Token
1. Expand the deployed contract in "Deployed Contracts"
2. Call functions to test functionality

## Usage Examples

### Checking Total Supply
```javascript
totalSupply() // Returns: 1000000000000000000000000
```

### Checking Your Balance
```javascript
balanceOf(0xYourAddress) // Returns your token balance
```

### Transferring Tokens
```javascript
transfer(0xRecipientAddress, 100000000000000000000) // Transfer 100 tokens
```

### Approving Spender
```javascript
approve(0xSpenderAddress, 50000000000000000000) // Approve 50 tokens
```

### Delegated Transfer
```javascript
transferFrom(0xOwnerAddress, 0xRecipientAddress, 50000000000000000000) // Transfer 50 tokens on owner's behalf
```

## Testing Scenarios & Results

### Test 1: Initial Balance
- **Objective:** Verify deployer receives total supply
- **Action:** Check balanceOf(deployer)
- **Result:** ✓ Received 1,000,000 MTK

### Test 2: Token Transfer
- **Objective:** Transfer tokens to another address
- **Action:** transfer(recipient, 100)
- **Result:** ✓ Successfully transferred, recipient balance increased

### Test 3: Approve & Transfer From
- **Objective:** Test delegated spending
- **Action:** approve() then transferFrom()
- **Result:** ✓ Allowance respected, transfer successful

### Test 4: Security Validation
- **Objective:** Verify zero address rejection
- **Action:** transfer(0x0, 100)
- **Result:** ✓ Transaction reverted with "Cannot transfer to zero address"

## What I Learned

1. **ERC-20 Standard Importance:** Understanding why certain functions and events are required ensures compatibility across DeFi ecosystem

2. **Event Logging:** Events are crucial for off-chain monitoring and allow applications to track token movements efficiently

3. **Access Control:** Zero address checks prevent accidental token loss and demonstrate defensive programming practices

4. **State Management:** Mappings efficiently store balances and allowances while maintaining gas efficiency

5. **Security Considerations:** Input validation at the contract level is essential since blockchain transactions are immutable

## Repository Structure
```
MyToken-ERC20/
├── contracts/
│   └── MyToken.sol           # Main ERC-20 contract
├── screenshots/
│   ├── compilation.png       # Successful compilation proof
│   ├── deployment.png        # Deployment transaction
│   ├── token-info.png        # Token metadata display
│   ├── transfer-test.png     # Transfer transaction
│   └── events.png            # Event logs
├── README.md                 # This file
└── LEARNING.md              # Personal reflections (optional)
```

## Quality Checklist
- ✓ Contract compiles with Solidity 0.8.x without errors
- ✓ All ERC-20 required functions implemented
- ✓ Transfer and Approval events properly emitted
- ✓ Input validation for zero addresses
- ✓ Code includes meaningful comments
- ✓ Tested transfer, approve, and transferFrom functions
- ✓ Repository is public and accessible

## How to Use This Repository

1. **View the contract:** Navigate to `contracts/MyToken.sol`
2. **Copy to Remix IDE:** Copy the contract code from GitHub
3. **Follow deployment instructions:** Use Remix IDE deployment steps above
4. **Test using examples:** Try the usage examples provided

## Additional Resources
- [ERC-20 Token Standard](https://eips.ethereum.org/EIPS/eip-20)
- [Remix IDE Documentation](https://remix-ide.readthedocs.io/)
- [Solidity Documentation](https://docs.soliditylang.org/)
- [OpenZeppelin ERC-20](https://docs.openzeppelin.com/contracts/4.x/erc20)

## License
MIT License - Feel free to use this code for educational purposes
