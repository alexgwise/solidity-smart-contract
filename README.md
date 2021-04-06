# solidity-smart-contract

### This homework assignment requires at least one of the contract options be completed. I have submitted levels 1 and 2: ###
- Associate Profit Splitter
- Tiered Profit Splitter

For each assignment, I used Ganache for my test account addresses.

### Associate Profit Splitter ###

The first assignment was relatively straightforward. The uint amount was sent equal to the msg.value and divided equally into three parts. 
Then, each employee received a transfer/deposit of the divided value. 

Below is a sample of the code:

function deposit() public payable {
        // @TODO: Split `msg.value` into three
        uint amount = msg.value/3; 

        // @TODO: Transfer the amount to each employee
        employee_one.transfer(amount);
        employee_two.transfer(amount);
        employee_three.transfer(amount); 
  
I first compiled my code, and deployed the contract. Below is a screen print of the successful block creation in Ganache from the contract creation. 

![](https://github.com/alexgwise/solidity-smart-contract/blob/main/Images/associate%20profit%20splitter/profit%20splitter%20contract%20creation.PNG)        

Next, I submitted a transfer of **4** Ether to be divided among the three accounts. The below screen shot shows the balance for each account prior to submitting.

![](https://github.com/alexgwise/solidity-smart-contract/blob/main/Images/associate%20profit%20splitter/balances%20before%20deposit.PNG)

The next two screen shots show the successful block creation of submitting the deposit/transfer, and the resulting balance increase for each account.

![](https://github.com/alexgwise/solidity-smart-contract/blob/main/Images/associate%20profit%20splitter/funds%20transfer.PNG)

![](https://github.com/alexgwise/solidity-smart-contract/blob/main/Images/associate%20profit%20splitter/account%20balances%20after%20deposit.PNG)

The contract worked!


### Tiered Profit Splitter ###

For the 2nd contract, the number of points to be divided is done on a percentage basis. We first take the msg.value and divide it by 100. , which will allow us to multiply the points by a given number to represent the percentage. We use += to keep a running total of the amount distributed.

Below is a sample of the code:

uint points = msg.value / 100; // Calculates rudimentary percentage by dividing msg.value into 100 units
        uint total;
        uint amount;

        // @TODO: Calculate and transfer the distribution percentage
        // Step 1: Set amount to equal `points` * the number of percentage points for this employee
        // Step 2: Add the `amount` to `total` to keep a running total
        // Step 3: Transfer the `amount` to the employee
        amount = points * 60;
        total += amount;
        employee_one.transfer(amount);

        // @TODO: Repeat the previous steps for `employee_two` and `employee_three`
        // Your code here!
        amount = points * 25;
        total += amount;
        employee_two.transfer(amount);
        
        amount = points * 15;
        total += amount;
        employee_three.transfer(amount);
        
I first compiled my code, and deployed the contract. Below is a screen print of the successful block creation in Ganache from the contract creation. 

![](https://github.com/alexgwise/solidity-smart-contract/blob/main/Images/tiered%20profit%20splitter/deploying%20the%20contract.PNG)

Next, I submitted a transfer of **10** Ether to be divided among the three employees according to their percentage. The below screen shot shows the balance for each account prior to submitting.

![](https://github.com/alexgwise/solidity-smart-contract/blob/main/Images/tiered%20profit%20splitter/starting%20balance.PNG)

The next two screen shots show the successful block creation of submitting the deposit/transfer, and the resulting balance increase for each account.

![](https://github.com/alexgwise/solidity-smart-contract/blob/main/Images/tiered%20profit%20splitter/transferring%20the%20funds.PNG)

![](https://github.com/alexgwise/solidity-smart-contract/blob/main/Images/tiered%20profit%20splitter/ending%20balance.PNG)

***Success!***
