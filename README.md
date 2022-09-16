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
Dev Experience
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

Arrays, Dictionaries, Unwrapping and Optionals 

```
var people: [String] = ["Soccer", "Hockey", "Football"] 
log(people)
```

```
var favSocialMedias: {String: UInt64} = {"Facebook": 0, "Instagram": 4, "Twitter": 1, "Youtube": 2}
```

The ! operator forces the program to read the type params. This happens when a type optional ? isn't provided. This is best practice to do one or the other; not only will the code throw an error but if a called variable isn't present then the program will explode.

We get the error in the image below since the type is neither optional nor is the variable unwrapped. 


### Chapter 3 - Day 4 

Structs 

Structs are containers of other types. Structs can only have the pub access modifier.

##### Exercise

Deply new contract with a struct, create a dictionary, create a function that adds to array/dictionary

```
pub contract BetAuth {
    pub var bets: {Address: Bet}
    
    pub struct Bet {
        pub let firstName: String
        pub let teamName: String
        pub let playerName: String
        pub let amount: Int
        pub let account: Address

        init(_firstName: String, _teamName: String, _playerName: String, _amount: Int, _account: Address) {
            self.firstName = _firstName
            self.teamName = _teamName
            self.playerName = _playerName
            self.amount = _amount
            self.account = _account
        }
    }

    pub fun addBet(firstName: String, teamName: String, playerName: String, amount: Int, account: Address) {
        let newBet = Bet(_firstName: String, _teamName: String, _playerName: String, _amount: Int, _account: Address)
        self.bets[account] = newBet
    }

    init() {
        self.bets = {}
    }
}

```

Add a transaction to call created function

```
import BetAuth from 0x01

transaction(firstName: String, teamName: String, playerName: String, amount: Int, account: Address) {

    prepare(signer: AuthAccount) {}

    execute {
        BetAuth.addBet(firstName: String, teamName: String, playerName: String, amount: Int, account: Address)
        log("We're done.")
    }
}
```

Read defined Struct

```
pub fun main(account: Address): BetAuth.Bet {
    return Authentication.bets[account]!
}

```



