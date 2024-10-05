### Receive Function

-   **Purpose**: Triggered when a smart contract receives Ether
-   **Functionality**:
    -   Allows the contract to receive Ether
    -   Enables the contract to perform actions based on the specific Ether transfer

### Fallback Function

-   **Purpose**: Serves as a catch-all function for specific scenarios
-   **Triggered when**:
    1.  A call is made to the contract for a function that does not exist
    2.  The contract receives Ether but does not have a receive function