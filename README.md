# Project Title
MyToken 
## Simple Overview
This project is a basic implementation of an Ethereum smart contract that creates and manages a custom cryptocurrency token. The smart contract includes functionalities to mint new tokens, burn existing tokens, and keep track of balances for each address.

## Description
MyToken is a simple Solidity-based smart contract that demonstrates the fundamental operations of a cryptocurrency token. The contract defines public variables for the token name, abbreviation, and total supply. It maintains a mapping of addresses to balances, allowing the contract to track the number of tokens each address holds. The mint function increases the total supply and the balance of a specified address, while the burn function decreases the total supply and the balance of a specified address, with checks to ensure the balance is sufficient for burning.

## Getting Started

### Installing
1. **Download the Project**
   - Clone the repository from GitHub:
     ```sh
     https://github.com/yasar654/my_token1.git
     ```
   
- Navigate to the project directory:
     ```sh
     cd https://github.com/yasar654/my_token1
     ```
     2. **Open Remix IDE**
   - Go to [Remix IDE](https://remix.ethereum.org/).
   - In the file explorer, create a new file named `my_token1.sol`.
   - 3. **Copy and Paste the Smart Contract Code**
   - Copy the following code and paste it into `my_token1.sol`:
     ```solidity
     // SPDX-License-Identifier: MIT
     pragma solidity 0.8.18;

     /*
            REQUIREMENTS
         1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
         2. Your contract will have a mapping of addresses to balances (address => uint)
         3. You will have a mint function that takes two parameters: an address and a value. 
            The function then increases the total supply by that number and increases the balance 
            of the “sender” address by that amount
         4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
            It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
            and from the balance of the “sender”.
         5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
            to the amount that is supposed to be burned.
     */

     contract MyToken {
         // public variables here
         string public tokenName = "Yasar Alam";
         string public tokenAbbrv = "YA";
         uint256 public totalSupply = 0;

         // mapping variable here
         mapping(address => uint256) public balances;

         // mint function
         function mint(address _address, uint _val) public {
             totalSupply += _val;
             balances[_address] += _val;
         }

         // burn function
         function burn(address _address, uint _val) public {
             if (balances[_address] >= _val) {
                 totalSupply -= _val;
                 balances[_address] -= _val;
             }
         }
     }
     ```
#### How to Run the Program in Remix
1. **Compile the Smart Contract**
   - Select the `Solidity Compiler` tab.
   - Ensure the compiler version is set to `0.8.18`.
   - Click `Compile MyToken.sol`.

2. **Deploy the Contract**
   - Go to the `Deploy & Run Transactions` tab.
   - Select the appropriate environment (e.g., JavaScript VM).
   - Click `Deploy`.

3. **Interact with the Contract**
   - After deploying, the contract will appear under `Deployed Contracts`.
   - To mint tokens:
     - Input the address and the amount of tokens to mint.
     - Click the `mint` button.
   - To burn tokens:
     - Input the address and the amount of tokens to burn.
     - Click the `burn` button.
### Common Issues
- **Compilation Errors:** Ensure the Solidity version specified matches the version set in the Remix compiler.
- **Deployment Errors:** Make sure the selected environment is correct and the contract is compiled without errors.
- **Interaction Errors:** Ensure the address and value inputs are valid and that sufficient balance exists for burning tokens.

## Authors

  - GitHub: [yasar654](https://github.com/yasar654)
  
