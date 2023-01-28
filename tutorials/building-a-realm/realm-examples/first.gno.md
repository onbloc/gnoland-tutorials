# first.gno

The `first.gno` realm declares variables, constants, and functions.

### Realm Code

```go
// first.gno

package first

import "gno.land/p/demo/avl"

var myVar = 1

const myConst = 10

var initlVar int

func init() {
	initlVar = 1000
}

func GetInitValue() int {
	return initlVar
}

func get() int {
	return myVar
}

func Get() int {
	return myVar
}

func Inc() int {
	myVar += 1
	return myVar
}

func IncByInput(inc int) int {
	myVar += inc
	return myVar
}

func Dec() {
	myVar -= 1
}

func ImpossibleInc() {
	myConst += 1
}
```

Let's break down the code by each segment.



```go
var myVar = 1

const myConst = 10

var initlVar int

func init() {
	initlVar = 1000
}

func GetInitValue() int {
	return initlVar
}
```

The code block above displays the variable & constant declaration code (and 2 functions). The `init()` function is a pre-defined function that serves a similar purpose as that of the Golang (executed with priority upon initializing or importing a package).

As a result, once the code above is executed, the `initlVar` variable with only a declared data type, but without an initial value, is assigned with a value of `1000`.



```go
func get() int {
	return myVar
}

func Get() int {
	return myVar
}

func Inc() int {
	myVar += 1
	return myVar
}

func IncByInput(inc int) int {
	myVar += inc
	return myVar
}

func Dec() {
	myVar -= 1
}

func ImpossibleInc() {
	myConst += 1
}
```

The code block above displays the function declaration code.

The `get()` function and the `Get()` function are equivalent in functionality, with the exception of the capitalization of the latter, which serves to implement the previously discussed access control mechanism.

The `Inc()` function and the `IncByInput()` function are designed to increment the value of `myVar`. Note that the `IncByInput` function specifically obtains the number to be increased, as an argument, from the user.

The `Dec()` function decrements the value of `myVar`. However, as it does not possess a return value, an additional function must be used to verify the result.

The `ImpossibleInc()` function at the end results in an error as it attempts to modify the value of the constant.



### Test Code

```go
// first_test.gno

package first

import "testing"

func Test(t *testing.T) {
	// GetInitValue
	{
		got := GetInitValue()
		expected := 1000
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	// get
	{
		got := get()
		expected := 1
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	// Get
	{
		got := Get()
		expected := 1
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	// Inc
	{
		got := Inc()
		expected := 2
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	// IncByInput
	{
		got := IncByInput(777)
		expected := 779
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	// Dec
	{
		Dec() // can't assign return value since Dec() doesn't return anything
		got := Get()
		expected := 778
		if got != expected {
			t.Fatalf("expected %v, got %v.", expected, got)
		}
	}

	// ImpossibleInc()
	{
		// ImpossibleInc() // will panic, since myConst is const not var
	}
}



```
