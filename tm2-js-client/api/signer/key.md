## Key Signer

Private key-based signer instance

### new KeySigner

Creates a new instance of the private-key KeySigner

#### Parameters

* `privateKey` **Uint8Array** the raw Secp256k1 private key
* `publicKey` **Uint8Array** the raw Secp256k1 public key

#### Usage

```ts
// Generate the public / private key from somewhere
const {publicKey, privateKey} = await generateKeyPair(
    entropyToMnemonic(generateEntropy()),
    index ? index : 0
);

new KeySigner(privateKey, publicKey);
// new Secp256k1 key signer created
```