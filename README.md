# 6 Days of Solidity

### Day 1 Making the Zombie Factory

In NutShell it's all about the basics of whole solidity programming language and I will bet you will get more excited to learn more in this Course.
    
  CHAPTER 1: LESSON OVERVIEW:
    
    In Starting you will get to know that what is our main mission and at the end what you want to achieve. 
    Basically we are going to make Zombiefactory in which zombie get created so we will be going to implement 
    such feature so that user can easily make their own choice of Zombie.
    
  CHAPTER 2: Contracts
   
    Contracts is nothing just the piece of code which get migrated into blockchain and once it get migrated into 
    blockchain it become immutable.
    Do take care of this line as well before writing solidity. It is just kind of compiler version. 
    pragma solidity >=0.5.0 <0.6.0; 
   
  CHAPTER 3: State Variables & Integers  
    
    State variables are permanently stored in contract storage. This means they're written to the Ethereum blockchain.    
    Unsigned Integers: (uint) It is non-negative integers.
    Signed Integers: (int) for any integers in solidity.
    
  CHAPTER 4: Math Operations
   
    Addition Operation => (3 + 2) >= 5
    Subtraction Operation => (3 - 2) => 1
    Multiplication Operation => (3 * 2) => 6
    Division Operation => (3 / 2)  => 1 (Gives the Quotient value)
    Modulo Operation => (3 % 2) => 1 (Gives the Remainder value)
    Exponentiation Opeerartion => (2 ** 3) => 8 (Gives the Power value)
    
  CHAPTER 5: Structs
  
    Struct is similar to that we had learnt in C,C++ nothing special here too. 
    It allows us to create our data Type in simple terms.
    In this Course we are using beacuse it will hold the basic charcteristic of our Zombie. (Initially the name and DNA).
    
  CHAPTER 6: Arrays  
    
    Array is a common Data Structure in every Programming language.Everyone know how it works and its feature,its useCase.
    
    In Solidity also two types of Array are present:
    Fixed Size Array -> As name suggest we have to give the size before hand.
    Dynamic Array -> Again name Suggest we don't have to give the actual size before hand, it can keep growing.
    
    Public Arrays - It is nothing but we just give the array scope by public means we can access it from any contract,
    Also by default it will create its getter method by solidity.
    
    Declaration of array
    Fixed Size Array = uint[5] fxd;
    Dynamic Array = uint[] dyn;
    
  CHAPTER 7: Function Declarations
  
    Function is used in programming to write better cdes. It also helps to remove redundancy in our code.
    
    Decalaration:
       
       function  nameOfFunction( string _str, uint _y) public {
       
                //write code here
        }  
    
    Little About Argument & Parameter that are used in function.
    
    In function declaration we pass Parameters.It can be used in two ways:
    
        1) Pass by Value => It means it will create a new copy of what you are passing as Argument while calling 
           the function. In this it will not affect your original argument.
        2) Pass by reference => It means it will not create any copy,it just use the address of argument that 
           you are passing.while calling the function.But It will manipulate your original argument.
                 
           We use memory for pass by Value in Solidity.
           
           Example:
           function exmaple(string memory _name, uint memory _age) public {
           }
            
    In function call we pass argument. example: nameofFunction("Aman" , 20); 
    
    
  CHAPTER 8: Working With Structs and Arrays
    
    In this Lesson you will be goin to use struct and array together. It is not complicate that it looks initially.
    
    -> You know how to create Array.
    -> you know how to make struct.
    -> Now just change the data Type of Array with struct name. In this way that array will become the struct Array to hold
       Zombie feature such as name,dna.
       
    To Insert into Array take help of push() function it come handy with array.

  CHAPTER 9: Private / Public Functions
    
    Private Function -> It will be used only in that contract where it defined.
    Public Function ->  From any where we can access it.
    
    Be Cautiuos with public function beacuse it causes vulnerabilities issue in our code. So, better use Private instead Public. 
    
  CHAPTER 10: More on Functions:
     
    Return Values: It is completely depend upon the return type of function,if function type is string then it will return string only.
    
       Example: 
       
       uint numbePlate = 5955;      
       function _taxiNumber() private returns (uint memory)
       {
            return numberPlate;
       }
    
    Function Modifiers: So, It is actually new to me and very suprising to see that function also have modifiers.
        
        There is two types of Function Modeifiers we have in Solidity.
        
        View - In View it doesn't change the function at all it just allow us to look inside function.
            
            Example:
            
            string name = "Aman";
            function test( --- here we are not passing any parameter ---) private view returns (string memory)
            {
                return name;
            }
            
        Pure - But using Pure we can modify our function for sure but with our parameter only. it will not access any 
        other elemnet in our code.
        
            Example:
           
            function test(uint _a,uint _b) private view returns (uint)
            {
                return a + b;
            }
            
        Note: It may be hard to remember when to mark functions as pure/view. Luckily the Solidity compiler is 
        good about issuing warnings to let you know when you should use one of these modifiers.
           
    
  CHAPTER 11 & 12: Keccak256 and Typecasting
        
        Keccak256 is just the random hashing genrator.For Random generation of DNA for our Zombies.
        
            Declaration Example:
                keccak256(abi.encodePacked("aaaab"));
        
        TypeCasting we know changing the data type in between our code of any variable as per our useCase.
            
            Example:
                bytes eg;           
                uint test = uint(eg);
                
        At last In this will pretty much completed our lesson just put it all together to make whole code work.Hurray!!!             
    
  CHAPTER 13: Events
  
        Events are a way for your contract to communicate that something happened on the blockchain to your app front-end, 
        which can be 'listening' for certain events and take action when they happen.
        
            Declaration example:
            
                event IntegersAdded(uint x, uint y, uint result);
                emit IntegersAdded(_x, _y, result);
        
    
  CHAPTER 14: Web3.js
          
          In this Chapter you will get a little glimpse of web3.0, how it is going to work.
          Ethereum has a Javascript library called Web3.js.
          
          Now In Chapter 15 you make your own Zombie and share with friends.

### Day 2 Zombies Attack Their Victims

In this Module we are going to add Multiplayer feature as well as adding some extra feature to make our Zombie army appearnace
little different.

   CHAPTER 1: Lesson 2 Overview:

     Zombie Feeding : To make our Zombie being more effective we will do like if zombie infect the other person it will 
                      turn into the zombie as well.

                      Technically speaking we will calculate the another DNA for the new zombie which will be nothing 
                      but the average of perevous zombie dna and host dna.

   CHAPTER 2: Mappings and Addresses:

       In this we learnt about addresses and Mapping in Blockchain.

       Address: It is like the bank account number everyone have a bank account they do transaction to this.
                Simlilarly here to , the owner have its own address through which transaction can be done and uniquely 
                identifies the person.

                For example: If you ever send crypto to any blockchain wallet, there you see the address which is used 
                for transaction.

       Mapping: In Simple terms if you ever used any Programming language like Java,Phython there you seen something 
                called Hashmap or Dictionary. Here to in Solidity we have Mapping which is almost same, Key Value Pair 
                where Key will be always unique.

       We are using Mapping In our project to store the address of owner with some value to it which will be the ZombieID.

   CHAPTER 3: Msg.sender  

       To find out the owner address we generally use msg.sender variable which global variable in Solidity which gives 
       the current owner address. With the use of msg.sender as a key in our mapping which tell us the address of owner 
       and value will be ZombieID,it tell us who own that zombie.

   CHAPTER 4: Require

       Require is quite useful for verifying certain conditions that must be true before running a function.
       We will be using the require to check whether the current user not gnereate unlimited zombie so, it will stop that 
       thing.

       We will check if the current User count of Zombie will be zero then allow to generate army.

   CHAPTER 5 & 6: Inheritance & Import

       Inheritance provide the code reusibilty feature. Also it will inherit the properties of its parent contract.
       In this way we will reduce or organize our code more efficiently.

       It is basically Objected Oriented Programming Feature.

       We will be making another contract which will be take all the information about Zombie feeding.Now after making that 
       contract.We have to use the property of our earlier contract which is ZombieFactory. So, to use that will use import 
       keyword in our child contract.

       Similar to importing Modules in python.Think in this way.
    
  CHAPTER 7: Storage vs Memory (Data location)
  
    Storage refers to variables stored permanently on the blockchain. 
    
    Memory variables are temporary, and are erased between external function calls to your contract. 
    Think of it like your computer's hard disk vs RAM.
    
  CHAPTER 8: Zombie DNA
    
    The formula for calculating a new zombie's DNA is simple: the average between the feeding zombie's DNA and the 
    target's DNA.
    
    Using thsi we will Calculate:
    uint newZombieDna = (zombieDna + targetDna) / 2;
    
  CHAPTER 9: More on Function Visibility
  
    Internal is the same as private, except that it's also accessible to contracts that inherit from this contract.
    External is similar to public, except that these functions can ONLY be called outside the contract — they can't 
    be called by other functions inside that contract.


  CHAPTER 10: What Do Zombies Eat?
    
    CryptoZombies love to eat... CryptoKitties!
    In order to do this we'll need to read the kittyDna from the CryptoKitties smart contract. We can do that because 
    the CryptoKitties data is stored openly on the blockchain.
    
    By including this interface in our dapp's code our contract knows what the other contract's functions look like, 
    how to call them, and what sort of response to expect.Now let's declare our interface for the CryptoKitties contract.
    
  CHAPTER 11: Using an Interface

    Continuing our previous example with NumberInterface, once we've defined the interface as:

    contract NumberInterface {
      function getNum(address _myAddress) public view returns (uint);
    }
    
  CHAPTER 12: Handling Multiple Return Values
  
    This getKitty function is the first example we've seen that returns multiple values. Let's look at how to handle them:          
    
  Bonus: Kitty Genes

    Let's make it so zombies made from kitties have some unique feature that shows they're cat-zombies.
    To do this, we can add some special kitty code in the zombie's DNA.

    If you recall from lesson 1, we're currently only using the first 12 digits of our 16 digit DNA to determine 
    the zombie's appearance. So let's use the last 2 unused digits to handle "special" characteristics.

    We'll say that cat-zombies have 99 as their last two digits of DNA (since cats have 9 lives). 
    So in our code,we'll say if a zombie comes from a cat, then set the last two digits of DNA to 99.

### Day 3 Advanced Solidity Concepts

In this Module we will see the Actual Blockchain Implementation, why is it so have such a huge hype behind the 
smart contract and all the other cool stuffs.

  CHAPTER 1: Immutability of Contracts
    
    We have heard lot about security in blockchain so how it looks.
    -> First, thing if we deployed the smart contract in blockchain then it can't be further modified it will 
       set once for all.
    -> So,If you find the bug in your contract after you had deployed, then you have to write new smart contract 
       by fixing that issue and deployed it again, in this way it become immutable and more secure than any other 
       API or CODE.
    
    What is our Concern in this Project?
    
    We had hardcoded the address of kittysmart Contract so we have to take care for future option what if their 
    address get corrupted,or give any other faults later on we will not be able to solve that issue once we deployed 
    the contract, so we will use the function to write the address instead of hardcoding it.
    
  CHAPTER 2 & 3: Ownable Contracts , onlyOwner Function Modifier
  
    In Chapter-1 we have created the function which is external so anybody can alter the address other than the 
    original owner.So we have to prevent that issue. To do that we will be using OpenZeppelin's Ownable contract 
    in our dapp.
    
    In Chapter 3, we are just adding onlyOwner modifier after external keyword in function that we are working 
    such that,externally after the smart contract get deployed only owner have responsibility to alter the address. 
    But it is also suspect the security of dapps then how it can be decentralised,So we have to take a look over the 
    code such that owner itself in future doesn't have a backdoor to trick the client.
    
  CHAPTER 4: Gas
    
    Gas is basically a fee which is taken by ethereum to run the computation of your smart contract.So, every time a 
    user call the function it have to paid that amount, also it is not fixed depends upon the number of operation as 
    well as storage. So, it will be  very necessarily to make code optimization at gret levl, beacuse it' all money 
    that will go.
    
    To minimze the gas fee little bit use struct for variables to declared,also in clustered manner.
    
    eg. 
        struct number{
            uint8 a;
            uint8 b;
            uint32 x;
            uint32 y;
        }
    
    Now we will be doing the same,also we get to know why there is so much structs all around the contracts.
    
    We will adding two more feature which is level & readytime, declared in struct becuase now we know why!!!
    
  CHAPTER 5: Time Units
   
    In this Chapter we are implementing the cooldown time for zombie to make our game more intereseting. So every time 
    if zombie feed or attack he has to wait for some time which is here called as cooldown time, we are going to implement 
    using now keyword which the unix timestamp according to that we will be going to update the createzombie function 
    also, we will push in the zombie array two new feature which is level and cooldowntime.
    
  CHAPTER 6 & 7: Zombie Cooldowns,Public Functions & Security
    
    In this chapter we are making two function which will take care of zombie cooldown. We are calculating readyTime 
    in function triggerCooldown after that, we are checking that readytime, it return true when it is less than the value 
    now or false otherwise. Then, we change the public to internal scope due to security reason in function feedAndMultiply.
    Then call the function triggerCooldown and isReady to set as require.
    
  CHAPTER 8 & 9: More on Function Modifiers,Zombie Modifiers
    
    We are going to make our own modifier to set level for game, so that in each level new abilities would come play into game.
    We can pass argument into modifiersa and call them in another functions argument.
    
    Point to remeber:
    At last line add _; in code so that it will call the rest of the function.
    
    Now, we will be adding some functionalities for user so, that if they level up their zombie they get some kind of 
    reward or advantage.
    1) For level2 or above they can change their name.
    2) Level 20 above, they can customised the dna of Zombies.
    
    Important:
    calldata: It is similar to memory but is used only in case of external function.
    
    Then, Simply make two function and using modifier abovelevel we set the abilities that user can do at certain level 
    which is 2 and 20 in this case.
  
  CHAPTER 10: Saving Gas With 'View' Functions
  
    At last we have to see that how many zombies that user have in his/her account. We are going to
    implement that function here to view the zombie Army.
    
    Important:
    1.) One User calls the View function then, it doesn't cost any gas fee, because it is not manipulating blockchain.
    2.) But, if we call internally then definitely it will cost the gas fee.So view functions are only free when they're 
        called externally.
    
  CHAPTER 11 & 12: Storage is Expensive, For Loops
  
    Storage in blockchain is really expensive. So to avoid that we are using the memeory with array because it is the only option
    to reduce the cost, because everytime we call the function and if it is storage then it will be huge ammount to be paid as fee.
    
    Point to Note:
    -> Memory array have fixed size rather than storage array.
    
    We are using for loop to iterate over all the zombies that user have. It is Simple for loop which tracks the count of zombie
    and at every index we are putting the zombie count;
    
    
    
  End.............................
    
    
### Day 4 Zombie Battle System

In this Module we will be Implementing the battle System of Zombies

  CHAPTER 1: Payable
    
    To Call a function it require some fee, so now we are going to implement that fee part in our game too, without that it
    will not be different application than normal application in market.
    
    Normal API don't send money in their function call but it happen in ethereum or say blockchain world.
    
    Points to Note:
    1) We will check first whether the fee that is sent is sufficient enough to call the function or not.
    2) The function who transact will have the keyword payable otherwise, it won't be able to carry the process forward,it will reject.
    3) msg.value will hold the fee of user while calling the function.
    
    We are adding the feature to level up the zombies by paying fee, this how we monitized from game
    
 CHAPTER 2: Withdraw
    
    Now, we are going to implemnt the feature that extract the ether from contract address to whomsoever I want.
    
    Point to note:
    -> We are making one function that will set the fee in future as well beacuse of price of Ether is booming, so 0.001 will be much
       expensive in future.
    -> We add the whole code of withdraw.
      
 CHAPTER 3 & 4: Zombie Battles & Random Numbers
   
    Creating new file and contract for zombie Attack which is inherr=iting the property of ZombieHelper contract. 
    
    In Solidity random number generation is actuualy a very hard task, we are just use keccak256() hash function for
    practical, but in real life it is harder to thought such a randomNumber that can't be break by thousands of nodes that are compete
    to solve the block.
      
   
 CHAPTER 5: Zombie Fightin'
 
    Our zombie battles will work as follows:

    -> You choose one of your zombies, and choose an opponent's zombie to attack.
    -> If you're the attacking zombie, you will have a 70% chance of winning. The defending zombie will have a 
       30% chance of winning.
    -> All zombies (attacking and defending) will have a winCount and a lossCount that will increment depending on the 
       outcome of the battle.
    -> If the attacking zombie wins, it levels up and spawns a new zombie.
    -> If it loses, nothing happens (except its lossCount incrementing).
    -> Whether it wins or loses, the attacking zombie's cooldown time will be triggered.
    
    This will be the whole architecture of our zombie battle.
    

CHAPTER 6,7,8: Refactoring Common Logic, Back to Attack!
        
        We are removing the redunndacy from our code by using modifiers. which is to check everytime the owner address.
        We just make the function that will predict the outcomes of battle.
        
   
CHAPTER 9: Zombie Wins and Losses
      
      We will be going to add the functionality of leaderboard game whic tell how much game won or loss. Implementing in our 
      struct data type for simplicity.
      
      Adding two variables of uint16 
      -> winCount
      -> lossCount
 
CHAPTER 10 & 11: Zombie Victory, Zombie Failure

       If winCount is less than attackVictoryProbability = 70,then it wins.
       -> increase the level of Zombie.
       -> increase the lossCount of enemy
       -> Increase the winCount.
       
       The loser:
       -> Increase the  enemy winCount.
       -> Increase the lossCount.
       -> Call the triggerCooldown function , so it will rest for some time till next battle.
   
   

END.....................................................



### Day 5 ERC721 & Crypto-Collectibles

In this Module we will be going to add feature of Collectibles like NFT , in which you can give your zombies to your friend 
and family member too.

  CHAPTER 1: Tokens on Ethereum
    
    Tokens : In Ethereum it a smart Contract that follows set of rules, so that it can interact with other token in same manner.
    It uses mapping to know which address have how much token in it.
    
    ERC20 token V/S ERC721 token
    
    ERC20 token are divisible token which means any part of 1 token can be used.
    They will be more useful in dealing witch Currency.
    They Can be interchange with the other token, such as Exchange Companies do like Binance, WazirX,etc.
    
    Example: 1 Bitcon,0.00000010 btc ,0.0000010 all possible 
    
    ERC721 aren't divisible that we want this feature to implement in our game.
    Also they aren't interchangeble,It will be unique and non-divisible.
    Using ERC721 we don't need to implement auction or escrow logic.
    
  
  CHAPTER 2: ERC721 Standard, Multiple Inheritance
  
    We will be implementing some Standard ERC721 methods.
    
    How to inherit Multiple contract.
    We can do that simply by just using the comma.
    Example :
        contract A is B,C;
        
    Now we will just import the erc721 contract into our contract file and we will be implmenting the methods one by one. 
  
  CHAPTER 3: balanceOf & ownerOf
  
    Ready to implement the methods of ERC721 start with.
    
    balanceof -> This function take argument as an address of User and return how many tokens it possess, in our case token 
                 implies Zombies.
                 
    owner of -> It takes argument as token Id and return the address of owner who have that token. In our case token Id implies 
                to Zombie ID.

  CHAPTER 4: Refactoring
  
    We have change the modifier na ownerOf in contract Zombiefeeding.sol because it will cause error if we use ownerOf method 
    of ERC721.To avoid that we have to change our implmentation part, beacise ERC721 have standard practice they dont't care about 
    our internal implmentation. We can't change them.

  CHAPTER 5 , 6 , 7 & 8: ERC721: Transfer Logic,ERC721: Transfer Cont'd , ERC721: Approve
  
    Transfer Logic:
    
      First way to do that is using transferFrom() function it will take three argument which is address of sender , address 
      of recipient and token ID what you want to send. This function will call by tokenOwner.
      
      - Second way is to implement the approve() function followed by transferFrom() function. tranferFrom() will be same as it is.
      - In approve() function it will ask for two argument which is recipient address and tokenID he wants to send then the
        owner will call transferFrom() function.
      
      Now will just tranfer the zombie to recipent address and change the owner address associated with _to address 
      which is again recipient address.
      
    -> Now we will be going to make sure that only owner/approved address could transfer so now to check owner it 
       is simple. for approved address we have to make mapping of uint to address which will take care of approval 
       address if any of two will be true will call the transfer function.
       
    -> We will be filling out the approval mapping that we created. We will first chcek in approved method that it 
       have modifier onyOwnerOf, so that only owner can call this approved method, after that simply insert the address 
       of approved owner.
       
    -> At last throw emit Approved so that it can reflect into frontend as well.

  
  CHAPTER 9: Preventing Overflows
  
    We have implemnted the Transfer Logic but we have to prevent some corner cases as well, So that User accidentally not able 
    to transfer the tokens. For eg. address like 0 which is also called buring address.
    
    So to avoid that.
    
    Overflow-> Suppose we have (uint8) data type which store  8 bit only in binary 11111111,in decimal 2^8 -1 =255.
               For Example: uint8 num = 255;
                            num++;
                            
                            It will print 0, because it overflow the data type value.
                            
    Underflow-> Works in similar manner suppose we have uint8 which is unsigned Integer it means that it cannot be negative.
               For Example: uint8 num = 0;
                            num--;
                            
                            It will Print 0 Cause Underflow error beacuse it must be positive.
    
    We are using uint256 which is much have biggest data tyoe value. 2^256 -1.
    
    Solution: To use Library called safeMath from OpenZeppelin it will take care of all Overflows and 
              Underflows or many faults.
    
    Library is just a smart Contract through which we can take help. 
    Example to use library " using SafeMath for uint256".
  
  
  CHAPTER 10: SafeMath Part 2
    
    To Implement we use Librray keyword that gives the featire of using statement.
    Also it usses assert keyword to prevent ups and down.
    Assert is similar to require instead ,require efund the gas if the function fails.
    But assert will not refund so try to use require, only use assert when somenthing is extremely fishy.
    
    In this way will be replacing all increment and decremnt operation with add() and sub() function.
  
  CHAPTER 11 & 12: SafeMath Part 3,SafeMath Part 4
    
    We Use the library SafeMath for uint which uint256 to prevent from overflow and underflow.
    But we also have uint16,uint32 data types so we have to make two mre safemath library for this data type as Well.
    
    Then We just replace all the increment and decrement operation with add() and sub() functions.  
  
  CHAPTER 13: Comments
  
    In Programming Comments play an vital role.It Nourish the Code also make it more readable.
    
    Single Line Comment:->  We use two slash which is //
    Multilen Comment:-> We use this /*   */
     
  
  END.................................................................


### Day 6 App Front-ends & Web3.js

  CHAPTER 1: Intro to Web3.js
  
  
  CHAPTER 2: Web3 Providers
  
  
  CHAPTER 3: Talking to Contracts
  
  
  CHAPTER 4: Calling Contract Functions
  
  
  
  CHAPTER 5: Metamask & Accounts
  
  
  CHAPTER 6: Displaying our Zombie Army
  
  
  CHAPTER 7: Sending Transactions
  
  
  
  CHAPTER 8: Calling Payable Functions
  
  
  
  CHAPTER 9: Subscribing to Events

