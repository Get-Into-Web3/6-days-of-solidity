# 6 Days of Solidity

### Day 1: Making the zombie factory

1. Firstly, I got to know of the Smart Contracts, that form the fundamental building block of Ethereum Applications
2. All solidity source code start with a “Version pragma” that declares the version of solidity compiler the code   should use
3. State Variables:
    3.1 Permanently stored in contract storage (permanently written to Ethereum blockchain)
    3.2 Type we used on day 1:
        3.2.1 Unsigned integers (uint): non-negative integers
        3.2.2 string : used for UTF-8 data of arbitrary-length
4. Arrays: 
    4.1 Fixed arrays: eg- uint[10] studentData;
    4.2 Dynamic arrays eg- uint[] dynamic;
5. Types of math operations in solidity:
    5.1 Addition: x+y
    5.2 Subtraction: x-y
    5.3 Multiplication x*y
    5.4 Division: x/y
    5.5 Modulus: x%y
    5.6 Exponent: x = y**z (where, x = y to the power z)
6. Then I got to know the “struct” data type. In simpler terms I would say it is a custom data type that is created by the user. It can be declared by struct keyword. Eg:        struct Student{ uint age; string name; }
7. In this module, I learned to make an array of structs. Eg- Student[] public students (array of struct ‘Student’ named students.
8. Functions in solidity: 
    8.1 Syntax-  function printName(uint _sno, string _name) public{ }
    8.2 Here function is the keyword to declare a function, printName is the function name, takes in 2 parameters (_sno and _name) and public is the keyword, that allows             anyone to call the function and body goes in the {}
    8.3 ‘memory’ keyword is used to specify that function variable be stored in memory
    8.4 2 ways to pass an argument in a function:
        8.4.1 By value: original value remains unaffected
        8.4.2 By reference: changes takes place in the original value
9. Array.push() is used to add an element in the end of an array
10. Functions(public/private): public(by default) functions can be called from anywhere, while private functions can be called by functions of the same contract only
11. Functions in solidity can return values, either single or many of different data types as well.
12. Keccak256 - a hash function that maps a given data into a random 256-bit hexadecimal number. Also got to know, how we can typecast a given data to same other type
13. Events: these let the smart contract interact with the app-frontend whenever something happens. We ‘emit’ a response to an event.


### Day 2 Zombie attack their victims

1. In this lesson, I started with learning about mapping and addresses. Ethereum blockchain is made up of accounts  and each account has an 'address'. Mappings are another way to store data in a 'key-value' like way
2. msg.sender, one of the global variables in solidity, that refers to the address of the person calling a function
3. 'require()' statement is used in a function if we want a certain condition to be fullfilled before executing a function, the condition goes in the parenthesis of require()
4. Inheritence - one contract can inherit from another contract. Syntax- contract Child is Parent ; the child can access all the public variables and functions of parent. Child of child similarly inherits from parent of his parent as well.
5. in order to import another file we write:  import "./filename.sol";
6. Memory locations of variables:
    6.1 Storage: remains permanent on blockchain
    6.2 memory: are temporary
7. 2 more function visibilities apart from public and private: internal(similar to private but private functions can also be called by child) and external(similar to public, but can only be called outside contract)
8. interfaces- that allows 2 contracts to interact with each other


### Day 3 Advanced Solidity Concepts

1. In this lesson, we got to know that the smart contracts are immutable. Then we get to know of the OpenZeppelin library and the Ownable contact in it, onlyOwner Function of contract Ownable.
2. Function modifiers - these look quite similar to functions but are declared with a 'modifier' keyword. they can't be called directly and are used to change the behaviour of a function. they are called by writing their name abnd passing reqd arguments during calling some other function.
3. Then i got to know that a user has to spend "gas" in order to execute a function in a DApp. gas can be bought using ether, and every function has a gascost that is determined by the resources being used in that function, and therefore it becomes important to optimise a function to reduce gascost as possible.
4. the variable 'now' returns the current unix timestamp in a uint256 by default. 
5. it is important to make our contracts secure. And in order to do this, we can declare such functions as internal instead of public, and add onlyOwner modifier to functions that are only meant to be called by ownner of contract.
6. in order to save gas, it is advisable to set our functions as 'external view' since the gas is not required if the user is just viewing and the function is not changing anything on blockchain.
7. another way to reduce gascost is to reduce storage usage and using variables as in memory, especially in external view functions.
8. then i got to know of the for-loops in solidity, and they are same as in javascript.

### Day 4 Zombie Battle systems

In this module, we get to know of payable modifier, that can recieve ether. Further we used keccak256 hash function to generate a random number, by passing in 3 arguments( now, msg.sender, and an incrementing value). The rest of the module was based on what we learned in prior modules and involved refactoring our code, making some modifiers where a same require statement was being used in many functions, implementing win and loss count for zombies and deciding winner of a zombie battle using an if statement.

### Day 5 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 6 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
