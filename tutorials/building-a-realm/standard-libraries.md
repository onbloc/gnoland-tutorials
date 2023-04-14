# Standard Libraries

When developing a realm in Gnolang, developers may utilize libraries created by the Gno developer community.

The Gnoland Team has already built a set of libraries in the [stdlibs folder](https://github.com/gnolang/gno/tree/master/stdlibs). These modules can be imported in a manner similar to how libraries are imported in Golang.

An example of importing a `std` library in Gnolang is demonstrated in the following command.

```bash
$ import "std"
```

Let's explore some of the most useful modules in the library.

## `stdshim`

### ``[`banker.gno`](https://github.com/gnolang/gno/blob/master/stdlibs/std/banker.gno)``

A library for manipulating coins used on Gnoland. Interfaces that must be implemented when using this library are as follows:

```go
// returns the list of coins owned by the address
GetCoins(addr Address) (dst Coins)

// sends coins from one address to another
SendCoins(from, to Address, amt Coins)

// returns the total supply of the coin
TotalCoin(denom string) int64

// issues coins to the address
IssueCoin(addr Address, denom string, amount int64)

// burns coins from the address
RemoveCoin(addr Address, denom string, amount int64)
```

### ``[`coins.gno`](https://github.com/gnolang/gno/blob/master/stdlibs/std/coins.gno)``

A library that declares structs that express coins on Gnoland.

The struct looks like the following:

```go
type Coin struct {
    Denom    string   `json:"denom"`     // the symbol of the coin
    Amount   int64    `json:"amount"`    // the quantity of the coin
}
```

## `testing`

A library that declares the use of `*testing.T`, which is used for the creation and execution of test cases during the development and testing phase of realms utilizing the `gno` CLI tool with the `test` option.
