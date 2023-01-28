# Concepts

## Blocks

A block refers to a unit of data that is added to the blockchain - one can think of blocks as containers that store information in a blockchain. Once added, blocks become immutable, meaning that no one can modify or forge the data contained. Alongside the transaction data, a unique code called a "hash" is included in each block to link adjacent blocks in order. This feature ensures that changing a block ends up separating it from all subsequent blocks.

_What is a hash? A hash is an output of a “hash function”, a cryptographic function that takes an input and returns a fixed-length string. Some important characteristics of hash functions are as follows:_

1. _Deterministic: A single input always yields the exact same output._
2. _Asymmetric: Functions are easy to solve in one way, but probabilistically impossible to crack in the reverse, meaning that you cannot derive the input using the output._
3. _Random: Two similar inputs will produce two different and unconnected outputs._
4. _Collision-resistant: It is computationally infeasible to find two different inputs that produce the same output._

## Transactions

A transaction on a blockchain represents a transmission of data such as transferring ownership of an asset from one account to another, executing functions of a smart contract, voting on polls, or even creating a new class of asset on the blockchain.

## Cryptocurrency

Cryptocurrencies are digital assets whose transactions are recorded on blockchains. Cryptocurrencies are classified in 2 types:

**Coins:** Coins are natively-issued cryptocurrencies of blockchains. These cryptocurrencies are mostly used to pay for using resources of a chain, to vote on its updates or changes, or to secure it via staking. Some examples of coins are Ether for Ethereum, BNB for BSC, ATOM for the Cosmos Hub, and GNOT for Gnoland.

**Tokens:** Tokens are cryptocurrencies issued via smart contracts that define and track their supply and ownership. Tokens are usually created using a standard contract for uniformity and interoperability across dapps. Some examples of token standards are: ERC-20 for Ethereum-based tokens, BEP-20 for BSC-based tokens, CW-20 for Cosmwasm Chain-based tokens, and GRC-20 for Gnoland-based tokens.

## Keys

Keys are part of the authentication system of blockchains. There are two types of keys: private keys and public keys.

At its core, a private key is an astronomically large number (a 256-bit integer with approximately 1.158 x 10^77 combinations), randomly assigned to an individual upon creating an account on a wallet, a term for software that provides you with an interface to manage your assets on blockchains. The private key assigned to the account is the only way to access its funds by signing transactions initiated from it.

A public key is derived from the private key by applying a set of mathematical operations that involve elliptic curve functions and hash functions. These functions ensure that each public key is paired to its private key, while remaining irreversible to the private key. The public key serves 2 purposes:

1. To be converted into an address that can be used to receive cryptocurrencies.
2. Authenticating the legitimacy of a transaction to ensure that it has been signed by the actual owner.

## Gas

Gas refers to the cost necessary to execute a transaction on the network. Gas exists to compensate for the computational resources spent by validators (or miners) in verifying, processing, and updating the transaction to the blockchain.

Below are commonly-used terms related to Gas:

* Gas Price: The amount of fee tokens that you’re willing to pay per unit of gas. For example, if your transaction consumes 100,000 gas and you set your gas price as 5 uGNOT (the smallest unit of GNOT), your total fee payment will be 500,000 uGNOT.
* Gas Limit: The upper bound of gas you set for your transaction. Your transaction gets reverted if the gas limit is reached without the transaction being completed. However, if your transaction is successfully completed within the gas limit, the remaining gas gets returned to your wallet.

## Networks

A network refers to a distinct instance of a blockchain. There can be many networks of a single blockchain software such as [Goerli](https://goerli.net/) or [Sepolia](https://sepolia.dev/) network of Ethereum to provide a test environment for developers.

## Consensus Algorithms

Consensus algorithms refer to a set of rules that define how participants (nodes) in a blockchain network agree on a single state of the blockchain. Consensus algorithms ensure that all nodes agree on the order of transactions and who gets to validate the latest block to earn rewards. Various types of algorithms exist to keep validators financially aligned to contribute to the maintenance of the blockchain by rewarding honest ones while penalizing malicious ones. Some of the most popular algorithms include:

* Proof-of-Work (PoW): The PoW algorithm is where nodes called "miners" compete to solve a complex mathematical puzzle in order to add a new block to the blockchain. The computational resources invested to solve the puzzle is called hash power. The first miner to solve the puzzle is rewarded with cryptocurrency and network fees. This structure ensures that the security of a PoW blockchain scales with hash power of nodes, as one would have to invest over 50% of total hash power to temper with the blockchain.
* Proof-of-Stake (PoS): In a PoS consensus algorithm, nodes can become validators to add blocks and earn rewards by locking cryptocurrencies as collateral. This behavior is called staking. The number of blocks that a validator may add is proportional to the amount of cryptocurrencies staked. In PoS, the security of the chain is proportional to the market capitalization of the staking cryptocurrency.
* Delegated Proof-of-Stake (dPoS): DPoS is an extended version of PoS in which the number of validators that participate in block production are fixed. In a dPoS blockchain, validators are elected based on the amount of staking tokens that are staked to them as delegation from the community.

## Smart Contracts

The term "smart contract" refers to computerized protocols that automatically execute upon the fulfillment of predefined conditions, without the need for third-party intervention. Despite a common misconception, the concept of smart contracts predates the advent of blockchain technology. It was first introduced by computer scientist Nick Szabo in 1994, in his research paper "[Formalizing and Securing Relationships on Public Networks](https://firstmonday.org/ojs/index.php/fm/article/view/548/469)". Szabo described smart contracts as a combination of protocols and user interfaces that formalize and secure relationships over computer networks, with design objectives and principles drawn from legal principles, economic theory, and the theories of reliable and secure protocols.

In 2013, Ethereum creator Vitalik Buterin published a post on his blog, entitled "[Ethereum: The Ultimate Smart Contract and Decentralized Application Platform](https://web.archive.org/web/20131228111141/https://vbuterin.com/ethereum.html)", outlining his implementation of smart contracts on the Ethereum blockchain for wide-scale usage.

## **Dapps**

Dapps (decentralized applications), are applications that run on blockchain. Dapps rely on smart contracts to ensure the integrity and autonomy of their operations, making them censorship-resistant and autonomous.
