# Interact with Gnoland

This tutorial will teach you how to interact with the Gnoland blockchain by creating an account and calling various realms to send transactions on the network.

## Prerequisites

* [Initial Setup](../docs/environment-setup/initial-setup.md)

## Create an Account

In order to interact with Gnoland, you need an account that you will use to sign and send transactions. You may create a new account with `gnokey generate` or recover an existing one with `gnokey add`. Confirm that your account was successfully added with `gnokey list` to display all accounts registered in the key base of your device.&#x20;

```bash
$ gnokey generate # create a new seed phrase (mnemonic)

$ gnokey add {your_account_name} --recover  # registers a key with the name set as the value you put in {your_account_name} with a seed phrase

$ gnokey list # check the list of keys
```

## Register As a User

```bash
$ gnokey maketx call my-account \
    --gas-fee "1000000ugnot" \
    --gas-wanted "2000000" \
    --pkgpath "gno.land/r/demo/users" \
    --broadcast \
    --send "200000000ugnot" \
    --func "Register" \
    --args "" \
    --args "my_account" \ # (must be at least 6 characters, lowercase alphanumeric with underscore)
    --args "" \
    --chainid "test3" \
    --remote "test3.gno.land:36657"

# username: must be at least 6 characters, lowercase alphanumeric with underscore
```

> **Note:** With a user registration fee of 200 GNOT and a gas fee that ranges up to 2 GNOT, you must have around 202 GNOT to complete this transaction. After registering as a user, you may replace your address with your `username` when developing or publishing a realm package.

## Get Account Information

```bash
# Get account information
$ gnokey query auth/accounts/{address} --remote "test3.gno.land:36657"

# Get account balance
$ gnokey query bank/balances/{address} --remote "test3.gno.land:36657"

# Get /r/demo/boards user information
$ gnokey query vm/qrender --data "gno.land/r/demo/users
my_account" --remote "test3.gno.land:36657"
```

## Send Tokens

The following command will send 1,000,000 ugnot (= 1 GNOT) to the address specified in the `to` argument.

```bash
# Creates and broadcast a token transfer transaction
$ gnokey maketx send my-account \
    --gas-fee "1ugnot" \
    --gas-wanted "2000000" \
    --memo "" \
    --broadcast \
    --send "1000000ugnot" \
    --to "{address}" \
    --chainid "test3" \
    --remote "test3.gno.land:36657"
```

## Create a Board

Try creating a board called `my_board` on the `gno.land/r/demo/boards` realm with the following command:

```bash
# Calls the CreateBoard function of gno.land/r/demo/boards
$ gnokey maketx call my-account \
    --gas-fee "1000000ugnot" \
    --gas-wanted "10000000" \
    --broadcast \
    --pkgpath "gno.land/r/demo/boards" \
    --send "" \
    --func "CreateBoard" \
    --args "my_board" \
    --chainid "test3" \
    --remote "test3.gno.land:36657"
```
