# Create a Token

## Simple Overview of Use/Purpose

This project demonstrates how to create a simple token on the Ethereum blockchain using Solidity. It covers fundamental concepts such as storing token details, minting new tokens, and burning existing tokens.

## Description

You will develop a smart contract named MyToken using Solidity 0.8.18. This contract will include public variables for token details, a mapping for balances, a mint function to increase the supply, and a burn function to decrease it, ensuring sufficient balance before burning.

## Getting Started

### Installing

1. Visit the [Remix IDE](https://remix.ethereum.org/).
2. No installations are required as Remix is an online IDE.

### Executing Program

1. Open Remix IDE.
2. Create a new file named MyToken.sol.
3. Copy and paste the following code into the file:

solidity
```
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
    string public Token_Name = "Priyanshu";
    string public Token_Abbrv = "Prince";
    uint public Total_Supply = 0;


    // mapping variable here
    mapping(address=>uint)public balances;


    // mint function
    function mint(address Token_Address,uint value) public {
        Total_Supply += value;
        balances[Token_Address] += value;

    }

    // burn function
    function burn(address Token_Address,uint value) public {
        if(balances[Token_Address]>= value){
        Total_Supply -= value;
        balances[Token_Address] -= value;
        }

    }

}
```

    

4. Compile the contract by clicking on the "Solidity Compiler" tab and then "Compile MyToken.sol".
5. Deploy the contract by navigating to the "Deploy & Run Transactions" tab, selecting your contract, and clicking "Deploy".
6. Interact with your deployed contract using the provided interface to call functions like tokenName, tokenAbbr, totalSupply, mint, and burn.

## Help

For common problems or issues:

1. Ensure you have a stable internet connection while using Remix IDE.
2. Make sure the Solidity version in Remix is set to 0.8.18.
3. If you encounter any errors during compilation or deployment, double-check the syntax and version compatibility.

For further assistance, you can refer to the Remix documentation or run the help command within Remix IDE if available.

## Authors

Contributors:

- Priyanshu Pargaie 
  - GitHub: [@Pargaiepriyanshu](https://github.com/Pargaiepriyanshu)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
