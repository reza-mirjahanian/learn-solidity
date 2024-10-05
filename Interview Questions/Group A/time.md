Solidity provides **five valid keywords** for measuring time:

1.  **seconds**
2.  **minutes**
3.  **hours**
4.  **days**
5.  **weeks**

* * * *

#### **Deprecated Keyword**:

-   The **`year`** keyword was **deprecated** in Solidity version **0.5.0** and later
-   


Important Considerations
------------------------

1.  **Block Time Variability**

    -   Ethereum block time is not constant
    -   Average block time: ~13-15 seconds (subject to change)
2.  **Miner Manipulation**

    -   Miners can slightly manipulate timestamps
    -   Don't rely on `block.timestamp` for high-precision timing
3.  **Gas Costs**

    -   Time-based operations consume gas
    -   Optimize code to minimize unnecessary time checks