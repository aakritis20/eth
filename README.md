Hi there, My name is Aakriti Singh and here i am gonna briefly give the explanation of the given assessment/project.
so firstly what i did in this project is i i declared three variable named aa tokenName, tokenAbb, totalSupply. and they all are public so that anyone can access them.
then i declared i did mapping, so that address will point to totalSupply and tells the balance.
then i declared another function named as mint and in that function i declared two parameters named as address and value and add the value to total supply and the address of the balance.
and then lastly i declared another function named as burn function which works exactly opposite to the mint function basically burn function deletes the value from total supply and a balance of sender.
To use the solidity we are using the online website named as remix.ethereum.org, which works exactly same as vs code

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
