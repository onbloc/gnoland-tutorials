# Concepts

## Proof of Contribution

Proof-of-Contribution (PoC) is a novel consensus mechanism that powers Gnoland. Unlike previous approaches to reach consensus in an asynchronous environment based on pure financial power (be it hash power or amount of tokens staked), Proof-of-Contribution relies on a group of Contributors to govern and operate the blockchain. According to the official Gnoland [blog](https://test3.gno.land/r/gnoland/blog:p/intro), there are 4 ways to become a contributor:

* Complete predefined tasks
* Complete pre-defined bounties
* Complete retroactive bounties
* Vesting style-rewards for core members

Out of these select Contributors, few are elected as Validators who have exclusive rights to verify transactions and produce blocks.

Revenue (fees) of the Gnoland blockchain is shared across Contributors, Validators, and smart contract publishers.

## Gnolang

Gnolang is a specialized programming language designed for the creation of smart contracts, known as "realms," for the Gnoland blockchain. As an interpreted variant of the Golang language, Gnolang inherits key characteristics such as simplicity, modularity, and concurrency.

Upon submission of source code to the Gnoland Chain, the GnoVM performs an abstract syntax tree interpretation, which requires developers to provide the original source code for transparency and accountability, in contrast to the use of bytecodes on the Ethereum blockchain.

In the near future, Gnolang will incorporate concepts related to multithreading and concurrency, such as Goroutines and Gochannels, to enhance the development of realms on the Gnoland platform.

## Realm

A realm refers to a specific instance of a smart contract that can be written in the Gnolang programming language.&#x20;

Each realm has the capability to publicly export the function `Render(path string) string`, which performs rendering when passed a valid markdown as a parameter for the specified `path`. This feature allows for increased ease of use and interactivity when working with realms.

During the development and prototyping phase, developers may utilize the `gnodev` CLI tool to streamline the testing and building of realms.

Additionally, realms offer the benefit of being able to utilize packages from standard libraries, such as `random`, `maths`, `avl`, and much more

## Tendermint 2

_Work in progress_

## IBC 2

_Work in progress_

## Gnode

_Work in progress_

## Gnoland Virtual Machine (GVM)

_Work in progress_
