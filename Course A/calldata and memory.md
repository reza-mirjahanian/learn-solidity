# Comparison: `calldata` vs `memory` in Solidity

| Feature                    | `calldata`                                | `memory`                                  |
|----------------------------|-------------------------------------------|-------------------------------------------|
| **Definition**              | A non-modifiable, temporary location where function arguments are stored. | A temporary, modifiable location used to store variables during function execution. |
| **Mutability**              | Immutable (cannot be modified).           | Mutable (can be modified within the function). |
| **Persistence**             | Data exists only for the duration of the external function call. | Data exists only during the function execution and is discarded afterward. |
| **Gas Cost**                | Cheaper than `memory` for large data inputs because no copying occurs. | More expensive for large data structures since data is copied into memory. |
| **Usage**                   | Used primarily for function inputs in external functions to avoid unnecessary copying. | Used for variables that need to be modified or for internal function arguments. |
| **Storage Location**        | Data is passed by reference (no copying) and is stored directly in the calldata. | Data is passed by value (copied) and stored in memory. |
| **Typical Use Cases**       | External function parameters, especially for large arrays or structs. | Internal function parameters, temporary variables, or data that needs to be modified. |
| **Example Declaration**     | `function foo(uint[] calldata arr) external {}` | `function foo(uint[] memory arr) public {}` |
| **Modifiability**           | Cannot be modified. Attempting to modify will result in a compiler error. | Can be modified freely within the function. |

---

### **Key Differences:**
- **Immutability**: `calldata` is immutable, while `memory` is mutable.
- **Gas Efficiency**: `calldata` is more gas-efficient for large data structures since it avoids copying, whereas `memory` requires copying data, making it more expensive.
- **Function Scope**: `calldata` is typically used for external function parameters, while `memory` is used for internal function parameters and temporary variables.