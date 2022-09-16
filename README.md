# flow-quest
flow cadence bootcamp

### Chapter 1 - Day 1

Smart Contracts are logic-based computer programs developed by engineers/developers. Smart Contracts live at an address . These functions take in a parameter(s) and stores said parameter into data. It then sends the updated data to the blockchain. It does so through logic within functions written within scripts and transactions, which ultimately allows users to interact and exchange data (nft, payment, etc).

Transactions are paid functions with logic that changes data on the blockchain.

Scripts are code that also have logic within them but it is only a 'view' or 


### Chapter 1 - Day 2 

Safety and Security
Clarity
Approachability
Developer Experience
Resource Oriented Programming

### Chapter 2 - Day 1

![flow](https://user-images.githubusercontent.com/25441286/190719274-f4db094e-57fa-42da-bbf2-2fb856e85651.png)

### Chapter 2 - Day 2 

changeGreeting is the name of a function but we need to import and call the name of the contract 

__AuthAccount__ allows us to access any data in the account (e.g. like paying for the transaction with the account)

Prepare provides access to the information/data of the account. The difference between prepare and execute is execute can't do that. But it can call functions that change the data on the blockchain. Theoretically you don't need the execute method as one could do everything with the prepare method but it makes the code more clear and 'separates' the logic.

Exercise: 

```
pub contract NumberContract {
  pub var myNumber: Int 
  
  pub fun updateMyNumber(newNumber: Int) {
     self.myNumber = newNumber 
  }
  
  init() {
    self.myNumber = 0 
  }
}

import NumberContract from Ox

transaction(myNewNumber: Int) {
 prepare(signer: AuthAccount) {}
 
 execute {
  NumberContract.updateMyNumber(newNumber: myNewNumber)
 }
}
```

### Chapter 2 - Day 3 

var flowCadenceCode: String = "isCool"
var people: [String] = ["Zach", "Unlimited", "Jacob"] 
var addresses: [Address] = [0x1, 0x2, 0x3] 

// index into arrays

var addresses: [Address] = [0x1, 0x2, 0x3]
log(addresses[0]) // 0x1
log(addresses[2]) // 0x3

// remove element from index 

var people: [String] = ["Jacob", "Alice", "Damian"]
people.remove(at: 1)
log(people) // ["Jacob", "Damian"] 











