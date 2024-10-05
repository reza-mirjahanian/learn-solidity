###  **Difference Between `transfer` and `transferFrom` in ERC-20 Tokens**


### **Key Points:**

#### **1. `transfer` Function:**

-   **Purpose**:
    -   Used when a **user** wants to send their **ERC-20 tokens** directly to another user or protocol.
-   **Direct Transfer**:
    -   The sender initiates the transfer and sends tokens from their wallet to the recipient's wallet.

#### **2. `transferFrom` Function:**

-   **Purpose**:
    -   Used for **delegated transfers**, where a **third party** (such as a protocol) is authorized to transfer tokens on behalf of the token owner.
-   **Approval Required**:
    -   The token owner must first **approve** the third party to spend a certain amount of tokens.
-   **Use Case**:
    -   Commonly used by **DeFi protocols** like **Uniswap** and **PancakeSwap** to facilitate token swaps. These platforms use `transferFrom` to move tokens in and out of users' wallets during transactions.