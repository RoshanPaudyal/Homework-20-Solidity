# Homework-20-Solidity

JointSavings Smart Contract
This is a Solidity smart contract that implements a joint savings account, where two authorized Ethereum addresses can deposit and withdraw funds.

Getting Started
To get started with this project, you will need an Ethereum wallet and an IDE like Remix to deploy and test the smart contract.

Prerequisites
An Ethereum wallet like MetaMask
The Remix IDE for Solidity development
Installing
Clone the repository to your local machine.
Open the JointSavings.sol file in the Remix IDE.
Compile the smart contract using the Solidity compiler.
Deploy the contract to the Ethereum network using the Remix IDE.
How to Use
The smart contract has the following functions that you can use:

setAccounts
This function sets the two authorized Ethereum addresses that can withdraw funds from the contract. You need to call this function before you can deposit or withdraw any funds.

solidity
Copy code
function setAccounts(address payable account1, address payable account2) public;
deposit
This function allows you to deposit funds into the contract. You need to send Ether to this function to deposit funds.

solidity
Copy code
function deposit() public payable;
withdraw
This function allows you to withdraw funds from the contract. You need to specify the amount to withdraw and the recipient address.

solidity
Copy code
function withdraw(uint amount, address payable recipient) public;
contractBalance
This function returns the current balance of the contract.

solidity
Copy code
function contractBalance() public view returns (uint);
lastToWithdraw
This function returns the address of the last person to withdraw funds from the contract.

solidity
Copy code
function lastToWithdraw() public view returns (address);
lastWithdrawAmount
This function returns the amount of the last withdrawal from the contract.

solidity
Copy code
function lastWithdrawAmount() public view returns (uint);
Examples
Here are some examples of how to use the JointSavings smart contract.

Example 1: Set the authorized accounts
solidity
Copy code
// Set the authorized accounts
contract.setAccounts(0x0c0669Cd5e60a6F4b8ce437E4a4A007093D368Cb, 0x7A1f3dFAa0a4a19844B606CD6e91d693083B12c0);
Example 2: Deposit funds
solidity
Copy code
// Deposit 1 ether into the contract
contract.deposit.value(1 ether)();

// Verify the contract balance
assert(contract.contractBalance() == 1 ether);

// Deposit 10 ether into the contract
contract.deposit.value(10 ether)();

// Verify the contract balance
assert(contract.contractBalance() == 11 ether);

// Deposit 5 ether into the contract
contract.deposit.value(5 ether)();

// Verify the contract balance
assert(contract.contractBalance() == 16 ether);
Example 3: Withdraw funds
solidity
Copy code
// Withdraw 5 ether to accountOne
contract.withdraw(5 ether, 0x0c0669Cd5e60a6F4b8ce437E4a4A007093D368Cb);

// Verify the contract balance
assert(contract.contractBalance() == 11 ether);

// Verify the last withdrawal amount and recipient
assert(contract.lastWithdrawAmount() == 5 ether);
assert(contract.lastToWithdraw() == 0x0c0669Cd5e60a6F4b8ce437E4a4A007093D368Cb);

// Withdraw 10 ether to account
