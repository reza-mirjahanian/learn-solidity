#### **`mint` vs. `safeMint` in ERC-721**:

-   **`mint`**:

    -   This function **creates (mints)** a new token and assigns it to a specified address.
    -   It **does not check** whether the receiver address is a smart contract or a regular user address.
-   **`safeMint`**:

    -   This function also **mints a new token**, but it performs an **additional safety check**.
    -   It verifies if the recipient is a **smart contract**.
        -   If the recipient is a smart contract, it ensures that the contract implements the **ERC-721 Receiver interface** (`IERC721Receiver`), which can properly handle receiving NFTs.
    -   This prevents tokens from being sent to contracts that **cannot handle NFTs**, avoiding potential token loss.