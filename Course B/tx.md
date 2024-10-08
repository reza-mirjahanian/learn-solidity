
With  `msg.sender`  the owner can be a contract.

With  `tx.origin`  the owner can never be a contract.

In a simple call chain A->B->C->D, inside D  `msg.sender`  will be C, and  `tx.origin`  will be A.

`msg.sender`  is preferred for the flexibility it provides. Furthermore, for Serenity, even though it's a while out, Vitalik recommends avoiding  `tx.origin`:  

Carefully consider if you really ever need to use  `tx.origin`. Remember, you may not be the only user of your contract. Other people may want to use your contract and want to interact with it via a contract they've been written.

If the origin is really desired in D, then each of the functions in the contracts B, C, D could take an extra parameter to propagate the origin: A would pass its address (`this`) to B, B would pass the value to C, and C would pass it to D.

 a contract that uses a passed in value for the origin, must be very careful in how it uses the origin: anyone can pass in a value that is not the real origin.