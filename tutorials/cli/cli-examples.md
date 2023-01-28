# CLI Examples

## Create an Account

You may create a new account or recover one using the seed phrase.

```bash
$ gnokey generate # create a new seed phrase (mnemonic)

$ gnokey add my-account --recover  # registers a key named ‘my-account’ with a seed phrase

$ gnokey list # check the list of keys
```

## Add a Test Account and Run Faucet

### **Step 1. Create an account named `test1` with the test seed phrase below.**

```bash
$ gnokey add test1 --recover
```

> **Test Seed Phrase:** source bonus chronic canvas draft south burst lottery vacant surface solve popular case indicate oppose farm nothing bullet exhibit title speed wink action roast

### **Step 2. Run the gnofaucet**

```bash
$ gnofaucet serve test1 --chain-id dev --send 500000000ugnot
```

### **Step 3. Request for GNOT from the faucet**

```bash
$ curl --location --request POST 'http://localhost:5050' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'toaddr={address to receive}'
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
    --args ""

# username: must be at least 6 characters, lowercase alphanumeric with underscore
```

> **Note:** With a user registration fee of 200 GNOT and a gas fee that ranges up to 2 GNOT, you must have around 202 GNOT to complete this transaction. After registering as a user, you may replace your address with your `username` when developing or publishing a realm package.

## Get Account Information

```bash
# Get account information
$ gnokey query auth/accounts/{address}

# Get account balance
$ gnokey query bank/balances/{address}

# Get /r/demo/boards user information
$ gnokey query vm/qrender --data "gno.land/r/demo/users
my_account"
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
    --to "{address}"
```

## Create a Board

You can create a board called `my_board` on the `gno.land/r/demo/boards` realm with the following command.

```bash
# Calls the CreateBoard function of gno.land/r/demo/boards
$ gnokey maketx call my-account \
    --gas-fee "1000000ugnot" \
    --gas-wanted "10000000" \
    --broadcast \
    --pkgpath "gno.land/r/demo/boards" \
    --send "" \
    --func "CreateBoard" \
    --args "my_board"
```
