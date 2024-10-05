

### **Comparison of Function Visibility**


![alt text]({4E684B8D-FFA0-427D-9A23-9A4C82BC0496}.png)

-----------------

1.  **Public**

    -   Accessible by:
        -   Anyone
        -   Other contracts
        -   The contract itself
2.  **External**

    -   Accessible by:
        -   Only other contracts, unless using this.functionName().
3.  **Internal**

    -   Accessible by:
        -   The smart contract itself
        -   Contracts that inherit from it
4.  **Private**

    -   Accessible by:
        -   Only the smart contract itself