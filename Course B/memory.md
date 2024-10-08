

Without the  _memory_  keyword, Solidity tries to declare variables in  _storage_.

Lead Solidity dev chriseth: “You can think of storage as a large array that has a virtual structure… a structure you cannot change at runtime - it is determined by the state variables in your contract”.

That is, the structure of storage is set in stone at the time of contract creation based on your contract-level variable declarations and cannot be changed by future method calls. BUT -- the contents of that storage can be changed with sendTransaction calls. Such calls change “state” which is why contract-level variables are called “state variables”. So a variable  `uint8 storage var;`  declared at the contract level can be changed to any valid value of uint8 (0-255) but that “slot” for a value of type uint8 will always be there.

If you declare variables in functions without the  _memory_  keyword, then solidity will try to use the storage structure, which currently compiles, but can produce unexpected results.  _memory_  tells solidity to create a chunk of space for the variable at method runtime, guaranteeing its size and structure for future use in that method.

_memory_  cannot be used at the contract level. Only in methods.

See the  [the entry "What is the memory keyword? What does it do?"](https://docs.soliditylang.org/en/v0.3.3/frequently-asked-questions.html#what-is-the-memory-keyword-what-does-it-do)  in the FAQ. I quote it here:

> The Ethereum Virtual Machine has three areas where it can store items.
> 
> The first is “storage”, where all the contract state variables reside. Every contract has its own storage and it is persistent between function calls and quite expensive to use.
> 
> The second is “memory”, this is used to hold temporary values. It is erased between (external) function calls and is cheaper to use.
> 
> The third one is the stack, which is used to hold small local variables. It is almost free to use, but can only hold a limited amount of values.
> 
> For almost all types, you cannot specify where they should be stored, because they are copied everytime they are used.
> 
> The types where the so-called storage location is important are structs and arrays. If you e.g. pass such variables in function calls, their data is not copied if it can stay in memory or stay in storage. This means that you can modify their content in the called function and these modifications will still be visible in the caller.

There are defaults for the storage location depending on which type of variable it concerns:

-   state variables are always in storage
-   function arguments are always in memory
-   local variables of struct, array or mapping type reference storage by default
-   local variables of value type (i.e. neither array, nor struct nor mapping) are stored in the stack
-   
------------


`memory`  and  `calldata`  (as well as  `storage`) are keywords that define the data area where a variable is stored. To answer your question directly,  `memory`  should be used when declaring variables (both function parameters as well as inside the logic of a function) that you want stored in memory (temporary), and  `calldata`  _must_  be used when declaring an  **external**  function's  **dynamic**  parameters.

The easiest way to think about the difference is that  `calldata`  is a non-modifiable, non-persistent area where function arguments are stored, and behaves mostly like memory.

----------

Breaking this down, let's first look at  `memory`.  `memory`'s lifetime is limited to a function call and is meant to be used to temporarily store variables and their values. Values stored in  `memory`  do not persist on the network after the transaction has been completed. Some notable implementation details about memory are as follows:

-   It can be used for both function declaration parameters as well as within the function logic
-   It is mutable (it can be overwritten and changed)
-   It is non-persistent (the value does not persist after the transaction has completed)

`calldata`  is very similar to memory in that it is a data location where items are stored. It is a special data location that contains the function arguments, only available for external function call parameters. From the Solidity  [docs](https://solidity.readthedocs.io/en/v0.5.11/types.html?highlight=memory#data-location):

> Calldata is a non-modifiable, non-persistent area where function arguments are stored, and behaves mostly like memory.

This is the cheapest location to use,  but it has a limited size. In particular, that means that functions may be limited in their number of arguments.[1](https://hackernoon.com/working-with-strings-in-solidity-c4ff6d5f8008)  Notable implementation details about  `calldata`  are as follows:

-   It can  **only**  be used for function declaration parameters (and not function logic)
-   It is immutable (it can't be overwritten and changed)
-   It  **must**  be used for dynamic parameters of an external function
-   It is non-persistent (the value does not persist after the transaction has completed)

----------

The following is a  **valid**  example of code using  `memory`  and  `calldata`:

```php
pragma solidity 0.5.11;

contract Test {
    
    string stringTest;
    
    function memoryTest(string memory _exampleString) public returns (string memory) {
        _exampleString = "example";  // You can modify memory
        string memory newString = _exampleString;  // You can use memory within a function's logic
        return newString;  // You can return memory
    }
    
    function calldataTest(string calldata _exampleString) external returns (string memory) {
        // cannot modify _exampleString
        // but can return it
        return _exampleString;
    }
}

```

----------


One good way to think about the difference and how they should be used is that  `calldata`  is allocated by the caller, while  `memory`  is allocated by the callee.