three main function types in Solidity:

1.  Writing functions
2.  View functions
3.  Pure functions


-   View functions for reading state
-   Pure functions for computations
-   Writing functions for modifying state


---------
1.  **Return Values in Writing Functions:**

    -   It's possible but not recommended to return values from writing functions
    -   Return values are mainly for inter-contract communication
    -   In real blockchain environments (outside Remix), events are used instead of return values for writing functions