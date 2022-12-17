To initiate an ETH price update, the smart contract should call the getLatestEthPrice function of the oracle. Now, due to its asynchronous nature, there's no way the getLatestEthPrice function can return this bit of information. What it does return instead, is a unique id for every request. Then, the oracle goes ahead and fetches the ETH price from the Binance API and executes a callback function exposed by the caller contract. Lastly, the callback function updates the ETH price in the caller contract.


