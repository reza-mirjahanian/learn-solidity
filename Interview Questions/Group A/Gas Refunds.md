#### **What Are Gas Refunds?**

-   Gas refunds are provided for certain operations that **reduce the state size** of the blockchain.

* * * *

#### **Operations That Provide Gas Refunds**:

1.  **`selfdestruct` (Deprecated)**:

    -   Previously, the **`selfdestruct`** function could be used to **delete a contract** and free up storage, providing a gas refund.
    -   **Note**: This operation is now **deprecated**.
2.  **Deleting Storage Slots**:

    -   Gas refunds are given when **storage slots** are **deleted** or **cleared**.
3.  **Setting Storage Slots to Zero**:

    -   Another operation that provides a gas refund is **setting storage slots to zero**, as this reduces the amount of data stored on the blockchain.