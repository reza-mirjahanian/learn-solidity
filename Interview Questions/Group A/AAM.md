#### **Automated Market Maker (AMM) Pricing Formula**:

-   AMMs like **Uniswap** use the **constant product formula**:
    **`x * y = k`**

    -   **`x`**: Amount of **Token X** in the pool.
    -   **`y`**: Amount of **Token Y** in the pool.
    -   **`k`**: A **constant** representing the product of the two token quantities.

* * * *

#### **How It Works**:

-   When a user trades one token for another:
    -   The user **inputs one token** into the pool.
    -   The AMM calculates the **amount of the other token** to be received using the **constant product formula**.
    -   The **quantities of both tokens** in the pool are updated.
    -   The **constant `k`** is maintained, ensuring balance in the pool.

* * * *

#### **Key Formula**:

-   **`x * y = k`**: This formula ensures that the product of the token amounts in the pool remains constant, determining the price of the tokens during trades.