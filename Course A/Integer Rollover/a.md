### **Key Concepts:**

-   **Pre-0.8.0 Arithmetic Behavior:**

    -   In Solidity versions **prior to 0.8.0**, arithmetic operations (such as addition and subtraction) could result in **overflow** or **underflow** without throwing an error. This behavior is called **wraparound**.
    -   For example, decrementing an unsigned integer (uint) that is already zero would cause the value to "wrap around" to the maximum possible value instead of throwing an error.
-   **SafeMath Library:**

    -   To prevent overflow and underflow, developers commonly used libraries like **SafeMath**, which introduced additional checks (e.g., `require` statements) to ensure arithmetic operations did not exceed valid ranges.
    -   These libraries were widely used in the Ethereum ecosystem to ensure the safety of arithmetic operations.

* * * *

### **Changes in Solidity 0.8.0 and Beyond:**

-   **Checked Arithmetic:**
    -   Starting from **Solidity 0.8.0**, arithmetic operations are **checked by default**. This means that if an operation results in an overflow or underflow, the transaction will automatically **revert** (i.e., throw an error), preventing the wraparound behavior.
    -   This change makes arithmetic operations safer and eliminates the need for external libraries like SafeMath.
-   

**Reverting to Unchecked Arithmetic in Solidity 0.8.x:**

-   If a developer wants to revert to the old behavior (i.e., wraparound), they can use the **`unchecked` block**.
-   Wrapping the arithmetic operation inside an `unchecked {}` block will bypass the built-in checks and allow the operation to wrap around as it did in pre-0.8.0 versions.
-   

```
unchecked {
    // Arithmetic operations inside this block will not be checked
    myUint--;
}
```