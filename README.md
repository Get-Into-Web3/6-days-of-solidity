# 6 Days of Solidity

### Day 1 Learnings

# First Lesson

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

### Day 3 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 4 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 5 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 6 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
