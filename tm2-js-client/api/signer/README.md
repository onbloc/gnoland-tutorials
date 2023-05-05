## Signer

A `Signer` is an interface that abstracts the interaction with a single Secp256k1 key pair. It exposes methods for
signing data, verifying signatures, and getting metadata associated with the key pair, such as the address.

Currently, the `tm2-js-client` package provides support for two `Signer` implementations:

- [Key](key.md): a signer that is based on a raw Secp256k1 key pair.
- [Ledger](ledger.md): a signer that is based on a Ledger device, with all interaction flowing through the user's
  device.

## API

### getAddress

Returns the address associated with the signer's public key

Returns **Promise<string>**

### getPublicKey

Returns the signer's Secp256k1-compressed public key

Returns **Promise<Uint8Array>**

### signData

Generates a data signature for arbitrary input

#### Parameters

* `data` **Uint8Array** the data to be signed

Returns **Promise<Uint8Array>**

### verifySignature

Verifies if the signature matches the provided raw data

#### Parameters

* `data` **Uint8Array** the raw data (not-hashed)
* `signature` **Uint8Array** the hashed-data signature

Returns **Promise<boolean>**