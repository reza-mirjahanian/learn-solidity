
```cpp
struct User {
   bool isActive;
   uint256 userAge;
}

mapping(userId => User) public users;

```

method 1;

```java
function example(uint256 userId) public {
   User memory user = users[userId];
   
   bool active = user.isActive;
   uint256 age = user.userAge;

   users[userId].isActive = false;
}

```

method 2;

```java
function example(uint256 userId) public {
   User storage user = users[userId];
   
   bool active = user.isActive;
   uint256 age = user.userAge;

   user.isActive = false;
}

```

Why method 2 cost less gas even we used storage keyword and get the all values from storage? which one should I use?

---------------------------------------


What method 1 does:

-   load full User struct from storage (2 sloads)
-   store User struct in memory (mstore)
-   load user.isActive from memory (mload), store on stack
-   load user.userAge from memory (mload), store on stack

method 2 does:

-   store storage pointer user (stack)
-   load user.isActive (sload), store on stack
-   load user.userAge (sload), store on stack

Storage operations are most costly, then memory, (then calldata), then stack. Method 2 bypasses memory altogether and thus is cheaper.