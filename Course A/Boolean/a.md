All variables in Solidity are initialized with their default value. There is no undefined or null!

Interacting with Booleans
-------------------------

-   Use getter function to retrieve current value
-   Use setter function to change the value
-   Can set to `true`, `false`, `1`, or `0`
    -   **Note**: Setting to `0` results in `true`, which may be unexpected

Boolean Operations
------------------

1.  **Logical Negation**: Use `!` operator
    -   Example: `myBool = !_myBool;`
2.  **Logical Conjunction**: Use `&&` operator
3.  **Logical Disjunction**: Use `||` operator
4.  **Equality**: Use `==` operator
5.  **Inequality**: Use `!=` operator

Key Takeaways
-------------

-   Booleans are fundamental and commonly used across programming languages
-   In Solidity, they have a default value of `false`
-   Be cautious when using integer values (0 or 1) to set boolean values
-   Various logical operations can be performed on booleans