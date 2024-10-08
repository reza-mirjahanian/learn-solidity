
> Data location must be  `memory`  or  `calldata`  for parameter in function, but none was given.

That is because of the new requirement to be explicit when using  [reference types](https://solidity.readthedocs.io/en/v0.7.4/types.html#reference-types), such as arrays. Also  `memory`  and  `calldata`  are now allowed in all functions regardless of their visibility.

A rewrite would look something like this:

```csharp
pragma solidity >=0.8.13;

contract ExternalPublicTest {
    function foo(uint[20] memory a) public pure returns (uint){
         return a[10]*2;
    }

    function bar(uint[20] calldata a) external pure returns (uint){
         return a[10]*2;
    }    
}

```

As a side note, you can decode  `calldata`  variables into  `memory`  but not the other way around.