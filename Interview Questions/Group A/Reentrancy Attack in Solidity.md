#### **How Does It Happen?**

-   **Vulnerability**: This attack is possible when a smart contract does not follow the **Checks-Effects-Interactions pattern**.
-   **Improper Flow**:
    -   The contract **updates storage variables after** making external contract calls.
    -   This allows the malicious contract to exploit the vulnerability by **reentering the function** before the state is updated.