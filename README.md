# 6 Days of Solidity

### Day 1 Learnings
Started with the objective of the lesson that is creating a random zombie generator. The zombie DNA was visualized as a 16 digit integer in which a pair of 2 digits, mapped to different traits of the zombie. 

Then learnt about contracts which are the starting points of the projects. 
Learnt about version pragma which should be written on the top of every code so that the code doesn't break in future for other compiler version. For the scope of the tutorial we used pragma solidity >=0.5.0 <0.6.0;. Learnt about state variables (the variables permanently stored in contract storage and written to Ethereum blockchain), uints (unsigned integers whose value is non negative), data types, different types of operators, structs (which allow us to create more complicated data types that have multiple properties), fixed and dynamic arrays, public (other contracts will be able to read from it but not write to it) and private arrays.

Also learnt about function declaration in Solidity, call by value (where the compiler creates a new copy of the parameter's value and passes it to the function), call by reference ( the function is called with a reference to original variable), different functions like: public (anyone or any other contract can call our contract's function and execute its code), private (only other functions within our contract will be able to call this function), view (only to view the data but not modify it) and pure (neither read nor modify the data).

Also learnt about how to specify the return type of the function ( returns (string memory)), hash function keccak256 (a version of SHA3)- a hash function basically maps an input into a random 256-bit hexadecimal number.

Also learnt about typecasting (it is just like we do in other languages) and finally events (to communicate that something happened on the blockchain to our app front end, which can be listening for certain events and take when they happen). 



### Day 2 Learnings

In Lesson 2 we made our game a multi player game and also added a more fun way to create zombies instead of just generating them randomly. 

Learnt about addresses and how Ethereum is made up of accounts and the account has a balance Ether (currency used on the Ethereum blockchain). Each account has an address like a bank account number. Mappings are another way of storing organized data in Solidity which stores data in key - value format. Learnt about msg.sender which is one of those global variables that are available to all the functions and refers to the address of the person who called the current function. We used these to update our createZombie method to assign ownership of the zombie to whoever called the function. 

Learnt about require (used for condition) and used it in the function so that each player could call this function only once. If the condition inside require is true, it will execute the further code but if not, it will throw an error. 

Learnt about inheritance and used it to get access to a function from a function which has inherited it. Learnt about import which allows us to access other files inside a file and is used because sometimes a codebase is too lare to be stored in a single file. 

Learnt about storage and memory data. Storage refers to the variables that are permanently stored on the blockchain. Memory variables are temporary and are erased when the function call ends. Most of the time the Solidity compiler handles the use of these keywords by default but there are times when we need to specify these keywords like dealing with structs and arrays. 

Calculated new zombie's DNA using the simple formula: the average between the feeding zombie's DNA and target's DNA. Learnt about two more types of function visibilities: internal and external. Internal is just like the private but it is also accessible to the contracts that inherit from this contract. External is somewhat same like public but it can only be called outside the contract and they cannot be called by any functions inside the contract. 

Learnt about interfaces and used it to access the CryptoKitties smart contract whose data is stored openly on the blockchain. Then used its getKitty function to do the required task. 

Also leant a very special thing about Solidity which I had not seen before in any language that I know. The functions in Solidity can return multiple values which can be very helpful. We also used the last unused two digits of the zombie DNA to handle " special " characterstics and used them to show the zombies having cat origin. And if statements are similar in Solidity just as in other languages. 

### Day 3 Learnings

Started with learning that once we deploy our contract to Ethereum, it is immutable that is we can never update or modify it. If there is a flaw in our contract, there is no way for us to patch it later. While this may sound bas but there is also a positive side to it that is the code is law and once we read the code of a contract and verify it, it will give expected results because no one can modify it now. 

We made function so that if in case something happens to the CryptoKitties contract then we can change the address to which our DApp was pointing because in absence of that function if the CryptoKitties contract went down then our DApp would point to nothing but a hardcoded address that no longer returned any kitties. 

Learnt about Ownable which is used when we want the ability to update the address in our contract but we don't want everyone to be able to update it. It sets owner to msg.sender, adds onlyOwner modifier and allows transfer of contract. Learnt about OpenZeppelin Solidity library which has secure and community vetted smart contracts that we can use in our own DApps. Learnt about modifiers (specified by the keyword modifier) which are used to check some requirements prior to execution. First the modifier of the function gets executed and when underscore ( _ ) and semi colon (;) is encountered, the further function gets executed.

Learnt about a very important security concern that is if DApp is on Ethereum it doesn't mean that it is completely decentralized because owner can add a malicious function in the code So we have to actually read the full source code to make sure it is free of special controls by the owner. Learnt about gas which is the currency paid by users every time they execute a function. Users spend ETH to buy gas to execute functions on the DApp. Code optimization is very important concern in Solidity because the more complex the code is or more the computing resources required, more is the usage of gas. 

When we eexecute a function, every single node on the network runs the same function to verify its output. So, thousands of nodes verifying every function execution is what makes Ethereum decentralized. According to me the main reason of charging for running function is to make sure that some one ccannot clog up the network with an infinite loop, or hog all the network resources with really intensive computations.

After learning about gas and costs, every things was mainly aimed at optimizing the code. Like if we have multiple uints inside a struct, we can use smaller sized uint when possible so as to allow Solidity to pack these variables together to take up less storage. Also writing same uints together ( uint32, uint32 and then uint) is considered better in terms of storage.

Learnt about variable now which returns the current unix timestamp of the latest block (the number of seconds passed since Jan 1st 1970). We used level and readyTime propoerties on our Zonbies and modified our code so that the zombies do not keep feeding on unlimited kitties and their cool down timer is triggered after eating a kittie. We can also pass a storage pointer to a struct as an arguement to a private or internal function. Learnt that modifers can also take arguements just like functions do.

One important that I learnt about view function is that they don't cost any gas when they are called externally by the user. This is because view function only read data and do not modify it. This was a huge take away that we can use external view functions wherever possible to minimize the cost. Storage variables are expensive because every time we write storage we change data and in that cost comes in. For this we can rebuild an array in memory every time a function is called.

Also learnt about usage of for loops for code optimization (particularly in case of Crypto Zombies) in Solidity. 


### Day 4 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 5 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 6 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
