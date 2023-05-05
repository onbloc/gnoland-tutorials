## WebSocket Provider

Provider based on WS JSON-RPC requests.

### new WSProvider

Creates a new instance of the WebSocket Provider

#### Parameters

* `baseURL` **string** the WS URL of the node
* `requestTimeout` **number** the timeout for the WS request (in MS)

### closeConnection

Closes the WS connection. Required when done working
with the WS provider

### sendRequest

Sends a request to the WS connection, and resolves
upon receiving the response

#### Parameters

* `request` **RPCRequest** the RPC request

Returns **Promise<RPCResponse\<Result>>**

### parseResponse

Parses the result from the response

#### Parameters

* `response` **RPCResponse\<Result>** the response to be parsed

Returns **Result**

### waitForOpenConnection

Waits for the WS connection to be established