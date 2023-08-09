# Write Realms

## Arguments

Similar to Golang, variables can be assigned with names and data types.

```go
package demo

func Hello(name string) string {
	return "Hello " + name + "!"
}
```

> **Note:** Although concrete data types of Golang are supported, the [`avl`](https://github.com/gnolang/gno/tree/master/examples/gno.land/p/demo/avl) package must be used since `map` is unusable due to its non-deterministic properties.

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

The sample code above imports the `avl` and `dom` packages by their respective package paths.

## Access Modifier

In Gnolang, the distinction of access modifiers is based on the naming conventions of objects.

* Starting with an uppercase
  * Can be externally accessed, representing: `Public`
  * Similar to the `public` and `external` modifiers in Solidity
* Starting with a lowercase
  * Cannot be externally accessed, representing: `Private`
  * Similar to the `private` and `internal` modifiers in Solidity
