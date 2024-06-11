# Token

This Solidity contract allows us to manage a token with mint and burn functionalities. 

## Description

This Solidity contract allows us to manage a token with mint and burn functionalities. The mint function increases the total supply and assigns tokens to an address, while the burn function reduces the total supply and the tokens of an address if they have enough tokens.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., To.sol). Copy and paste the following code into the file:

```solidity
pragma solidity 0.8.18;

contract Token 
{
    // public variables here

    string public Tname= "SANKET";
    string public Tabbrv ="SK";
    uint public totalSupply =0;
    
    // mapping variable here
    mapping(address => uint) public balances;


    // mint function
    function mint (address addre, uint value) public 
    {
        totalSupply += value;
        balances[addre] += value;

    }

    // burn function
    function burn (address addre, uint value) public 
    {
        if (balances[addre] >= value) 
        {
            totalSupply -= value;
            balances [addre] -= value;
        } 

                                       
    }
}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn function. Click on the "Token" contract in the left-hand sidebar, and then fill the address and value that is token to be added in mint function. click on the "transact" button to execute the function. check the balance after adding tokens. Now to burn the tokens fill the address and value that is token to be deducted in burn function. click on the "transact" button to execute the function. check the balance after deducting tokens. At last check whether the token burnt is not greater than the available balance
