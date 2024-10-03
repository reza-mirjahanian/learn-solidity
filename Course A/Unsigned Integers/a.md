### **Important Notes**

-   **Integer Overflow and Underflow**:
    -   In older versions of Solidity, exceeding the maximum or minimum value of an integer would cause a **rollover** (e.g., `255` would roll over to `0` for a `uint8`).
    -   In newer Solidity versions, this behavior has been changed, and exceeding the limits will now **revert** the transaction, preventing rollovers.

2.  **Gas Optimization**:

    -   Assigning a default value explicitly (like `0` for `uint`) **increases gas costs**. If the default value is sufficient, it's better to leave the variable uninitialized to save on gas.
    
3. **Rounding with Integers**

   -  Integers in Solidity are always rounded down! If we divide e.g. 100 / 101 = 0.990... but in Solidity the result will be 0. Integers in Solidity are actually *cut off* (not even rounded), in other words *always* rounded down.

### **Key Concepts**

-   **Integers and Unsigned Integers**:

    -   Both are **whole numbers** without decimal points.
    -   **Signed integers** can hold both negative and positive values.
    -   **Unsigned integers** only hold non-negative values, ranging from **0 to a large positive number**.
-   **Range**:

    -   Unsigned integers range from **0 to 2^256 - 1**.
    -   Signed integers range from **\-2^128 to 2^128 - 1**.

* * * *

### **Examples and Use Cases**

1.  **Defining Unsigned Integers**:

    -   Example of defining an unsigned integer (`uint`) in Solidity:
        ```angelscript
       
        uint public myUint;
        
        ```

    -   By default, the value of `myUint` is **0** if not initialized.
    -   You can also initialize it with a specific value:
        ```abnf
       
        uint public myUint = 100;
        
        ```


3.  **Setter Function**:

    -   A function to set the value of `myUint`:
        ```csharp
       
        function setMyUint(uint _myUint) public {
            myUint = _myUint;
        }
        
        ```

4.  **Uint256 Size**:

    -   `uint` is an alias for `uint256`, which can store values from **0 to 2^256 - 1**, a very large number.
    -   This is much larger than JavaScript's maximum integer size, which is why **Web3 projects** may use libraries like **BigInt** or **BigNumber** to handle large numbers.

* * * *

### **Smaller Unsigned Integers**

-   Solidity allows the use of smaller unsigned integers, such as `uint8`, `uint16`, `uint32`, etc., which can save on **storage and gas costs**. However, using smaller types can lead to **side effects** if the maximum space is exceeded.

-   **Example**:

    -   Defining a `uint8`:
        ```angelscript

        uint8 public myUint8;
        
        ```

-   **Incrementing a uint8**:

    -   A function to increment `myUint8`:
        ```csharp
        
        function incrementUint8() public {
            myUint8++;
        }
        
        ```

    -   If `myUint8` reaches its maximum value (**255** for `uint8`), the transaction will **fail** and revert, as the maximum value cannot be exceeded.

* * * *

### **Signed Integers**

-   Signed integers (`int`) allow for both **negative and positive** values.

    -   Example of defining a signed integer:
        ```abnf
        
        int public myInt = -10;
        
        ```

-   **Incrementing and Decrementing**:

    -   You can increment or decrement signed integers, moving between negative and positive values.
    -   If you try to decrement an unsigned integer below zero, the transaction will **fail** because unsigned integers cannot hold negative values.

* * * *

### **Arithmetic Operations**

-   Solidity supports various arithmetic operations:
    -   **Addition** (`+`)
    -   **Subtraction** (`-`)
    -   **Multiplication** (`*`)
    -   **Division** (`/`)
    -   **Modulo** (`%`)
    -   **Exponentiation** (`**`), e.g., `2 ** 4` results in `16`.

* * * *

