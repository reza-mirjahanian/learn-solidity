### Behavior of message.sender:

-   If an account directly interacts with a contract:
    -   `message.sender` is the address of that account
-   If Contract A calls Contract B:
    -   `message.sender` in Contract B is the address of Contract A