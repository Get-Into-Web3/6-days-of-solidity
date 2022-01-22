# 6 Days of Solidity

## `Day 1 Learnings`

### `Contract`

`Contract` is like class in C++. It encapsulates the solidity code like `functions, variables, structs`.

```solidity
contract HelloWeb3{
	
}
```

### Version `pragma`

Solidity code starts with version pragma which defines the version of compiler the solidity code should use

It does not change the version of compiler but it checks whether the code written matches the rules of the version specified.

```solidity
pragma solidity >=0.6.5;
```

the above statement will ensure that the code will compile in any version of compiler starting from 0.6.5

```solidity
pragma solidity <0.7.0;
```

the above statement will ensure that the code will compile in any version of compiler below 0.7.0;

```solidity
pragma solidity ^0.6.5;
```

the above statement will ensure that the code will compile in any version of compiler from 0.6.5 to 0.7.0, i.e. will not work from 0.7.0

### State Variables and Integers

Variables are considered as columns we store in db. 

### Variable types:

`State variables` : Exist in contract storage. 

`Local variables` : Exist only within the function

`Global variables` : Exist in global workspace and provide information about the blockchain and transaction properties.


### `uint` - unsigned integer

by default `uint = uint256` (256 bit unsigned integer)

`uint` can have less sizes like `uint8, uint16, uint32`...

### Math Operations

Math operations in `solidity` are same as most of the programming languages

```solidity
Addtion x + y
Subtraction  x - y
Multiplication x * y
Division x / y
Exponential/ Power of : x ** y
```

### ```Structs```

Structure is data type which can hold different data types together

Sometimes we need more complex data structures like struct

```solidity
struct StructName{
	
}
```
```solidity
struct Web3Struct{
	uint age;
	string str;
}
```

### Arrays

Collection of homogeneous data types is arrays

`Fixed arrays` : type arrayName [ arraySize ];
`Dynamic arrays` : Dynamic memory arrays are created using new keyword.
```solidity
uint size = 3;
uint balance[] = new uint[](size);
```

### Function Declarations

functions are series of actions grouped together for reuse

functions in solidity are declared using function keyword
```solidity
function funcName( datatype _para, datatype _para1){
}
```
Its convention to start parameters names with _

Parameters are passed in two ways
1) By ```value``` : New copy of variable is created for a function
2) By ```reference``` : Reference to original variable is passed as parameter

### Working With Structs and Arrays

Struct is collection of heterogeneous data types

Arrays are collection of homogeneous data types

struct keyword is used for declaring struct

arrays can be declared using []

Lets create struct Student 
```solidity
struct Student{
	string memory name;
	uint id;
}
```
Now we have to create array of Students

```solidity
Student[] students;
```

Lets add some values to students array
```solidity
function addStudent( string memory _name, uint _id ) public{
	students.push( Student(name, id));		//push struct to students array
}
```

### Private / Public Functions

Access specifiers in Solidity

```Public``` : funtions can be accessible outside the contract also 

```Private``` : functions are accessible within the contract only


public function
```solidity
function funcName( datatype1 _name1, datatype2 _name2) public{
	
}
```
private function

```solidity
function _funcName( datatype1 _name1, datatype2 _name2) private{
	
}
```

### More on Functions

```Return values```

Need return and returns keyword

```solidity
function funcName( datatype1 _name1 ) public returns ( datatype1 ){
	return name2;
}
```

### Function Modifiers

How we access the data of the contract defines different function modifiers

```view``` : only viewing data and not modifying data

```solidity
function funcName() public view returns(datatype1) {
	return(name1);
}
```
```pure``` : doesn't even accessing any data

```solidity
function funcName( datatype1 _name1, datatype1 _name2 ) private pure returns( datatype1 )  {
	return name1 + name2;
}
```
### Keccak256 and Typecasting

### ```Keccak256```

Ethereum has the hash function keccak256 built in, which is a version of SHA3. A hash function basically maps an input into a random 256-bit hexadecimal number. A slight change in the input will cause a large change in the hash.

Syntax
 ```solidity
 keccak256(bytes)
 ```

To pass parameter to ```keccak256``` pack the parameter into bytes
 ```solidity
 abi.encodePacked(param)
 ```

### Typecasting

Converting between data types

You can't perform operation on two different data types one from them need to typecast in order to get the result.
```solidity
uint8 a = 5;
uint b = 6;
// throws an error because a * b returns a uint, not uint8:
uint8 c = a * b;
// we have to typecast b as a uint8 to make it work:
uint8 c = a * uint8(b);
```

### Putting It Together

```solidity
pragma solidity ^0.7.5;
contract StartUps{
	struct Company{
		string name;
		string founder;
		uint marketcap;
	}
	Company[] companies;

	function addCompany( _name memory string, _founder memory string, uint _marketcap) public{
		companies.push(Company(_name, _founder, _marketcap));
	} 
	function getCompanyDetails(_id uint) public view returns(string memory, string memory, uint){
		return companies[_id];
	}
}
```

### Events

Events are a way for your contract to communicate that something happened on the blockchain to your app front-end, which can be 'listening' for certain events and take action when they happen.

```solidity
// declare the event
// whenever emited this event in frontend you can handle this
event IntegersAdded(uint x, uint y, uint result);

//function which is going to emit the event
function add(uint _x, uint _y) public returns (uint) {
  //Addition Operation happens
  uint result = _x + _y;
  // fire an event to let the app know the function was called:
  emit IntegersAdded(_x, _y, result);
  return result;
}
//In your app you can access the result and do operations
YourContract.IntegersAdded(function(error, result) {
  // do something with result
})
```

### Web3.js

For communicating with the contract Ethereum has JavaScript Library ```web3.js```.


## ```Day 2 Learnings```

### Mappings and Addresses

```Address```

Ethereum blockchain is made up of accounts just like you have bank account. And each account has address as you have account no.

```Mappings```

Data structure which as its name suggests maps key to value

```mapping``` keyword is used to declare mappings

lets take example as mapping address to name and make it public so it will look something like below

```solidity
mapping( address => string ) public addressToName;
```

### ```msg.sender```

As we discussed before solidity has some global variables and this variables are accessible to all functions. msg.sender is global variable which returns the address of the person who called the function.
```solidity
address addr = msg.sender;
```

### Require

In simple language you can compare require with if statement i.e. require requires certain conditions to be satisfied then only executes next lines.

Else throws error and won't execute further.

```solidity
require(msg.sender == owner);
```

### Inheritance

Inheritance is feature of OOP which provide code reuse and efficiency.

Inheritance in Solidity is achieved through ```is``` keyword 

```solidity
contract Parent{
	//some code
}

contract Child is Parent{
	//some code
}
```

### Import

Importing files in our code solidity has import keyword.
put import statement after pragma version 
```solidity
import "./path/file";
```
### Storage vs Memory (Data location)

In solidity you can store variables in two locations storage and memory

```Storage``` : Variables are stored permanently on Blockchain

```Memory``` : Variables are stored temporarily and are erased with every function call

Solidity auto deals with the variables storage type most of the times

Like state variables are auto storage type

And function variables are auto memory and disappear when function call ends

Sometimes you need to use this with arrays and structs

### More on Function Visibility

In addition to public and private solidity has two more visibility specifiers internal and external

||Public|External|Internal|Private|
|----|----|----|---|----|
|Same Contract| Yes | Yes | Yes | Yes |
|Inherited Contract| Yes | No | Yes | No |
|Outside the contract| Yes | Yes | No | No |

### Interface

- cannot have any functions implemented

- can inherit from other interfaces

- all declared functions must be external

- cannot declare a constructor

- cannot declare state variables

### Using an Interface

```solidity
contract InterfaceEx{
	function returnNum( uint _id) external returns( bool isEven );
}

contract UseInterface{
	uint data;
	InterfaceEx interfaceex = InterfaceEx();
	function getInfo( uint _num ) public returns( uint ){
		data = interfaceex.returnNum(_num);
	}
}
```
### Handling Multiple Return Values

Lets say your function is returning multiple values
```solidity
function returnMultiple( uint _id ) public returns( uint a, uint b, uint c){
	return (1, 2, 3);
}
```
```() => denotes tuple```

### if statement

Conditional statement used for enforcing some conditions that must be satisfied

```solidity
if ( condition ){
	//then do this
}
else{
	//do that
}
```
### Wrapping It Up

Lets summarise what we learnt in this lesson

```
Mapping - Map key values
Address - Address of account
Require - The condition that must be satisfied before executing function
msg.sender - Returns the address of the person/ contract that is calling the function
Inheritance - Achieved using is keyword
import - importing files into the program 
storage and memory - can relate to Hard Disk and RAM
function visibility - public, private, external, internal
interface - special type of contract with declared function i.e without definition
return multiple value - returned as tuple of values
if statement - to check for the conditions to satisfy
```

## `Day 3 Learnings`

### Immutability of Contracts

Once contract is deployed on Ethereum, it’s immutable, which means that it can never be modified or updated again.

The initial code you deploy to a contract is there to stay, permanently, on the blockchain. This is one reason security is such a huge concern in Solidity. If there's a flaw in your contract code, there's no way for you to patch it later. You would have to tell your users to start using a different smart contract address that has the fix.

### Ownable Contracts

`OpenZeppelin's Ownable contract`
OpenZeppelin is a library of secure and community-vetted smart contracts that you can use in your own DApps. 

`Constructors`: constructor() is a constructor, which is an optional special function that has the same name as the contract. It will get executed only one time, when the contract is first created.

`Function Modifiers`: Modifiers are kind of half-functions that are used to modify other functions, usually to check some requirements prior to execution. 

### onlyOwner Function Modifier

Modifiers are code that can be run before and / or after a function call.

Modifiers can be used to:

- Restrict access
- Validate inputs
- Guard against reentrancy hack
```solidity
modifier onlyEven(uint _num) {
    require( num % 2 == 0 );
    _;
}
 function getPower(uint _num) public onlyEven(_num) {
    power =  _num ** 2;
 }
```

### Gas
`Gas — the fuel Ethereum DApps run on`

How much gas is required to execute a function depends on how complex that function's logic is. Each individual operation has a gas cost based roughly on how much computing resources will be required to perform that operation (e.g. writing to storage is much more expensive than adding two integers). The total gas cost of your function is the sum of the gas costs of all its individual operations.

The creators of Ethereum wanted to make sure someone couldn't clog up the network with an infinite loop, or hog all the network resources with really intensive computations. So they made it so transactions aren't free, and users have to pay for computation time as well as storage.

When used directly `uint8, uint16, uint32` all require same gas but when used within struct they are packed by solidity to optimise gas requirement

```solidity
struct Packed{
	uint8 a;
	uint32 b;
	uint c;
}
```

will require less gas than

```solidity
uint8 a;
uint32 b;
uint c;
```
### Time Units

Solidity provides some native units for dealing with time.

The variable now will return the current unix timestamp of the latest block (the number of seconds that have passed since January 1st 1970). The unix time as I write this is 1642329321.

Unix time is traditionally stored in a 32-bit number. This will lead to the "Year 2038" problem, when 32-bit unix timestamps will overflow and break a lot of legacy systems. 

So if we wanted our DApp to keep running 20 years from now, we could use a 64-bit number instead — but our users would have to spend more gas to use our DApp in the meantime.

### Passing structs as arguments

Passing struct as a parameter to function which will have storage or memory access. 

### Public Functions & Security

public and external functions can be abused by the user, so using public/ external can be security problem so use internal as access specifier.

### More on Function Modifiers

Funtion modifiers can take parameters 

```solidity
modifier paraMeter(uint para){
	require(para >= 0);
	_;
}
```

`calldata` - special data location that contains function arguments, only available for external functions


### Saving Gas With `'View'` Functions

`view` functions don't cost any gas when they're called externally by a user.

This is because view functions don't actually change anything on the blockchain – they only read the data. So marking a function with view tells web3.js that it only needs to query your local Ethereum node to run the function, and it doesn't actually have to create a transaction on the blockchain (which would need to be run on every single node, and cost gas).

 If a view function is called internally from another function in the same contract that is not a view function, it will still cost gas. This is because the other function creates a transaction on Ethereum, and will still need to be verified from every node. So view functions are only free when they're called externally.

### Storage is Expensive

One of the more expensive operations in `Solidity` is using `storage`

This is because every time you write or change a piece of data, it’s written permanently to the blockchain. Forever! Thousands of nodes across the world need to store that data on their hard drives, and this amount of data keeps growing over time as the blockchain grows. So there's a cost to doing that.

In order to keep costs down, you want to `avoid writing data to storage except when absolutely necessary`. 

Sometimes this involves seemingly inefficient programming logic — like rebuilding an array in memory every time a function is called instead of simply saving that array in a variable for quick lookups.

### For Loops

Instead of using storage variables using for loop makes things less expensive.

```solidity
for( initialise; condition; increment/decrement){
	//do something here
}
```

## `Day 4 Learnings `

### Payable

### Visibility modifiers : when and where the function can be called from

We have seen the visibility modifiers before in this challenge

`public, external, internal, private`

### State Modifiers : which tell us how the function interacts with the BlockChain
||Read from Blockchain|Write to Blockchain|Fees required when called from Internal funtion|Called from External function|
|------|--------|---------|--------|---------|
|view|Yes|No|Yes|No|
|pure|No|No|Yes|No|
|payable|Yes|Yes|Yes|Yes|


### Withdraws
In the previous chapter we saw how to send ether to smart contract. That ether is stored in smart contract Ethereum account. So to get those ethers we have to write a withdraw function.

```solidity
 function withdraw() external onlyOwner {
    address payable _owner = address(uint160(owner()));
    _owner.transfer(address(this).balance);
  }
```

### Random number 

### Generating random number using keccak256
```solidity
uint randNonce = 1;
uint random = uint(keccak256(abi.encodePacked(now, msg.sender, randNonce))) % 100;
```

this will take current timestamp and msg sender account address, randNonce and encode it to random hash then we are converting it to uint and % by 100 which will give us number between 0-99.

```but this is not safe method to generate random number```

### So how do we generate random numbers safely in Ethereum?

1 Perfectly Decentralized Lottery-Style Non-Malleable Commitment:

- The Casino sets aside a reward for a random number
- Each user generates their own secret random number N
- Users create their commitment by hashing their N with their address: bytes32 hash = sha3(N,msg.sender)
note: steps 2 & 3 should be performed locally, in secret
- Users send their hash to the contract, along with ether greater than or equal in value to the value of the random number.
- Submissions continue for some number of blocks, or until sufficient participants have joined.
- Once the submission round has ended, the reveal round begins.

- Each user submits their random number N to the contract
- The contract verifies that the sha3(N,msg.sender) matches the original submission
- If the user does not submit a valid N in time, his deposit is forfeit.

- The Ns are all XOR'd together to generate the resulting random number.
- This number is used to determine which of the participants receives the reward. (N % numUsers)

## `Day 5 Learnings`

### ERC721 & Crypto-Collectibles

### Tokens on Ethereum
A token on Ethereum is basically just a smart contract that follows some common rules — namely it implements a standard set of functions that all other token contracts share

`ERC20 - Ethereum Request for Comment 20`
Since all ERC20 tokens share the same set of functions with the same names, they can all be interacted with in the same ways.

An ERC20 token contract keeps track of `fungible tokens`: any one token is exactly equal to any other token; no tokens have special rights or behavior associated with them. This makes ERC20 tokens useful for things like a medium of exchange currency, voting rights, staking, and more.

### ERC721 Standard, Multiple Inheritance
You can make a fungible token using ERC20, but what if not all tokens are alike? This comes up in situations like real estate or collectibles, where some items are valued more than others, due to their usefulness, rarity, etc. ERC721 is a standard for representing ownership of `non-fungible` tokens, that is, where each token is unique.

ERC721 is a more complex standard than ERC20, with multiple optional extensions, and is split across a number of contracts.

```solidity
contract ERC721 {
  event Transfer(address indexed _from, address indexed _to, uint256 indexed _tokenId);
  event Approval(address indexed _owner, address indexed _approved, uint256 indexed _tokenId);

  function balanceOf(address _owner) external view returns (uint256);
  function ownerOf(uint256 _tokenId) external view returns (address);
  function transferFrom(address _from, address _to, uint256 _tokenId) external payable;
  function approve(address _approved, uint256 _tokenId) external payable;
}
```

### Multiple Inheritance:

    Multiple contracts are used by the contract.

```solidity
contract C is A, B{
	
}
```

### balanceOf & ownerOf
```solidity
function balanceOf(address _owner) external view returns (uint256 _balance);	
```
This function simply takes an address, and returns how many tokens that address owns.

```solidity
 ownerOf(uint256 _tokenId) external view returns (address _owner);
 ```
 This function takes a token ID (in our case, a Zombie ID), and returns the address of the person who owns it.

### Refactoring

Remember, we're using the ERC721 token standard, which means other contracts will expect our contract to have functions with these exact names defined. That's what makes these standards useful — if another contract knows our contract is ERC721-compliant, it can simply talk to us without needing to know anything about our internal implementation decisions.

### ERC721: Transfer Logic

Note that the ERC721 spec has 2 different ways to transfer tokens:

```solidity
function transferFrom(address _from, address _to, uint256 _tokenId) external payable;
```
The token's owner calls transferFrom with his address as the _from parameter, the address he wants to transfer to as the _to parameter, and the _tokenId of the token he wants to transfer.
and

```solidity
function approve(address _approved, uint256 _tokenId) external payable;
```
the token's owner first calls approve with the address he wants to transfer to, and the _tokenID . 

The contract then stores who is approved to take a token, usually in a mapping (uint256 => address). Then, when the owner or the approved address calls transferFrom, the contract checks if that msg.sender is the owner or is approved by the owner to take the token, and if so it transfers the token to him.


### ERC721: Approve

Remember, with approve the transfer happens in 2 steps:

You, the owner, call approve and give it the _approved address of the new owner, and the _tokenId you want them to take.

The new owner calls transferFrom with the _tokenId. Next, the contract checks to make sure the new owner has been already approved, and then transfers them the token.

There is one more thing to do- there's an Approval event in the ERC721 spec. 

### Preventing Overflows

There are extra features we may want to add to our implementation, such as some extra checks to make sure users don't accidentally transfer their zombies to address 0 (which is called "burning" a token — basically it's sent to an address that no one has the private key of, essentially making it unrecoverable). 

### Contract security enhancements: Overflows and Underflows:

What's an `overflow`?

Let's say we have a uint8, which can only have 8 bits. That means the largest number we can store is binary 11111111 (or in decimal, 2^8 - 1 = 255).

```solidity
uint8 num = 255;
num++;
```

`so the num resets to 0 (11111111 + 1 = 1 00000000 = 00000000 )`

An underflow is similar, where if you subtract 1 from a uint8 that equals 0, it will now equal 255 (because uints are unsigned, and cannot be negative).

### Using SafeMath

To prevent this, OpenZeppelin has created a library called SafeMath that prevents these issues by default.

### A library is a special type of contract in Solidity. One of the things it is useful for is to attach functions to native data types.

```solidity
uint num = 200;
num.add(1);
num.sub(1);
num.mul(2);
num.div(2);
```

### Comments

The standard in the Solidity community is to use a format called natspec, which looks like this:

```solidity
/// @title A contract for basic math operations
/// @author SANSKRITI 💯💯😎💯💯
/// @notice For now, this contract just adds a multiply function
contract Math {
  /// @notice Multiplies 2 numbers together
  /// @param x the first uint.
  /// @param y the second uint.
  /// @return z the product of (x * y)
  /// @dev This function does not currently check for overflows
  function multiply(uint x, uint y) returns (uint z) {
    // This is just a normal comment, and won't get picked up by natspec
    z = x * y;
  }
}
```
`@title` and `@author` are straightforward.

`@notice` explains to a user what the contract / function does. @dev is for explaining extra details to developers.

`@param` and `@return` are for describing what each parameter and return value of a function are for.

Note that you don't always have to use all of these tags for every function — all tags are optional. But at the very least, leave a @dev note explaining what each function does.


## `Day 6 Learnings `

Ethereum network is made up of nodes, with each containing a copy of the blockchain. When you want to call a function on a smart contract, you need to query one of these nodes and tell it:

- The address of the smart contract
- The function you want to call, and
- The variables you want to pass to that function.

Ethereum nodes only speak a language called JSON-RPC, which isn't very human-readable. A query to tell the node you want to call a function on a contract looks something like this:
```solidity
{"jsonrpc":"2.0","method":"eth_sendTransaction","params":[{"from":"0xb60e8dd61c5d32be8058bb8eb970870f07233155","to":"0xd46e8dd67c5d32be8058bb8eb970870f07244567","gas":"0x76c0","gasPrice":"0x9184e72a000","value":"0x9184e72a","data":"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"}],"id":1}
```

`Infura` is a service that maintains a set of Ethereum nodes with a caching layer for fast reads, which you can access for free through their API. Using Infura as a provider, you can reliably send and receive messages to/from the Ethereum blockchain without needing to set up and maintain your own node.

`Metamask` is a browser extension for Chrome and Firefox that lets users securely manage their Ethereum accounts and private keys, and use these accounts to interact with websites that are using Web3.js.

```Note: Metamask uses Infura's servers under the hood as a web3 provider, just like we did above — but it also gives the user the option to choose their own web3 provider. So by using Metamask's web3 provider, you're giving the user a choice, and it's one less thing you have to worry about in your app.```

### Talking to contracts 
Web3.js will need 2 things to talk to your contract: its address and its ABI.

ABI stands for Application Binary Interface. Basically it's a representation of your contracts' methods in JSON format that tells Web3.js how to format function calls in a way your contract will understand.

When you compile your contract to deploy to Ethereum, the Solidity compiler will give you the ABI, so you'll need to copy and save this in addition to the contract address.

### Calling Contract Functions

Web3.js has two methods we will use to call functions on our contract: call and send.

call is used for view and pure functions. It only runs on the local node, and won't create a transaction on the blockchain.

send will create a transaction and change data on the blockchain. You'll need to use send for any functions that aren't view or pure.

MetaMask allows the user to manage multiple accounts in their extension.

We can see which account is currently active on the injected web3 variable via:
```solidity
var userAccount = web3.eth.accounts[0];
```
Because the user can switch the active account at any time in MetaMask, our app needs to monitor this variable to see if it has changed and update the UI accordingly

### What's a Wei?
A wei is the smallest sub-unit of Ether — there are 10^18 wei in one ether.

### Subscribing to Events

In order to filter events and only listen for changes related to the current user, our Solidity contract would have to use the indexed keyword

![complete](https://user-images.githubusercontent.com/67673060/150649569-fa874124-4c00-4534-b2df-6737b37487b7.PNG)

## Thank you for reading till end!
## Thank you Get into Web3 for this opportunity
## Keep Learning:)

