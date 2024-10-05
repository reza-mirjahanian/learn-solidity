Basic Definition
----------------

-   A configuration file for Go Ethereum used to create private networks
-   Required to create the very first block (Genesis block) in a private Ethereum network
-   Written in JavaScript Object Notation (JSON) format

Key Components
--------------

### 1\. Config Object

**Chain ID**

-   Can be set to any number *except* 1, 2, or 3
-   Reserved numbers:
    -   1: Main network
    -   2 & 3: Test networks
-   Example used in video: 15

**Protocol Settings**

-   Homestead block: Set to start from block 0
-   EIP (Ethereum Improvement Protocol): Configured to start from block 0

### 2\. Network Parameters

**Difficulty**

-   Controls mining speed
-   Lower difficulty = Faster mining
-   Can be adjusted if mining takes too long

**Gas Limit**

-   Determines contract complexity capabilities
-   Current mainnet: ~6 million
-   Higher limit allows more complex contracts
-   Options:
    -   Match mainnet (6 million) for compatibility
    -   Set higher for more complex contracts