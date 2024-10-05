#### **What is a Sandwich Attack?**

-   **Definition**: A sandwich attack is a **malicious trading strategy** where an attacker manipulates the price of a token by placing transactions **before and after** a target's trade, profiting from the price difference.

* * * *

#### **How It Works**:

1.  **Mempool Monitoring**:

    -   The attacker monitors the **mempool** (where unprocessed transactions are visible) and identifies a **profitable trade**.
2.  **First Transaction (Front Running)**:

    -   The attacker pays **extra gas** to process their **buy transaction** before the target's trade.
    -   This **increases the demand** and **drives up the token's price**.
3.  **Target Transaction**:

    -   The original trade (target's transaction) is processed, further **driving up the token price**.
4.  **Second Transaction (Back Running)**:

    -   The attacker **sells the token** at the inflated price, profiting from the price increase.
    -   This **devalues the token**, leaving the original trader with a **less valuable asset**.