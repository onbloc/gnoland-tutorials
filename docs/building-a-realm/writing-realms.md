# Write Realms

## Arguments

Similar to Golang, variables can be assigned with names and data types.

```go
package demo

func Hello(name string) string {
	return "Hello " + name + "!"
}
```

Although concrete data types of Golang are supported, `avl` packages must be used since `map` is unusable due to non-determinism.

## Data Handling

Data handling in Gnolang works similarly to data handling in Golang.

```go
package demo

var total int

func init() {
	total = 1000
}

func Add(nb int) int {
	total += nb
	return total
}
```

The code above globally declares an integer-typed `total` variable and sets its value to `1000`. Then it changes its value using the `Add()` function, by adding the number passed as the argument.

## Import

Importing in Gnolang also works similarly to importing in Golang.

```go
package demo

import (
	"gno.land/p/demo/avl"
	"gno.land/p/demo/dom"
)

func Render(path string) string {
	thread := dom.Plot{Name: "Hello!"}
	thread.AddPost("Foo", "foo foo foo")
	thread.AddPost("Bar", "bar bar bar")
	return thread.String()
}
```

The sample code above imports the `avl` package and the `dom` package.

## Access Modifier

In Gnolang, the distinction of access modifiers is based on the naming conventions of objects.

* Starting with an uppercase: Can be externally accessed == Public \~= public & external in Solidity
* Starting with a lowercase: Cannot be externally accessed == Private \~= private & internal in Solidity
