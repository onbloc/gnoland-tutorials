# Deploy and Call Realms

There are two methods of deploying and calling realms.&#x20;

1. With the blockchain: You can use the subcommands of [`gnokey`](../cli/gnokey.md) such as [`addpkg`](../cli/gnokey.md#subcommands), to deploy a realm to the Gnoland blockchain, and [`maketx call`](../cli/gnokey.md#call), to call available realms in the Gnoland blockchain.
2. Without a blockchain: You can use [`gno`](../cli/gno.md), which allows you to use the GnoVM without a blockchain in a local environment. This method is fast and allows you to use development patterns such as TDD. However, it does not facilitate the capability for external parties to participate in testing since it's done locally.

This section covers how to deploy and call realms with the first method - With the blockchain.

## Deploy

Use the `addpkg`, a subcommand of [`gnokey`](../cli/gno.md), to publicly deploy realms.

<figure><img src="../../.gitbook/assets/img05.png" alt=""><figcaption></figcaption></figure>

## Call

There are two ways to call your deployed function using `gnokey`.

### Method 1. `gnokey make tx call`

This method will execute a transaction to call a function in a realm. Note that this method is used for state-changing functions as it consumes gas.

<figure><img src="../../.gitbook/assets/16_gnokey_maketx_call.png" alt=""><figcaption></figcaption></figure>

### Method 2. `gnokey query`

This method is only for viewing the state of realms. Use this method for calling non-state-changing functions, as it does not consume any gas.

<figure><img src="../../.gitbook/assets/17_gnokey_query.png" alt=""><figcaption></figcaption></figure>
