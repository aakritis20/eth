# PROJECT
\
Create a token.

Here, the code creates a token with the following additional functions in addition to the address to uint name mapping for balance, which includes the token's name, abbreviation, and total supply:

The min function adds the value to the total supply and the address of the balance after taking two parameters, an address and a value.

The burn function eliminates a value from the sender's balance as well as the entire supply in the opposite way to the mint function. Additionally, in order to use Solidity, we must install Remix Ide or use it online by going to remix.ethereum.org. Similar to VS code, it functions.

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

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
# Executing Program

contract MyToken {

// public variables here
string public tokenName = "oracle";
string public tokenAbb = "or";
uint public totalSupply = 10;

// mapping variable here

mapping(address => uint) public balance;

// mint function

function mint (address _add, uint _value) public {
    totalSupply += _value;
    balance[_add] += _value;
}

// burn function

function burn (address _add, uint _value) public {
    if (balance[_add]>= _value) {
    totalSupply -= _value;
    balance[_add] -= _value;
}
}
}

# Author
Aakriti Singh
singhaakriti203@gmail.com

# License
This project is licensed under the MIT License - see the LICENSE.md file for details

