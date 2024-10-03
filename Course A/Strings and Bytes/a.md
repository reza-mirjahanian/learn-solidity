1.  Natively, there are no String manipulation functions.
2.  No even string comparison is natively possible
3.  There are libraries to work with Strings
4.  Strings are expensive to store and work with in Solidity (Gas costs, we talk about them later)
5.  As a rule of thumb: try to avoid storing Strings, use Events instead


Comparing two Strings
---------------------
```
  function compareTwoStrings(string memory _myString) public view returns(bool) {
        return keccak256(abi.encodePacked(myString)) == keccak256(abi.encodePacked(_myString));
    }
```


Strings vs Bytes
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Strings are actually arbitrary long bytes in UTF-8 representation. Strings do not have a length property, bytes do have that


Key Characteristics
-------------------

-   Strings are similar to arrays and byte arrays
-   Limited native string manipulation functions
-   Expensive to store on the blockchain
-   


**Setter Function for Strings:**

The key point here is that strings in function parameters must specify a data location (either memory or calldata), with memory being used in this case.
```
function setMyString(string memory newString) public {
    myString = newString;
}
```



String Manipulation
-------------------

-   Only native function: concatenation
-   No built-in string comparison
-   External libraries available for more complex operations
-   

