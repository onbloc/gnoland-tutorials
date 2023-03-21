# Overview

A realm refers to a specific instance of a smart contract that can be written in the Gnolang programming language. If your goal is to become a dapp developer, it is imperative that you fully understand how realms work.

Before we dive in, let's first study the differences between realms and packages.

#### ****[**Realms**](https://github.com/gnolang/gno/tree/master/examples/gno.land/r)****

* Smart contracts in Gnolang.
* Realms are stateful.
* The default import path is `gno.land/r/~~~`.
* Each realm has the capability to publicly export the function `Render(path string) string`, which performs rendering when passed a valid markdown as a parameter for the specified `path`.

#### ****[**Packages**](https://github.com/gnolang/gno/tree/master/examples/gno.land/p/demo)****

* A unit that contains functionalities and utilities that can be used in realms.
* Packages are stateless.
* The default import path is `gno.land/p/~~~`.
* Can be imported to other realms or packages.

A notable feature of realms is the `Render()` function. Let's see `Render()` in action with a sample code:

```go
package demo

func Render(path string) string {
	return "# Hello Gno!"
}
```

Upon calling the realm above, `# Hello Gno!`is printed with a string-typed `path` declared in an argument. It should be noted that, while the `path` argument included in the sample code is not utilized, it serves the purpose of distinguishing the path during the rendering process.

The `Render` function can be invoked through three distinct methods.

> **Note:** The examples below assume that the sample realm above has been deployed.

**Method 1. Visiting the website**

<figure><img src="../../.gitbook/assets/img01.png" alt=""><figcaption><p>Calling <code>Render</code> by visiting the website</p></figcaption></figure>

Upon deployment of a realm, the `Render()` function can be invoked by specifying the path on the website, thereby enabling the rendering of Markdown text.

**Method 2. The `maketx call` option using `gnokey`**

<figure><img src="../../.gitbook/assets/img02.png" alt=""><figcaption><p>Calling <code>Render</code> with <code>gnokey maketx call</code></p></figcaption></figure>

Instead of rendering, however, the raw markdown is printed.

**Method 3. The `query vm/qrender` option using `gnokey`**

<figure><img src="../../.gitbook/assets/img03.png" alt=""><figcaption><p>Calling <code>Render</code> with <code>gnokey query vm/qrender</code></p></figcaption></figure>

Similar to the 2nd method, the raw markdown is printed.
