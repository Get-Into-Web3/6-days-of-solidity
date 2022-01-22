# 6 Days of Solidity

### Day 1 Learnings
Started with the objective of the lesson that is creating a random zombie generator. The zombie DNA was visualized as a 16 digit integer in which a pair of 2 digits, mapped to different traits of the zombie. 

Then learnt about contracts which are the starting points of the projects. 
Learnt about version pragma which should be written on the top of every code so that the code doesn't break in future for other compiler versions. For the scope of the tutorial we used pragma solidity >=0.5.0 <0.6.0;. Learnt about state variables (the variables permanently stored in contract storage and written to Ethereum blockchain), uints (unsigned integers whose value is non negative), data types, different types of operators, structs (which allow us to create more complicated data types that have multiple properties), fixed and dynamic arrays, public (other contracts will be able to read from it but not write to it) and private arrays.

Also learnt about function declaration in Solidity, call by value (where the compiler creates a new copy of the parameter's value and passes it to the function), call by reference ( the function is called with a reference to original variable), different functions like: public (anyone or any other contract can call our contract's function and execute its code), private (only other functions within our contract will be able to call this function), view (only to view the data but not modify it) and pure (neither read nor modify the data).

Also learnt about how to specify the return type of the function ( returns (string memory)), hash function keccak256 (a version of SHA3)- a hash function basically maps an input into a random 256-bit hexadecimal number.

Also learnt about typecasting (it is just like we do in other languages) and finally events (to communicate that something happened on the blockchain to our app front end, which can be listening for certain events and take action when they happen). 



### Day 2 Learnings

In Lesson 2 we made our game a multi player game and also added a more fun way to create zombies instead of just generating them randomly. 

Learnt about addresses and how Ethereum is made up of accounts and the account has a balance Ether (currency used on the Ethereum blockchain). Each account has an address like a bank account number. Mappings are another way of storing organized data in Solidity which stores data in key - value format. Learnt about msg.sender which is one of those global variables that are available to all the functions and refers to the address of the person who called the current function. We used these to update our createZombie method to assign ownership of the zombie to whoever called the function. 

Learnt about require (used for condition) and used it in the function so that each player could call this function only once. If the condition inside require is true, it will execute the further code but if not, it will throw an error. 

Learnt about inheritance and used it to get access to a function from a function which has inherited it. Learnt about import which allows us to access other files inside a file and is used because sometimes a codebase is too large to be stored in a single file. 

Learnt about storage and memory data. Storage refers to the variables that are permanently stored on the blockchain. Memory variables are temporary and are erased when the function call ends. Most of the time the Solidity compiler handles the use of these keywords by default but there are times when we need to specify these keywords like dealing with structs and arrays. 

Learnt about two more types of function visibilities: internal and external. Internal is just like the private but it is also accessible to the contracts that inherit from this contract. External is somewhat same like public but it can only be called outside the contract and they cannot be called by any functions inside the contract. 

Learnt about interfaces and used it to access the CryptoKitties smart contract whose data is stored openly on the blockchain. Then used its getKitty function to do the required task. 

Also leant a very special thing about Solidity which I had not seen before in any language that I know. The functions in Solidity can return multiple values which can be very helpful. We also used the last unused two digits of the zombie DNA to handle " special " characterstics and used them to show the zombies having cat origin. And if statements are similar in Solidity just as in other languages. 

### Day 3 Learnings

Started with learning that once we deploy our contract to Ethereum, it is immutable that is we can never update or modify it. If there is a flaw in our contract, there is no way for us to patch it later. While this may sound bas but there is also a positive side to it that is the code is law and once we read the code of a contract and verify it, it will give expected results because no one can modify it now. 

We made function so that if in case something happens to the CryptoKitties contract then we can change the address to which our DApp was pointing because in absence of that function if the CryptoKitties contract went down then our DApp would point to nothing but a hardcoded address that no longer returned any kitties. 

Learnt about Ownable which is used when we want the ability to update the address in our contract but we don't want everyone to be able to update it. It sets owner to msg.sender, adds onlyOwner modifier and allows transfer of contract. Learnt about OpenZeppelin Solidity library which has secure and community vetted smart contracts that we can use in our own DApps. Learnt about modifiers (specified by the keyword modifier) which are used to check some requirements prior to execution. First the modifier of the function gets executed and when underscore ( _ ) and semi colon (;) is encountered, the further function gets executed.

Learnt about a very important security concern that is if DApp is on Ethereum it doesn't mean that it is completely decentralized because owner can add a malicious function in the code So we have to actually read the full source code to make sure it is free of special controls by the owner. Learnt about gas which is the currency paid by users every time they execute a function. Users spend ETH to buy gas to execute functions on the DApp. Code optimization is very important concern in Solidity because the more complex the code is or more the computing resources required, more is the usage of gas. 

When we execute a function, every single node on the network runs the same function to verify its output. So, thousands of nodes verifying every function execution is what makes Ethereum decentralized. According to me the main reason of charging for running function is to make sure that some one cannot clog up the network with an infinite loop, or hog all the network resources with really intensive computations.

After learning about gas and costs, every things was mainly aimed at optimizing the code. Like if we have multiple uints inside a struct, we can use smaller sized uint when possible so as to allow Solidity to pack these variables together to take up less storage. Also writing same uints together ( uint32, uint32 and then uint) is considered better in terms of storage.

Learnt about variable now which returns the current unix timestamp of the latest block (the number of seconds passed since Jan 1st 1970). We used level and readyTime properties on our Zonbies and modified our code so that the zombies do not keep feeding on unlimited kitties and their cool down timer is triggered after eating a kittie. We can also pass a storage pointer to a struct as an arguement to a private or internal function. Learnt that modifers can also take arguements just like functions do.

One important that I learnt about view function is that they don't cost any gas when they are called externally by the user. This is because view function only read data and do not modify it. This was a huge take away that we can use external view functions wherever possible to minimize the cost. Storage variables are expensive because every time we write storage we change data and in that cost comes in. For this we can rebuild an array in memory every time a function is called.

Also learnt about usage of for loops for code optimization (particularly in case of Crypto Zombies) in Solidity. 


### Day 4 Learnings

Learnt about the Payable modifier. Since in Ethereum the money, data and the contract code live on Ethereum itlself, it allows us to call a function and pay the money at the same time. Someone can call the function (marked as payable) from Web3.js that is from our DApp's JavaScript front end and pay the money (Ether) by simple logic. We can also make a withdraw function to withdraw the Ether from the contract.

Learnt about generating random numbers using keccak256 hash function and also learnt that the method which we were using is not totally secure. One safe way was to use an oracle to access a random number function from outside of the Ethereum blockchain. Learnt about else statements which is also same as other languages' if else implementation
The chapter was focused on implementing the logic of zombie battles andd fights and some features that will be updated as a result of the fights between the zombies. All this was basically the implementation of all the stuff we had learnt till here. 


### Day 5 Learnings

Learnt about ERC20 tokens. A token on Ethereum is basically just a smart contract that implements a standard set of functions that all other token contracts share. The interesting point I got to know was that if our application is capable of interacting with one ERC20 token, it is also capable of interacting with any ERC20 token. But here for CryptoZombies we can use ERC721 tokens.

When we implement any token contract, we first copy the interface to its own Solidity file and import it, then we have our contract inherit from it and then override each method with a function definition. Learnt about balanceOf function which takes an address and returns how many tokens that address owns. Also learnt about ownerOf function which takes tokenId as the parameter and returns the address of the person who owns it. Also we cannot have function and a modifier with same name. We had done this in our code so we had to refactor the code. 

Learnt about the two different ways to transfer tokens. First was : the owner calls the transferFrom function with his address as _from_ parameter, the destination address as _to_ parameter and the tokenId of the token for transfer. Second was: owner calls approve function with tokenId, the contract stores who is approved for taking token, then after the owner who is approved calls the transferFrom function, the token is transferred. 

Learnt about overflows (for example increasing a uint number beyond its maximum value after which it is set to 0) and underflows ( for example decrementing a value to its minimum value or subtracting 1 from 0 value). As a solution for this we use SafeMath library provided by OpenZeppelin. We can use SafeMath in the code like: using SafeMath for uint256. Learnt about add, mul, sub and div which perform the desired operations but at the same time they protect overflows. We can also use SafeMath for particular uint like SafeMath32.

Finally learnt about comments whose syntax in Solidity is same as in C++.



### Day 6 Learnings

Here we create a basic web page where our users can interact with. Learnt that Ethereum network is made up of nodes, with each containing a copy of the blockchain. In case we need to call a function on a contract, we query one of the nodes and tell it the address of contract, function we want to call and the variables which we want to pass. A query for calling a function is very big and cumbersome but Web3.js hides these nasty queries below the surface, so we only need to interact with a convenient and easily readable JavaScript interface. 

In setting a Web3 provider we need a node to handle our reads and writes. Infura is a third party service which makes the stuff little easier so that we do not need to maintain our own Ethereum node. We can easily send and receive messages to/from the Ethereum blockchain without needing to set up and maintain our own node. Also learnt about Metamask which is browser extension for Chrome and FireFox which allows the users to securely manage their ethereum accounts and private keys, and use the accounts to interact with the Web3.js websites. 

For talking to our contract we need 2 things that is address and its ABI. When we deploy our contract, it gets fixed address on Ethereum where it will live forever. Learnt about ABI (Application Binary Interface) which is a representation of our contracts' methods in JSON format. We are provided with the ABI by the Solidity compiler when we compile our contract to deploy to Ethereum.

Web3.js has two methods which we use to call functions on our contract: call and send. The call method is used for view and pure functions and only runs on local node. The send method is used for functions which are not view and pure and it changes data on blockchain. On MetaMask the user can manage multiple accounts as well as switch them and we can also by a logic see that which account is currently active.

Got to know about wei which is the smallest sub-unit of Ether and 1 ether equals 10^18 wei. In web3.js we can subscribe to an event so our web3 provider triggers some logic in our code every time it fires. Also learnt about indexed keyword which is used for filtering events and only listen for changes related to the curren user. We can also query past events using getPastEvents and this can be used if we want to display some sort of historical data from our record.

So that is all what I learnt from these 6 modules in the 6DaysofSolidity challenge.
