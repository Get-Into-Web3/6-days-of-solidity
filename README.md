# 6 Days of Solidity

### Day 1 Learnings

# Making the Zombie Factory
* I get to know that, Solidity which is a language for writing Smart Contracts.A contract is the fundamental building block of Ethereum applications.
*All solidity source code should start with a "version pragma" — a declaration of the version of the Solidity compiler this code should use. This is to prevent issues with future compiler versions potentially introducing changes that would break your code.It looks like this: pragma solidity >=0.5.0 <0.6.0;
* Solidity deals with variables and integers. for e.g: contract ZombieFactory { uint dnaDigits = 16 }
* Math Oprations in Solidity.same as in most programming languages: Addition: x + y Subtraction: x - y, Multiplication: x * y Division: x / y Modulus / remainder: x % y
* To deal with complex data type ,Solidity provides structs: for e.g: struct Zombie{ string name; uint dna; }
* When we want a collection of something,we can use an array.There are two types of arrays in Solidity: fixed arrays and dynamic arrays: // Array with a fixed length of 2 elements: uint[2] fixedArray; // another fixed Array, can contain 5 strings: string[5] stringArray; // a dynamic Array - has no fixed size, can keep growing: uint[] dynamicArray;
* Function in Solidity.It looks like the following: function createZombie(string memory _name,uint _dna) public {
}
* Working With Structs and Arrays.array.push() adds something to the end of the array. for e.g: Person[] public people; Person satoshi = Person(172, "Satoshi"); people.push(satoshi);
* In Solidity, functions are public by default. This means anyone (or any other contract) can call your contract's function and execute its code.Obviously this isn't always desirable, and can make a contract vulnerable to attacks. Thus it's good practice to mark your functions as private by default. declaration of a private function: function _addToArray(uint _number) private { numbers.push(_number); }
* More on Functions: Return Values To return a value from a function, the declaration looks like this: function sayHello() public returns (string memory) { return greeting; } Function modifiers function sayHello() public view returns (string memory) {
* Ethereum has the hash function keccak256 built in, which is a version of SHA3. A hash function basically maps an input into a random 256-bit hexadecimal number. A slight change in the input will cause a large change in the hash. for e.g: keccak256(abi.encodePacked("aaaac")); Typecasting: uint8 c = a * uint8(b);
* Events are a way for your contract to communicate that something happened on the blockchain to your app front-end, which can be 'listening' for certain events and take action when they happen. for e.g: event IntegersAdded(uint x, uint y, uint result); function add(uint _x, uint _y) public returns (uint) { uint result = _x + _y; // fire an event to let the app know the function was called: emit IntegersAdded(_x, _y, result); return result; }

### Day 2 Learnings

# Zombies Attack Their Victims
* Mappings and Addresses: Addreses: The Ethereum blockchain is made up of accounts, which you can think of like bank accounts. An account has a balance of Ether (the currency used on the Ethereum blockchain), and you can send and receive Ether payments to other accounts, just like your bank account can wire transfer money to other bank accounts. e.g: 0x0cE446255506E92DF41614C46F1d6df9Cc969183 Mappings: A mapping is essentially a key-value store for storing and looking up data. In the first example, the key is an address and the value is a uint, and in the second example the key is a uint and the value a string.
* Msg.sender, In Solidity, there are certain global variables that are available to all functions. One of these is msg.sender, which refers to the address of the person (or smart contract) who called the current function.
* Require is quite useful for verifying certain conditions that must be true before running a function.
* Inheritance, This can be used for logical inheritance (such as with a subclass, a Cat is an Animal). But it can also be used simply for organizing your code by grouping similar logic together into different contracts.
* Import, When you have multiple files and you want to import one file into another, Solidity uses the import keyword
* Storage vs Memory, Most of the time you don't need to use these keywords because Solidity handles them by default. State variables (variables declared outside of functions) are by default storage and written permanently to the blockchain, while variables declared inside functions are memory and will disappear when the function call ends. However, there are times when you do need to use these keywords, namely when dealing with structs and arrays within functions.
* More on Function Visibility, In addition to public and private, Solidity has two more types of visibility for functions: internal and external.
* internal is the same as private, except that it's also accessible to contracts that inherit from this contract. (Hey, that sounds like what we want here!).
* external is similar to public, except that these functions can ONLY be called outside the contract — they can't be called by other functions inside that contract.
* For our contract to talk to another contract on the blockchain that we don't own, first we need to define an interface.
* Handling Multiple Return Values

### Day 3 Learnings

# Advanced Solidity Concepts
* Immutability of Contracts, The initial code you deploy to a contract is there to stay, permanently, on the blockchain. This is one reason security is such a huge concern in Solidity. If there's a flaw in your contract code, there's no way for you to patch it later.
* Ownable Contracts, one common practice that has emerged is to make contracts Ownable — meaning they have an owner (you) who has special privileges.
* onlyOwner Function Modifier, A function modifier looks just like a function, but uses the keyword modifier instead of the keyword function. And it can't be called directly like a function can — instead we can attach the modifier's name at the end of a function definition to change that function's behavior.
* Gas — the fuel Ethereum DApps run on
* Time units - Solidity provides some native units for dealing with time.
* An important security practice is to examine all your public and external functions, and try to think of ways users might abuse them.
* View functions don't cost gas
* As Storage is Expensive, Declaring arrays in memory
* For Loops

### Day 4 Learnings

# Zombie Battle System
* payable functions are part of what makes Solidity and Ethereum so cool — they are a special type of function that can receive Ether.
* Withdraws: After you send Ether to a contract, it gets stored in the contract's Ethereum account, and it will be trapped there — unless you add a function to withdraw the Ether from the contract.
* The best source of randomness we have in Solidity is the keccak256 hash function.
* a winCount and a lossCount that will increment or decrement depending on the outcome of the result.

### Day 5 Learnings

# ERC721 & Crypto-Collectibles
* Tokens on Ethereum,A token on Ethereum is basically just a smart contract that follows some common rules — namely it implements a standard set of functions that all other token contracts share
* ERC721 Standard, Multiple Inheritance, ERC721 Standard, When implementing a token contract, the first thing we do is copy the interface to its own Solidity file and import it, import "./erc721.sol";. Then we have our contract inherit from it, and we override each method with a function definition.
* balanceOf: This function simply takes an address, and returns how many tokens that address owns.
* ownerOf: This function takes a token ID (in our case, a Zombie ID), and returns the address of the person who owns it.
* Refactoring, contracts will expect our contract to have functions with these exact names defined. That's what makes these standards useful
* ERC721: Transfer Logic.ERC721 spec has 2 different ways to transfer tokens: function transferFrom(address _from, address _to, uint256 _tokenId) external payable; function approve(address _approved, uint256 _tokenId) external payable;
* ERC721: Transfer Cont'd, implementation of external transferFrom function.
* ERC721: Approve, approve the transfer happens in 2 steps: You, the owner, call approve and give it the _approved address of the new owner, and the _tokenId you want him to take. The new owner calls transferFrom with the _tokenId. Next, the contract checks to make sure the new owner has been already approved, and then transfers him the token.
* Contract security enhancements: Overflows and Underflows
* Using SafeMath, To prevent overflow, OpenZeppelin has created a library called SafeMath
* Commenting in Solidity is just like JavaScript
### Day 6 Learnings

# App Front-ends & Web3.js
* Intro to Web3.js: the Ethereum network is made up of nodes, with each containing a copy of the blockchain. When you want to call a function on a smart contract
* Web3 Providers: Infura,Metamask.
* Contract ABI, ABI stands for Application Binary Interface. Basically it's a representation of your contracts' methods in JSON format that tells Web3.js how to format function calls in a way your contract will understand.
* Calling Contract Functions, call is used for view and pure functions. It only runs on the local node, and won't create a transaction on the blockchain.
* send will create a transaction and change data on the blockchain. You'll need to use send for any functions that aren't view or pure.
* Sending Transactions, sending a transaction requires a from address of who's calling the function (which becomes msg.sender.
* Calling Payable Functions, The logic for attack, changeName, and changeDna will be extremely similar
* A wei is the smallest sub-unit of Ether — there are 10^18 wei in one ether.
