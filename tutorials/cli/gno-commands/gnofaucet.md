# gnofaucet

`gnofaucet` is a server for distributing GNOT, the gas currency of Gnoland, to specific addresses. Interact with the `gnofaucet` from an address with an empty balance to fuel it with GNOT to pay for transactions.

## Run `gnofaucet` Commands

Enable the faucet using the following command.&#x20;

```bash
$ gnofaucet serve
```

#### **Options**

| Name                      | Type    | Description                                                                          |
| ------------------------- | ------- |--------------------------------------------------------------------------------------|
| `chain-id`                | String  | The id of the chain (required).                                                      |
| `gas-wanted`              | Int64   | The maximum amount of gas to use for the transaction (default: `50000`)              |
| `gas-fee`                 | String  | The gas fee to pay for the transaction.                                              |
| `memo`                    | String  | Any descriptive text (default: `""`)                                                 |
| `test-to`                 | String  | Test address (optional) 부연설명 필요                                                      |
| `send`                    | String  | Coins to send (default: `"1000000ugnot"`).                                           |
| `captcha-secret`          | String  | The secret key for the recaptcha. If empty, the captcha is disabled (default: `""`). |
| `is-behind-proxy`         | Boolean | Uses X-Forwarded-For IP for throttling (default: `false`).                           |
| `insecure-password-stdin` | Boolean | INSECURE! Takes password from stdin (default: `false`).                              |

