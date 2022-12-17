zkSync makes use of something called zk-SNARKs which stands for... "Zero-knowledge succinct non-interactive arguments of knowledge".

Definition:
- a zero-knowledge proof allows Alice (called the prover) to prove to Bob (called the verifier) that she knows something to be true, without conveying any other information.

zkSync relies on a smart contract deployed to the Ethereum network to `hold all assets`, while most computations are performed off-chain. Every time you sign a transaction, the protocol submits it to operators who roll up multiple transactions (potentially thousands) into a block, and compute the following:

- cryptographic commitment (root hash)
- cryptographic proof (the SNARK)
- state ∆, representing a small amount of data for each transaction

All this stuff is then sent to the smart contract running on the Ethereum network. This enables an interested party to reconstruct the state at any given point in time.

The SNARK verification is significantly cheaper than verifying every transaction individually, and storing the state off-chain is also much cheaper than storing it in EVM.


# Provider

A Provider is an abstraction of a connection to the Ethereum network, providing a concise, consistent interface to standard Ethereum node functionality.

The ethers.js library provides several options which should cover the vast majority of use-cases, but also includes the necessary functions and classes for sub-classing if a more custom configuration is necessary.

alchemy, infura, etherscan..
