#### **Pattern Breakdown**:

1.  **Checks**:

    -   Ensure that **access control**, **balances**, and other **`require` statements** are properly validated before proceeding.
    -   Example: Verifying that the caller has sufficient balance or proper permissions to execute the function.
2.  **Effects**:

    -   After checks are passed, **update all state variables** and internal information.
    -   Example: Deducting the user's balance or marking the funds as withdrawn **before** making any external calls.
3.  **Interactions**:

    -   Only after updating the state should the contract make **external calls** to other contracts or transfer funds.
    -   This prevents attackers from **reentering the contract** and exploiting unupdated state variables.

#### **Why is This Important?**

-   **Reentrancy Attack Risk**: If state variables (like balances) are updated **after** making an external contract call, malicious contracts can **call back** into the original function before the state is updated.
    -   This would allow the attacker to **withdraw more than their balance**, potentially **draining the entire contract** before the appropriate state updates are made