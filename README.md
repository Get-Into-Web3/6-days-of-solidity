# 6 Days of Solidity

### Day 1 Learnings

# First Lesson
[Level-1 CryptoZombie](https://share.cryptozombies.io/en/lesson/1/share/Manan?id=Y3p8MTY5OTE4)
<p align="center">
  <img src="https://www.shawntabrizi.com/assets/images/img_5add32b676792.png" width="350" height="350" title="hover text">
</p>
1. In the first lesson, I learnt about how to start a program in Solidity which is a language for writing Smart Contracts. 
First of all, we need to define a version of the Solidity we are using. 
The same can be done using 
```
pragma solidity <version>;
```

2. Then, we can define a smart contract using the keyword contract followed by the name of a contract and the pair of curly braces.
After that, in the second lesson, i learnt to declare the state variables. State variables remain permanently stored in the Ethereum Blockchain. We can think of them as storing the data in the database. 
uint is used for declaring unsigned integers. int can also include signed numbers. 

3. Then, I learnt about the math operations that can be performed using Solidity like Addition, Subtraction, Multiplication, Division, Modulus, Exponential.

4. In the next chapter, I learnt about Struct data type. It can have properties of an object. For example, a person struct can contain properties like name and age.
It can be declared using:
```
struct Car {
	uint number;
	string model;
}
```

5. The following chapter discusses about arrays. When you want a collection of something, you can use an array. There are two types of arrays in Solidity: fixed arrays and dynamic arrays
```
>> Fixed Array is of a fixed size like uint[2] num contains two unsigned numbers.
>> A dynamic array is of dynamic size like uint[] dynam.
```
If we want other contracts to read from an existing array, we can declare the array as public.

6. We can declare the functions like this:
```
function eatHamburgers(string memory _name, uint _amount) public {

}
```

7. We can pass the parameters to the function by value (Compiler creates a new copy of the parameter value and passes to the function).
Or by reference (Function changes the value of the variable it receives, the value of the original variable gets changed).

8. We can add an item to our created array like this
```
Person manan = Person(21, "Manan");
people.push(manan);
```

9. Functions are public by default in Solidity. That means anyone can call the function and execute code.
But sometimes, due to security reasons, we make it private. 

10. return parameter returns the value from the function. If our function doesn't change any values or write anything, we can declare it as a view function. 
If we do not access any data in the app, it is a pure function. 

11. A hash function maps an input into a random 256-bit hexadecimal number. Ethereum has the hash function keccak256 built in, which is a version of SHA3.

12. Events are a way for your contract to communicate that something happened on the blockchain to your app front-end, which can be 'listening' for certain events and take action when they happen.



### Day 2 Learnings
[Level-2 CryptoZombie](https://share.cryptozombies.io/en/lesson/2/share/Manan?id=Y3p8MTY5OTE4)

1. Mappings are a key-value store for storing and looking up data. 
It is defined like this:
```
mapping (address => uint) public balance;
```
This generally means that the balance can be found by entering the address and balance will be returned which is a uint.

2. msg.sender is a global variable which refers to the address of the person who called the cuurent function.

3. require keyword helps to verify certain conditions that must be true before running a function.

4. In order to avoid writing long smart contracts, we can use inheritance. It lets us split our code logic across multiple contracts to organize the code.
Let us say Car contract inherits vehicle. We can represent it using the following statement:
```
contract Car is vehicle {
}
```

5. import keyword helps you to import one file into another. 

6. In Solidity, there are two locations you can store variables — in storage and in memory.
Storage refers to variables stored permanently on the blockchain. Memory variables are temporary, and are erased between external function calls to your contract. 
State variables are storage by default and variables declared inside functions are memory. 

7. In **Internal visibility**, t's also accessible to contracts that inherit from this contract.
In **external visibility**, functions can only be called outside the contract. 

8. In order for one contract to talk to another contract on the blockchain that we don't own, we need to define an interface.
In an interface, function definition is not there. 

9. Solidity can return multiple values.
10. We can also write if statements in Solidity that tests a condition and then executes code if the condition passes.

### Day 3 Learnings
[Level-3 CryptoZombie](https://share.cryptozombies.io/en/lesson/3/share/Manan?id=Y3p8MTY5OTE4)

In Lesson 3, we discuss some more advanced Solidity Concepts.
1. After we deploy a contract to Ethereum, it is immutable. That means it cannot be modified. 
2. If we want a contract that can be changed by only a certain person or who created that contract, we can make the contract Ownable.They then have an owner who has special priveleges. 
3. Constructor gets executed only once when the contract is first created. 
4. Modifiers are kind of half-functions that are used to modify other functions, usually to check some requirements prior to execution.
5. Users have to pay every time they execute a function on the DApp using a currency called gas. 
	- Amount of gas required depends on how complex a function's logic is.
	- The total gas cost of your function is the sum of the gas costs of all its individual operations.
6. Storage Pointer can be passed to a struct as an argument to a private or internal function. 
7. We can also pass parameters to a modifier.
8. View functions don't cost any gas when they are called externally by a user. Becuase they actually change anything. 
9. Storage operation is expensive as the data is permanantly written to the blockchain. 
10. We can use the memory keyword with arrays to create a new array inside a function without needing to write anything to storage. The array will only exist until the end of the function call, and this is a lot cheaper gas-wise than updating an array in storage — free if it's a view function called externally.

### Day 4 Learnings
[Level-4 CryptoZombie](https://share.cryptozombies.io/en/lesson/4/share/Manan?id=WyJjenwxNjk5MTgiLDEsMTRd)

1. In Ethereum, both the money (Ether), the data (transaction payload), and the contract code itself all live on Ethereum, it's possible for us to call a function and pay money to the contract at the same time.
2. Wei is the smallest unit of Ethereum.
3. We cannot transfer Ether to an address unless that address is of type address payable. 
4. keccak256 hash function lets us generate random numbers too.
	- Nonce is a number that is only ever used once.
5. In Ethereum, when you call a function on a contract, you broadcast it to a node or nodes on the network as a transaction. 
6. The nodes on the network then collect a bunch of transactions, try to be the first to solve a computationally-intensive mathematical problem as a "Proof of Work", and then publish that group of transactions along with their Proof of Work (PoW) as a block to the rest of the network.
7. Multiple modifiers can be used on a single function. 

### Day 5 Learnings
[Level-5 CryptZombie](https://share.cryptozombies.io/en/lesson/5/share/H4XF13LD_MORRIS_%F0%9F%92%AF%F0%9F%92%AF%F0%9F%98%8E%F0%9F%92%AF%F0%9F%92%AF?id=Y3p8MTY5OTE4)

This Lesson discusses about ERC721 and Crypto-Collectibles.
1. A token on Ethereum is basically just a smart contract that follows some common rules — namely it implements a standard set of functions that all other token contracts share.
2. A smart contract usually has a mapping 
```
mapping(address => uint256) balances;
```
This mapping keeps track of how much balance each address has.
3. ERC721 tokens are not interchangeable since each one is assumed to be unique, and are not divisible. You can only trade them in whole units, and each one has a unique ID.
4. When implementing a token contract, the first thing we do is copy the interface to its own Solidity file and import it.
5. In Solidity, our contract can inherit from multiple contracts like
```
contract Steering is Car, Vehicle{
}
```
6. OpenZeppelin has created a library called SafeMath that helps to prevent the issue of overflow. 
7. The difference between assert and require is that require will refund the user the rest of their gas when a function fails, whereas assert will not. 
8. In safemath, if we want to add 1 to a variable, we use the following syntax
```
var = var.add(1);
```
instead of
```
var++;
```
9. SafeMath16 and SafeMath32 prevents overflow issue for uint16 and uint32 respectively. 
10. For single line comment:
```
// This is a single-line comment
```
For multi-line comment:
```
/* This is a multi-line comment.
   Solidity is great
*/
```

### Day 6 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
