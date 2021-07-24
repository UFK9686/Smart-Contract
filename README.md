# Smart-Contract
Homework20

We construct a smart contact to accept Ether into the contract and divide the Ether evenly among the associate level employees. This will allow the Human Resources department to pay employees quickly and efficiently. In this contract, we are allowing a HR department to deposit ETH into employee wallets using the following code:

pragma solidity ^0.5.0;



contract AssociateProfitSplitter {
  address payable employee_one;
  address payable employee_two;
  address payable employee_three;
  
  
    constructor(address payable _one, address payable _two, address payable _three) public  {
    employee_one = _one;
    employee_two = _two;
    employee_three = _three;
  }

function getBalance() public view returns(uint) {
      return address(this).balance;
  }
  
  function deposit() public payable {
    uint amount = msg.value/3;
    
    
    employee_one.transfer(amount);
    employee_two.transfer(amount);
    employee_three.transfer(amount);
    
    
    msg.sender.transfer(msg.value - amount * 3);
    
    }
    
    function() external public payable {
        
    deposit();
  
    }
  
  
}


## Please see screenshots for successful deposits and updated address balances.

![Screenshot (26)](https://user-images.githubusercontent.com/79285543/126877099-91a9d1bc-54b3-4fa7-b4a9-798ea7f8b331.png)
![Screenshot (23)](https://user-images.githubusercontent.com/79285543/126877100-2dba51bc-87df-4490-8b03-24f26fb874de.png)
![Screenshot (24)](https://user-images.githubusercontent.com/79285543/126877101-152daa38-312e-4c64-89f7-1cd00a993038.png)
![Screenshot (25)](https://user-images.githubusercontent.com/79285543/126877102-9a321fb1-3a39-4dda-aa1e-d234139e0565.png)
