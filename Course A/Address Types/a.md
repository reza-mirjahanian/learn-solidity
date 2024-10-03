Wei is the smallest, Ether = 10^18 Wei.

| Unit | Wei Exp | Wei |
| --- |  --- |  --- |
| wei | 1 | 1 |
| --- |  --- |  --- |
| Kwei | 10^3 | 1,000 |
| Mwei | 10^6 | 1,000,000 |
| Gwei | 10^9 | 1,000,000,000 |
| Ether | 10^18 | 1,000,000,000,000,000,000 |

-   **Address Type in Solidity:**
    -   The `address` type in Solidity stores **20 bytes**, which represents an **Ethereum address**.
    -   By default, an uninitialized address is set to the **zero address** (`0x0000000000000000000000000000000000000000`), which consists of 20 bytes of zeros.

**Retrieving the Balance of an Address:**

-   Every address on the Ethereum blockchain has a **balance** (in Wei), which can be accessed using the `.balance` property.
-   

```
function getAddressBalance() public view returns (uint256) {
    return someAddress.balance;
}
```