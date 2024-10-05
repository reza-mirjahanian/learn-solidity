1. **Introduction**
-------------------

-   The video introduces the purpose: to provide **100 questions and answers** to prepare for a Solidity job interview.
-   The questions range from **easy to difficult**, covering **key aspects** of Solidity smart contract development.
-   The video promises that after going through the 100 questions, viewers will be well-prepared for a job interview or will gain useful knowledge about Solidity.

### Key Points:

-   **Target Audience**: Those preparing for Solidity job interviews or anyone wanting to learn more about Solidity.
-   **Structure**: Questions are categorized by difficulty levels (easy, intermediate, and difficult).
-   **Sponsorship**: The video is sponsored by "The Blocks Pro," a platform for Ethereum and Solidity screencasts.

* * * *

2. **Easy Questions**
---------------------

-   The video starts with **easy questions** to build a foundation in Solidity smart contracts.

### Example Questions and Answers:

-   **What is an Ethereum smart contract?**
    -   A small program that runs on the Ethereum blockchain.
-   **What makes an Ethereum smart contract special?**
    -   Once deployed, it cannot be stopped, modified, or hacked (if the code is correct).
-   **Can a smart contract interact with other smart contracts?**
    -   Yes, this is one of the strengths of smart contracts, allowing them to call functions on other contracts.
-   **Can a smart contract call an API on the web?**
    -   No, smart contracts can only interact with other contracts on the Ethereum blockchain. To interact with external APIs, the **Oracle pattern** is used.
-   **Can a smart contract store a lot of data?**
    -   No, storing data costs gas and is limited by gas consumption per block, so it's not feasible to store large amounts of data on-chain.

* * * *

3. **Solidity Language Features**
---------------------------------

-   **Solidity Language**: The video covers key language features and characteristics of Solidity.

### Key Points:

-   **Other Languages**: Solidity is the most popular language for smart contracts, but there are alternatives like **Vyper** and **LLL**.
-   **Typed Language**: Solidity is **statically typed**, meaning variable types must be defined explicitly, unlike JavaScript which is dynamically typed.
-   **Compilation**: Solidity is a **compiled language**. Contracts are compiled before deployment, unlike JavaScript, which uses just-in-time (JIT) compilation.
-   **File Extension**: Solidity files use the `.sol` extension.
-   **Multiple Contracts**: A single `.sol` file can contain multiple contracts, but it's generally better for organization to have one contract per file.

* * * *

4. **Smart Contract Structure**
-------------------------------

-   **Typical Layout**: Solidity smart contracts follow a specific structure.

### Key Elements:

-   **Pragma Directive**: Specifies the Solidity version to avoid compatibility issues.
-   **Contract Declaration**: Defined using the `contract` keyword, followed by curly braces `{}` to enclose the contract's body.
-   **State Variables**: Variables that persist on the blockchain.
-   **Functions**: Define the logic for reading and modifying data.

* * * *

5. **State vs Local Variables**
-------------------------------

-   **State Variables**: Persist on the blockchain after contract execution.
-   **Local Variables**: Exist only during the execution of a function and are not stored on-chain.

### Example Problem:

-   **Shadowing Issue**: If a local variable inside a function has the same name as a state variable, it will shadow (override) the state variable within the function's scope. The solution is to rename the local variable.

* * * *

6. **Variable Visibility**
--------------------------

-   **Private and Public Variables**:
    -   **Private**: Can only be accessed within the contract.
    -   **Public**: Accessible by anyone.
-   **Default Visibility**: State variables are private by default.

### Important Note:

-   **Private Variables**: While private in the Ethereum Virtual Machine (EVM), all data on the blockchain is publicly accessible. Specialized tools can be used to read private variables, so they are not truly private.

* * * *

7. **Data Types in Solidity**
-----------------------------

-   **Common Data Types**:
    -   **uint**: Used for integers, especially for Ether and token transfers.
    -   **address**: Used for identifying users and contracts.
    -   **string**: Used for storing text, such as names.

### Container Types:

-   **Mappings**: Key-value stores, often used for efficient lookups.
-   **Arrays**: Used to store ordered lists of elements.

* * * *

8. **Mappings and Arrays**
--------------------------

-   **Array Declaration**: `uint[] public myArray;`
-   **Mapping Declaration**: `mapping(address => bool) public myMapping;`
-   **Nested Mapping**: Mappings within mappings, e.g., `mapping(address => mapping(address => bool))`.

### Adding Data:

-   **Array**: Use the `push` method to add elements.
-   **Mapping**: Use bracket notation, e.g., `myMapping[address] = true;`.

* * * *

9. **Loops and Iteration**
--------------------------

-   **Looping through Arrays**: Use `for` loops with an initialization condition, stopping condition, and increment step.
-   **Mapping Iteration**: Solidity does not provide a way to iterate over mappings directly. You need to keep track of keys separately.

* * * *

10. **Function Visibility**
---------------------------

-   **Function Visibilities** (from most restrictive to least):
    -   **Private**: Only callable within the same contract.
    -   **Internal**: Callable within the contract or derived contracts.
    -   **External**: Callable only from outside the contract.
    -   **Public**: Callable both internally and externally.

* * * *

11. **Error Handling**
----------------------

-   **Revert with Error Message**: Use `require` to conditionally throw an error with a custom message.
-   **Example**: `require(condition, "Error message");`

* * * *

12. **Solidity Compilation Output**
-----------------------------------

-   **Artifacts Produced**:
    -   **ABI (Application Binary Interface)**: Defines the contract's interface, including function signatures and event declarations.
    -   **Bytecode**: The compiled code that is deployed to the Ethereum blockchain.

* * * *

13. **Ethereum Virtual Machine (EVM)**
--------------------------------------

-   The EVM only understands **bytecode**, which is produced from Solidity code.
-   **Bytecode**: A series of low-level instructions (opcodes) that the EVM executes.

* * * *

14. **Gas and Transactions**
----------------------------

-   **Gas**: A unit of computation cost in Ethereum.
-   **Gas Price**: The amount of Ether paid per unit of gas, typically expressed in **gwei**.
-   **Gas Limit**: The maximum amount of gas a transaction can consume.
-   **Insufficient Gas**: If a transaction runs out of gas, it is reverted, and all state changes are undone.

* * * *

15. **Development Tools**
-------------------------

-   **Popular IDE**: **Remix** is the most widely used IDE for Solidity, accessible via a web browser.
-   **Frameworks**:
    -   **Truffle**: A popular Solidity development framework.
    -   **OpenZeppelin**: A library of secure, reusable smart contract components (e.g., ERC-20, ERC-721 tokens).
-   **Local Blockchain**: **Ganache** is a CLI tool to run a local, in-memory Ethereum blockchain for testing.

* * * *

16. **Deploying Smart Contracts**
---------------------------------

-   **Requirements**:
    -   **Bytecode** of the contract.
    -   An Ethereum address with enough Ether to cover transaction costs.
    -   A wallet to sign the transaction.

### Ethereum Wallets:

-   **MetaMask**: A browser extension wallet.
-   **MyEtherWallet**: A web-based wallet.
-   **Ledger/Trezor**: Hardware wallets for secure Ether storage.

* * * *

17. **Test Networks**
---------------------

-   **Mainnet**: The Ethereum main network where real Ether is used.
-   **Ropsten**: A public test network for testing smart contracts before deploying to Mainnet.
-   **Kovan**: Another public test network, though specific to the Parity client.

* * * *

18. **Intermediate Questions**
------------------------------

-   **Timestamp Management**: Solidity does not have a native date type, so timestamps (in seconds) are used.
-   **Custom Data Structures**: You can define custom structures using **structs** or **enums**.
-   **Combining Arrays and Mappings**: Arrays allow iteration, while mappings allow quick lookups. Combining both allows efficient data management.

* * * *

19. **Difficult Questions**
---------------------------

-   **Reentrancy Attack**: A vulnerability where an attacker repeatedly calls a contract before the previous execution is completed, potentially draining funds (e.g., The DAO attack).
-   **Preventing Reentrancy**: Use the **Checks-Effects-Interactions** pattern, or limit the gas available to external calls.

* * * *

20. **Advanced Solidity Features**
----------------------------------

-   **ABI Encoder V2**: Enables experimental features in Solidity, such as returning structs from external function calls.
-   **Gasless Transactions**: Transactions where users don't pay gas. Instead, the dApp's backend signs and submits the transaction.
-   **Libraries**: Reusable pieces of code that can either be deployed as standalone contracts or embedded into other contracts.

* * * *

21. **Assembly in Solidity**
----------------------------

-   **Assembly**: Low-level EVM code that can be used for advanced operations.
-   **Use Case**: For example, determining whether an address is a contract or a regular address using the `extcodesize` opcode.