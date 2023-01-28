# Packages

In contrast to standard libraries, packages encompass functionalities that are more closely aligned with the characteristics and capabilities of realms.

Similar to `stdlibs`, the Gnoland Team has built a set of packages in the [demo package](https://github.com/gnolang/gno/tree/master/examples/gno.land/p/demo).

## ``[`avl`](https://github.com/gnolang/gno/tree/master/examples/gno.land/p/demo/avl)``

In Golang, the classic key/value data type is represented by the `map` construct. However, while Gnolang also supports the use of `map`, it is not a viable option as it lacks determinism due to its non-sequential nature.

To address this issue, Gnolang implements the [AVL Tree](https://en.wikipedia.org/wiki/AVL\_tree) (Adelson-Velsky-Landis Tree) as a solution. The AVL Tree is a self-balancing binary search tree.

The `avl` package comprises a set of functions that provide the capability to manipulate the leaves and nodes of the AVL Tree.

Click on [this link](realm-examples/types.gno.md) for a sample usage of the `avl` package.

## ``[`grc20`](https://github.com/gnolang/gno/tree/master/examples/gno.land/p/demo/grc/grc20)``

Gnolang includes an implementation of the `erc20` fungible token standard, referred to as `grc20`. The interfaces of `grc20` are as follows:

```go
TotalSupply() uint64
BalanceOf(account std.Address) uint64
Transfer(to std.Address, amount uint64)
Allowance(owner, spender std.Address) uint64
Approve(spender std.Address, amount uint64)
TransferFrom(from, to std.Address, amount uint64)
```

Two types of contracts exist in`grc20`:

1. `AdminToken`\
   \- Implements the token factory with `Helper` functions.\
   \- The underlying struct should not be exposed to users. However, it can be typecasted as UserToken using the `GRC20()` method.
2. `UserToken`\
   \- Implements the `IGRC20` interface.\
   \- The underlying struct can be exposed to users. Created with the `GRC20()` method of adminToken.
