#### **What is Transaction Front Running?**

-   **Definition**: Front running occurs when someone with access to the **mempool** (a pool of unprocessed transactions) **spots a profitable transaction** and pays **higher gas fees** to execute their own transaction **before** the original one.

* * * *

#### **How It Works**:

-   **Mempool Access**: The attacker monitors the mempool, where pending transactions are visible.
-   **Gas Fee Manipulation**: By offering a higher gas fee, the attacker ensures their transaction is **processed first** by miners.
-   **Impact on Original Transaction**:
    -   The original transaction is either **less profitable** or **no longer profitable** because the attacker has already capitalized on the opportunity.

* * * *

#### **Relation to Sandwich Attack**:

-   **First Step**: Front running is the **initial phase** of a **sandwich attack**, where the attacker places transactions **before and after** the target transaction to manipulate the outcome.