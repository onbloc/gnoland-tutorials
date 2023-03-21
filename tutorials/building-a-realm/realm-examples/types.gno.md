# types.gno

The `types` realm shows data types that can be used when developing realms or packages.

### Realm Code

```go
// types.gno

package types

import (
	"errors"

	"gno.land/p/demo/avl"
)

var (
	gInt		int      	= -42
	gUint		uint    	= 42
	gString		string  	= "a string"
	gStringSlice	[]string	= []string{"a", "string", "slice"}
	gError		error   	= errors.New("an error")
	gIntSlice  	[]int    	= []int{-42, 0, 42}
	gUintSlice  	[]uint   	= []uint{0, 42, 84}
	gTree        	avl.Tree
)

func init() {
	gTree.Set("a", 	"a for alpha")
	gTree.Set("A", 	"A FOR ALPHA")
	gTree.Set("1", 	"1 for one")
	gTree.Set("b", 	"b for beta")
	gTree.Set("g", 	"g for gamma")
	gTree.Set("!", 	"! for !")
	gTree.Set("d", 	"d for delta")
	gTree.Set("%", 	"% for percent")
	gTree.Set("|", 	"| for pipeline")
}
```

The code above resets variables for various data types and uses the `init()` function to introduce 9 sets of data into the tree structure.

It should be noted that `avl.Tree` is imported, as Gnolang must use the AVL Tree instead of map for determinism.

### Test Code

```go
// types_test.gno
package types

import "testing"

func Test(t *testing.T) {
	{
		got := gTree.Size()
		expected := 9
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	{
		got := gTree.Has("a")
		expected := true
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	{
		got := gTree.Has("e")
		expected := false
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	{
		_, got := gTree.Get("a") 
		expected := true
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	{
		got, _ := gTree.GetByIndex(1)
		expected := "%"
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	{
		gTree.Remove("A")
		got := gTree.Size()
		expected := 8
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	{
		gTree.Set("A", "A FOR ALPHA")
		println(gTree.GetByIndex(0)) // ! ! for !
		println(gTree.GetByIndex(1)) // % % for percent
		println(gTree.GetByIndex(2)) // 1 1 for one
		println(gTree.GetByIndex(3)) // A A FOR ALPHA
		println(gTree.GetByIndex(4)) // a a for alpha
		println(gTree.GetByIndex(5)) // b b for beta
		println(gTree.GetByIndex(6)) // d d for delta
		println(gTree.GetByIndex(7)) // g g for gamma
		println(gTree.GetByIndex(8)) // | | for pipeline
	}
}

```

The AVL Tree is a commonly used package, hence results in a long test case. Let us breakdown the code by segments.



```go
	{
		got := gTree.Size()
		expected := 9
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}
```

`Size() int` returns the size of the AVL Tree (number of nodes).



```go
	{
		got := gTree.Has("a")
		expected := true
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	{
		got := gTree.Has("e")
		expected := false
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}
```

`Has(key string) (has bool)` returns the existence of the node for the given key.



```go
	{
		_, got := gTree.Get("a") 
		expected := true
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}
```

`Get(key string) index int, value interface{}, exists bool`) returns the index, value, and the existence of the node for the given key.



```go
	{
		got, _ := gTree.GetByIndex(1)
		expected := "%"
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}
```

`GetByIndex(index int) (key string, value interface{})` returns the key and the value of the node for the given index.



```go
	{
		gTree.Remove("A")
		got := gTree.Size()
		expected := 8
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}
```

`Remove(key string)` removes the node for the given key (without returning any value).



```go
	{
		gTree.Set("A", "A FOR ALPHA")
		println(gTree.GetByIndex(0)) // ! ! for !
		println(gTree.GetByIndex(1)) // % % for percent
		println(gTree.GetByIndex(2)) // 1 1 for one
		println(gTree.GetByIndex(3)) // A A FOR ALPHA
		println(gTree.GetByIndex(4)) // a a for alpha
		println(gTree.GetByIndex(5)) // b b for beta
		println(gTree.GetByIndex(6)) // d d for delta
		println(gTree.GetByIndex(7)) // g g for gamma
		println(gTree.GetByIndex(8)) // | | for pipeline
	}
```

`Set(key string, value interface{}) (newSelf *Node, update bool)` adds or renews the tree for the given key/value pair.

The `printIn` function shows all nodes of the tree based on the index.

From what is seen above, nodes are ordered as the following: special characters -> numbers -> uppercase letters -> lowercase letters ->  special characters.

The order is actually in the ascending code value (DEC) as specified in the [ASCII](https://www.asciitable.com/asciifull.gif).
