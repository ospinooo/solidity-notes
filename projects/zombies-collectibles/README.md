



Build artifacts: JSON file that solidity compiler generates when compiling a smart contract.

Every test suite loads the build artifacts that will interact with so Truffle will know how to format function calls etc.

Example:
We have MyAwesomeContract.sol we load the artifact like this:
```js
const MyAwesomeContract = artifacts.require(“MyAwesomeContract”);
```
This give us a contract abstraction. Hides solidity interaction with the created abstraction.

describe in mocha wil be contract in solidity tests.
```js
contract("MyAwesomeContract", (accounts) => {
   it("should be able to receive Ethers", () => {
   })
 })
```
Same as in js tests.

`truffle test`: The way this works is that Truffle will just inspect the "test" directory and execute the files it finds there.


```js
contractInstance = await CryptoZombies.new(); // Deploy contract, beforeEach()
await contractInstance.kill(); // Remove contract, afterEach()
```

Important function that lets the only the owner delete code in this address.
```solidity
function kill() public onlyOwner {
   selfdestruct(owner());
}
```

## Group tests

Group tests around contexts with a shared concept.
```js
contract("title", async () => {
    context("shared tests scope. Title here.", async () => {
        it("", async () => {
            // test
        })
    })
})
```

Compile to bytecode that EVM understands.

```sh
truffle compile
```

Migrate to a specific network

```
truffle migrate --network rinkeby
```