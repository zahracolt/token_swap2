<img width="900" alt="30 Jul - Navigating the DeFi Ecosystem" src="https://github.com/user-attachments/assets/f4166974-50f5-400f-b084-5b95428f48ed">

# Quest 4 - Bounty 🦄

Welcome to Quest 4 of the **Navigating the DeFi Ecosystem** campaign, where I increased  the functionality of the script by including a lending protocol to Aave!

## Pre-requisites

Before you begin, do ensure you have the following installed on your system:

- Git
- Node.js

## Project Setup ⚙️

1. Clone the repository

```bash
git clone https://github.com/zahracolt/token_swap2.git
```

2. Navigate to the project directory:

```bash
cd token_swap2
```

3. Install the necessary dependencies & libraries

```bash
npm install --save
npm install ethers dotenv
npm install @aave/protocol-v2
```

Now that you're set up, you're ready to start! 📜

### Detailed Description of the DeFi Script

This script is designed to automate a series of DeFi operations by interacting with two prominent decentralized finance protocols, Uniswap and Aave, on the Ethereum Sepolia testnet. The primary goal of the script is to swap one token for another using Uniswap and then supply the swapped tokens to Aave to earn interest. This workflow showcases the power of DeFi composability, where different protocols can be seamlessly integrated to create advanced financial operations.

#### **Protocols Involved:**

1. **Uniswap V3:**
   - **Functionality**: Uniswap is a decentralized exchange (DEX) that facilitates the swapping of ERC-20 tokens directly from a user's wallet. The protocol operates on an automated market maker (AMM) model, allowing users to trade tokens without the need for a traditional order book.
   - **Role in the Script**: The script leverages Uniswap to swap USDC (USD Coin) for LINK (Chainlink). This swap operation is the first step in the workflow, converting the user's initial token into a different asset that will later be supplied to Aave.

2. **Aave:**
   - **Functionality**: Aave is a decentralized lending protocol that allows users to supply and borrow tokens. By supplying tokens to Aave, users can earn interest on their holdings, while borrowers can access liquidity by collateralizing their assets.
   - **Role in the Script**: After the token swap on Uniswap, the script automatically supplies the acquired LINK tokens to Aave. This supply operation enables the user to start earning interest on their LINK holdings, providing a passive income stream.

#### **Overall Workflow:**

1. **Token Approval:**
   - Before any swap can occur, the script first interacts with the user's USDC token contract to grant approval to the Uniswap Swap Router. This approval allows Uniswap to spend the specified amount of USDC on the user's behalf. This is a standard procedure in DeFi to ensure that contracts can only spend the amount of tokens explicitly authorized by the user.

2. **Pool Information Retrieval:**
   - The script then queries Uniswap's Pool Factory contract to retrieve details about the liquidity pool associated with the USDC/LINK trading pair. This information includes the pool's address, the tokens it contains, and the fee structure. Knowing these details is essential for preparing the swap parameters.

3. **Token Swap Execution:**
   - With the necessary pool information in hand, the script prepares and executes the token swap on Uniswap. The swap operation converts the user's USDC into LINK, using the liquidity available in the specified Uniswap pool. The output of this operation is a certain amount of LINK tokens, depending on the current market conditions and the amount of USDC provided.

4. **Supply to Aave:**
   - After the swap, the script uses the LINK tokens obtained from Uniswap and supplies them to Aave. This supply operation is executed via Aave's Lending Pool contract. By supplying LINK to Aave, the user earns interest over time, effectively putting their tokens to work in a decentralized, permissionless manner.

5. **Earning Interest:**
   - Once the LINK tokens are supplied to Aave, they begin to accrue interest according to Aave's dynamic interest rate model. The interest earned depends on the overall supply and demand within the Aave protocol, providing the user with a passive income stream in the form of additional LINK tokens.

#### **Script Flow Summary:**

- **Step 1**: The user begins by initiating the token swap.
- **Step 2**: Approve Uniswap to spend USDC.
- **Step 3**: Retrieve pool information for the USDC/LINK pair from Uniswap.
- **Step 4**: Swap USDC for LINK on Uniswap.
- **Step 5**: Supply the swapped LINK tokens to Aave.
- **Step 6**: Start earning interest on the supplied LINK in Aave, completing the transaction ✅🎉.

![bounty](https://github.com/user-attachments/assets/965d9983-95ce-40fa-ac92-76361b87f077)


This script effectively demonstrates the integration of Uniswap and Aave, two leading DeFi protocols, to automate complex financial operations. By combining these protocols, the script provides users with an easy way to swap tokens and earn interest, all within a single, cohesive workflow.


