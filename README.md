Account 1: 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4

1. Deploy HelloWorld Contract with Account 1 @ `0xd8b934580fcE35a11B58C6D73aDeE468a2833fa8`
2. function owner: `0:address: 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4`
3. function getText: `0: string: Hello World`
4. function setText: `0: string: New Text`
5. function getText: `0: string: New Text`

Account 2: 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2

6. function getText: `0: string: New Text`. Although the state variable `text` is private, it's still accessible via the `getText` function.

7. function setText: Function call reverts because Account 2 is not the owner.

```
transact to HelloWorld.setText pending ...
transact to HelloWorld.setText errored: VM error: revert.

revert
	The transaction has been reverted to the initial state.
Reason provided by the contract: "Called is not the owner".
```

8. function transferOwnership: Function call reverts because Account 2 is not the owner.

```
transact to HelloWorld.setText pending ...
transact to HelloWorld.setText errored: VM error: revert.

revert
	The transaction has been reverted to the initial state.
Reason provided by the contract: "Called is not the owner".
```

Account 1: 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4

9. function transferOwnership: 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2. Success!
10. function setText: `0: string: New Owner Text`
11. function getText: `0: string: New Owner Text`
