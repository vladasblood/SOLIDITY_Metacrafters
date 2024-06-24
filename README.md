# Getting Started with Solidity - Metacrafters

This solidity program is to test out basic syntax and functionalities of the solidity programming language. The purpose of the program was to demonstrate on how NFTs work such as mint and burn by utilizing gas fees.

## Description

The program is a basic smart contract on the Ethereum blockchain written in Solidity. It returns a contract with various functions. The first function is `mint`, which increases the total supply of the token and maps it directly to the respective address. The second function, `burn`, decreases the token supply.

## Getting Started

### Executing program

To run this program, one can utilize the provided IDE for Solidity which is Remix. To access the website, please direct to this site [Remix IDE](https://remix.ethereum.org/)

Once you are on the website, create a new file on the "+" icon in the left-handed sidebar. Save the file with a `.sol` extension (e.g., MyToken.sol). Copy and paste the following code into the file:
```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances; //since every address associated with uint, when you give it the address,
                                            //it's gonna return the token amount that the address has.
    
    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public {
        
        if(balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    
    }

}
```

To compile, click on the `Solidity Compiler` tab in the left-handed sidebar. Make sure the Compiler option is set to `0.8.18` (or another compatible version), and then click on the `Compile MyToken.sol` button.

Once the compiler does not return any errors, you can deploy the contract by clicking on the `Deploy & Run Transactions` tab in the left-hand sidebar. Select any account address that contains 100 ether. Select the `MyToken` contract from the dropdown menu, and then click on the `Deploy` button.

Once the deployment is successful, you can interact with the functions by first calling the `mint` function. First, you need to add a value on the token by click on the `MyToken` contract in the left-hand sidebar, and then click on the `mint` function. In addition, the function needs two parameters, so you need to copy and paste the Ethereum address, and add any positive values. Similarly, the `burn` function performs the same way in the previous function, but now it will reduce any value that you put in the parameter value. Now, to check your current balance, you can use the `balances`.

## Help

If it somehow happens that the value does not perform either `mint` or `burn` function, please review the Ethereum address.

## Authors

Vladimir Al Guerrero
[@Linkedin](https://www.linkedin.com/in/vladimir-al-guerrero-178b6a24b/)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
