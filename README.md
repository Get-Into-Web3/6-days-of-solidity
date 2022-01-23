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


### Day 2 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 3 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 4 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 5 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 6 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
