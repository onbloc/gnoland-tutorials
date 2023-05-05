## Provider

A `Provider` is an interface that abstracts the interaction with the Tendermint2 chain, making it easier for users to
communicate with it. Rather than requiring users to understand which endpoints are exposed, what their return types are,
and how they are parsed, the `Provider` abstraction handles all of this behind the scenes. It exposes useful API methods
that users can use and expects concrete types in return.

Currently, the `tm2-js-client` package provides support for two Provider implementations:

- [JSON-RPC Provider](json-rpc-provider.md): executes each call as a separate HTTP RPC call.
- [WS Provider](ws-provider.md): executes each call through an active WebSocket connection, which requires closing when
  not needed
  anymore.

Read-only abstraction for accessing blockchain data

## Account Methods

### getBalance

Fetches the denomination balance of the account

#### Parameters

* `address` **string** the bech32 address of the account
* `denomination` **string** the balance denomination (optional, default `ugnot`)
* `height` **number** the height for querying.
  If omitted, the latest height is used (optional, default `0`)

Returns **Promise\<number>**

### getAccountSequence

Fetches the account sequence

#### Parameters

* `address` **string** the bech32 address of the account
* `height` **number** the height for querying.
  If omitted, the latest height is used. (optional, default `0`)

Returns **Promise\<number>**

### getAccountNumber

Fetches the account number. Errors out if the account
is not initialized

#### Parameters

* `address` **string** the bech32 address of the account
* `height` **number** the height for querying.
  If omitted, the latest height is used (optional, default `0`)

Returns **Promise\<number>**

## Block methods

### getBlock

Fetches the block at the specific height, if any

#### Parameters

* `height` **number** the height for querying

Returns **Promise\<BlockInfo>**

### getBlockResult

Fetches the block at the specific height, if any

#### Parameters

* `height` **number** the height for querying

Returns **Promise\<BlockResult>**

### getBlockNumber

Fetches the latest block number from the chain

Returns **Promise\<number>**

## Network methods

### getNetwork

Fetches the network information

Returns **Promise\<NetworkInfo>**

### getConsensusParams

Fetches the consensus params for the specific block height

#### Parameters

* `height` **number** the height for querying

Returns **Promise\<ConsensusParams>**

### getStatus

Fetches the current node status

Returns **Promise\<Status>**

### getGasPrice

Fetches the current (recommended) average gas price

Returns **Promise\<number>**

### estimateGas

Estimates the gas limit for the transaction

#### Parameters

* `tx` **Tx** the transaction that needs estimating

Returns **Promise\<number>**

## Transaction methods

### sendTransaction

Sends the transaction to the node for committing.
The transaction needs to be signed beforehand.

#### Parameters

* `tx` **string** the base64-encoded signed transaction

Returns **Promise\<string>**

### waitForTransaction

Waits for the transaction to be committed on the chain.
NOTE: This method will not take in the fromHeight parameter once
proper transaction indexing is added - the implementation should
simply try to fetch the transaction first to see if it's included in a block
before starting to wait for it; Until then, this method should be used
in the sequence:
get latest block -> send transaction -> waitForTransaction(block before send)

#### Parameters

* `hash` **string** The transaction hash
* `fromHeight` **number** The block height used to begin the search (optional, default `latest`)
* `timeout` **number** Optional wait timeout in MS (optional, default `15000`)

Returns **Promise\<Tx>**
