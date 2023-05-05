## Wallet

A `Wallet` is a user-facing API that is used to interact with an account. A `Wallet` instance is tied to a single key
pair and essentially wraps the given `Provider` for that specific account.

A wallet can be generated from a randomly generated seed, a private key, or instantiated using a Ledger device.

Using the `Wallet`, users can easily interact with the Tendermint2 chain using their account without having to worry
about account management.

## Initialization

### createRandom

Generates a private key-based wallet, using a random seed

Returns **Promise<Wallet>**

### fromMnemonic

Generates a bip39 mnemonic-based wallet

#### Parameters

* `mnemonic` **string** the bip39 mnemonic
* `accountIndex` **number** the account index (optional, default `0`)

Returns **Promise<Wallet>**

### fromPrivateKey

Generates a private key-based wallet

#### Parameters

* `privateKey` **string** the private key

Returns **Promise<Wallet>**

### fromLedger

Creates a Ledger-based wallet

#### Parameters

* `connector` **LedgerConnector** the Ledger device connector
* `accountIndex` **number** the account index (optional, default `0`)

Returns **Wallet**

## Provider Methods

### connect

Connects the wallet to the specified Provider

#### Parameters

* `provider` **Provider** the active Provider, if any

### getProvider

Returns the connected provider, if any

Returns **Provider**

## Account Methods

### getAddress

Fetches the address associated with the wallet

Returns **Promise<string>**

### getSequence

Fetches the account sequence for the wallet

#### Parameters

* `height` **number** the block height (optional, default `latest`)

Returns **Promise<number>**

### getAccountNumber

Fetches the account number for the wallet. Errors out if the
account is not initialized

#### Parameters

* `height` **number** the block height (optional, default `latest`)

Returns **Promise<number>**

### getBalance

Fetches the account balance for the specific denomination

#### Parameters

* `denomination` **string** the fund denomination (optional, default `ugnot`)

Returns **Promise<number>**

### getGasPrice

Fetches the current (recommended) average gas price

Returns **Promise<number>**

### estimateGas

Estimates the gas limit for the transaction

#### Parameters

* `tx` **Tx** the transaction that needs estimating

Returns **Promise<number>**

### signTransaction

Generates a transaction signature, and appends it to the transaction

#### Parameters

* `tx` **Tx** the transaction to be signed

Returns **Promise\<Tx>**

### sendTransaction

Signs and sends the transaction. Returns the transaction hash (base-64)

#### Parameters

* `tx` **Tx** the unsigned transaction

Returns **Promise<string>**

### getSigner

Returns the associated signer

Returns **Signer**
