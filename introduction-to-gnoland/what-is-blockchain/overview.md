# Overview

## Defining Blockchain

Blockchain is a distributed data processing system that records transactions across a network of computers. It is characterized by the decentralized distribution and storage of data, such as the transfer of value, across its network. The term "blockchain" refers to the structure of the data, which is composed of blocks that are linked together in a chain-like manner. These blocks serve as digital ledgers for recording peer-to-peer transaction data. The blocks are linked in a sequential manner, forming a chain over time. Due to the distributed nature of the system, all users maintain a copy of the transaction history, requiring consensus among all users for verification of the integrity of the recorded data.

Blockchain offers various advantages for developers and their projects. Its implementation enables secure and immutable record keeping and facilitates the development of decentralized applications, which ensure trust and transparency. Furthermore, blockchain can be employed to create smart contracts, which are self-executing agreements encoded in software, thereby increasing efficiency and minimizing the requirement for intermediaries.

## History of Blockchain

The concept of blockchain was first introduced in Bitcoin in 2008 by a pseudonymous figure called Satoshi Nakamoto. Bitcoin proposed a way for participants in a decentralized network to reach an agreement on a shared ledger with a unique mechanism called Proof-of-Work, which financially incentivizes the participants to invest computing power to solve a “puzzle” for the privilege to validate the latest block. Bitcoin enabled individuals to transfer value anywhere across the globe without the need for a third-party intermediary such as banks, payment processors, or governments.

Soon after Bitcoin, others began launching their own blockchains with added functionalities. However, releasing a new chain from scratch resulted in a low level of security and a high workload. As a solution, a Russian programmer Vitalik Buterin came up with a project called Ethereum, which allowed permissionless development and deployment of smart contracts, a term for automatically executed set of codes for building decentralized applications, or dapps for short.

While Ethereum significantly lowered the costs and time associated with dapp development, other issues emerged - the structure of Ethereum forced users to compete for resources of Ethereum, resulting in low speed and high transaction fees. Although this design was intentional to lower the hardware requirements for nodes, the tradeoff between decentralization and scalability ended up in an unappealing environment for developers looking for a fast and performant blockchain solution that didn't require an application to share resources with each other.

Out of the demand for interoperability, flexibility and sovereignty came Cosmos, a novel tech stack that consists of 3 main components:

1. Tendermint: A highly performant consensus layer that replaces Proof-of-Work with Proof-of-Stake, where block validation rights are earned in proportion to the node’s “stake” of each native asset.
2. Cosmos-SDK: A modular SDK that remarkably simplifies blockchain development.
3. IBC: A protocol for connecting independent blockchains to enable inter-blockchain communication such as cross-chain token swaps, messaging, and much more.

The birth of Cosmos created an ecosystem of interoperable, sovereign blockchains that are independent, yet composable by design. Unfortunately, problems that have yet to be solved exist: unsustainability of projects resulting from a lack of developer rewards excluding high token inflation, and ineffective governance structure that causes unaccountable, irresponsible community asset spending. Gnoland is a new smart contract platform that leverages and expands on the existing infrastructure and the community of the Cosmos ecosystem to solve these challenges.
