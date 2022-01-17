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
        
In this Module we are going to add Multiplayer feature as well as adding some extra feature in creating Zombie army.
  
  CHAPTER 1: Lesson 2 Overview:
    
     Zombie Feeding :  When a zombie feeds, it infects the host with a virus. The virus then turns the host into a new zombie that joins your army. 
                       The new zombie's DNA will be calculated from the previous zombie's DNA and the host's DNA.
        

    
  CHAPTER 2: Mappings and Addresses
  
    Addresses: The Ethereum blockchain is made up of accounts, which you can think of like bank accounts. An account has a balance 
               of Ether (the currency used on the Ethereum blockchain), and you can send and receive Ether payments to other accounts, 
               just like your bank account can wire transfer money to other bank accounts.
   
  
    Mapping:   A mapping is essentially a key-value store for storing and looking up data. In the first example, the key is an 
               address and the value is a uint, and in the second example the key is a uint and the value a string.
 
   
  CHAPTER 3: Msg.sender  
    
    
  CHAPTER 4: Require
   
    
  CHAPTER 5: Inheritance
  
    
  CHAPTER 6: Import  
    
  CHAPTER 7: Storage vs Memory (Data location)

  CHAPTER 8: Zombie DNA
  
     
    
  CHAPTER 9: More on Function Visibility


  CHAPTER 10: What Do Zombies Eat?

    
  CHAPTER 11: Using an Interface

           
    
  CHAPTER 12: Handling Multiple Return Values
          
    
  Bonus: Kitty Genes
  

        
    
  WRAP UP



### Day 3 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 4 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 5 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### Day 6 Learnings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
