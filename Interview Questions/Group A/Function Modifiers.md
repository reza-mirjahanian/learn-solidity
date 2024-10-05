#### **What Are Function Modifiers?**

-   **Definition**: Modifiers are a **block of code** that is executed **before** the main logic of a function.
-   **Purpose**: They are typically used to enforce conditions that must be met before a function can proceed.

#### **How Modifiers Work**:

-   A modifier can **check conditions** (e.g., verifying the caller's identity or ensuring sufficient balance) before allowing the function to execute.
-   If the condition in the modifier is **met**, the function continues. If not, the transaction is **reverted**.
-   

```
modifier onlyOwner() {
    require(msg.sender == owner, "Not the contract owner");
    _;
}

function withdraw() public onlyOwner {
    // Function logic here
}
```