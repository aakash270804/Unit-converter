# Ether_value
The EtherValue Solidity contract tracks the amount of Ether received in Wei (the smallest denomination of Ether) and provides functions to convert and retrieve the value in Wei, Gwei, and Ether.

## Description
The EtherValue contract is a simple Ethereum smart contract that:

Stores the total value of Ether sent to the contract in Wei.
Allows users to retrieve the total value in Wei, Gwei, or Ether through different getter functions.
The contract uses the receive() function to accept Ether, and it automatically updates the stored valueInWei whenever Ether is sent to the contract.

## Getting Started
### Installing
You can compile and deploy this contract using an Ethereum development environment like Remix.

Open the Remix IDE.
Create a new file with a .sol extension (e.g., EtherValue.sol).
Copy and paste the following code into the file:
solidity
Copy code
      
      // SPDX-License-Identifier: MIT
      
      pragma solidity ^0.8.26;

      contract EtherValue {
      uint256 public valueInWei;

      receive() external payable {
            valueInWei = valueInWei + msg.value;
      }

      function getValueInWei() public view returns (uint256) {
            return valueInWei;
      }

      function getValueInEther() public view returns (uint256) {
          return valueInWei / 1 ether;
      }

      function getValueInGwei() public view returns (uint256) {
          return valueInWei / 1 gwei;
    }
    }
## Executing Program
Compile the contract using the Solidity compiler in Remix. Ensure the compiler version is set to 0.8.26 or a compatible version.

Deploy the contract using the "Deploy & Run Transactions" tab.

After deploying, you can interact with the following functions:

Send Ether: The contract uses the receive() function to accept Ether. Send Ether to the contract, and the valueInWei will increase by the amount sent.
getValueInWei(): Retrieves the total Ether received in Wei.
getValueInEther(): Retrieves the total Ether received in Ether.
getValueInGwei(): Retrieves the total Ether received in Gwei.
## Help
To send Ether, you can use Remix's "Deploy & Run Transactions" interface. Use the value box in the "Deploy & Run" panel to send Ether in Wei.
Ensure you're using the correct Ether denominations when sending Ether (1 Ether = 10^18 Wei).
Make sure the Solidity compiler version is 0.8.26 or a compatible one.
## Authors
Aakash Raj 
akashraj2708@gmail.com
## License
This project is licensed under the MIT License - see the LICENSE.md file for details.

