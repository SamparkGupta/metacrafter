# Project Title MyToken

Simple Overview MyToken is a smart contract implemented on the Ethereum blockchain. It provides a basic framework for creating, minting, and burning a custom cryptocurrency token.

# Description
 The MyToken project is a Solidity-based smart contract designed to manage a custom cryptocurrency token. The contract includes public variables to store essential information about the token, such as its name ("SAMPARK"), abbreviation ("SAM"), and total supply. A mapping is used to track the balance of each address. The contract includes two primary functions: mint and burn. The mint function increases the total supply of tokens and adds the specified amount to the balance of a given address. Conversely, the burn function reduces the total supply and the balance of the specified address, ensuring the address has sufficient tokens to burn. This smart contract demonstrates fundamental concepts of token management on the Ethereum blockchain.

# Getting Started
# Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a.sol extension (e.g., project.sol). Copy and paste the following code into the file:

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
string public TokenName="SAMPARK";
string public TokenAbbrv="SAM";
uint public TotalSupply=0;
    // mapping variable here
mapping(address => uint) public balance;
    // mint function
function mint(address _address,uint _value)public{
   TotalSupply+=_value;
   balance[_address]+=_value;
}
    // burn function
    function burn(address _address,uint _value)public{
      if(balance[_address]>=_value)
      TotalSupply-=_value;
      balance[_address]-=_value;
}
}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.7" (or another compatible version), and then click on the "MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "project" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling both the functions.

# Author
SAMPARK GUPTA STUDENT CHANDIGARH UNIVERSITY
