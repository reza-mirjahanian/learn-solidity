he speaker outlines **five key properties** of a cryptographic hash function that are essential for blockchain:

1.  **Deterministic**:

    -   The same input will always produce the same output (hash) every time.
2.  **Quick Computation**:

    -   Hash functions can compute the digest quickly, even for large inputs.
3.  **One-Way Function**:

    -   It is computationally **infeasible** to reverse the process and derive the original input from the hash (i.e., you can't go from the hash back to the input without brute-forcing).
4.  **Small Change, Big Difference**:

    -   Even a **tiny change** in the input causes a **massive change** in the hash output, making the new output uncorrelated with the previous one.
5.  **No Collisions**:

    -   Two different inputs should never produce the same hash (i.e., every unique input should result in a unique hash).