# 6 Days of Solidity

### Day 1 Learnings
Started with the objective of the lesson that is creating a random zombie generator. The zombie DNA was visualized as a 16 digit integer in which a pair of 2 digits, mapped to different traits of the zombie. 

Then learnt about contracts which are the starting points of the projects. 
Learnt about version pragma which should be written on the top of every code so that code doesn't break in future for other compiler version. Learnt about state variables, data type, operators, structs, fixed and dynamic arrays, public and private arrays.

Also learnt about call by value, call by reference, different functions like: public, private, view and pure, hash function keccak256 (a version of SHA3), typecasting and finally events. 



### Day 2 Learnings

In Lesson 2 we made our game a multi player game and also added a more fun way to create zombies instead of just generating them randomly. 

Learnt about addresses and how Ethereum is made up of accounts and the account has a balance Ether. Each account has an address like a bank account number. Mappings are another way of storing organized data in Solidity which stores data in key - value format. Learnt about msg.sender which is one of those global variables that are available to all the functions and refers to the address of the person who called the current function. We used these to update our createZombie method to assign ownership of the zombie to whoever called the function. 

Learnt about require and used it in the function so that each player could call this function only once. If the condition inside require is true, it will execute the further code but if not, it will throw an error. 

Learnt about inheritance and used it to get access to a function from a function which has inherited it. learnt about import which allows us to access other files inside a file and is used because sometimes a codebase is too lare to be stored in a single file. 

Learnt about storage and memory data. Storage refers to the variables that are permanently stored on the blockchain. Memory variables are temporary and are erased when the function call ends. Most of the time the Solidity compiler handles the use of these keywords by default but there are times when we need to specify these keywords like dealing with structs and arrays. 

Calculated new zombie's DNA using the simple formula: the average between the feeding zombie's DNA and target's DNA. Learnt about two more types of function visibilities: internal and external. Internal is just like the private but it is also accessible to the contracts that inherit from this contract. External is somewhat same like public but it can only be called outside the contract and they cannot be called by any functions inside the contract. 

Learnt about interfaces and used it to access the CryptoKitties smart contract whose data is stored openly on the blockchain. Then used its getKitty function to do the required task. 

Also leant a very special thing about Solidity which I had not seen before in any language that I know. The functions in Solidity can return multiple values which can be very helpful. 

### Day 3 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 4 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 5 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 6 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
