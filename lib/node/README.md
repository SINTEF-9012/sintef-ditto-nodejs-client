# Ditto JavaScript Node.js client

It is an extended version of the official JavaScript API built and maintained purely for research purposes. Please contact @rdautov if you have any questions.

Implementation of the Eclipse Ditto JavaScript API that uses functionality of a Node.js environment. 
It is published to the npm registry as CommonJS module.

## Using

```shell
npm i --save  sintef--ditto-javascript-client-node
```

Create an instance of a client:

```javascript
const domain = 'localhost:8080';
const username = 'ditto';
const password = 'ditto';

// could also use newWebSocketClient() for the WebSocket implementation
const client = DittoNodeClient.newHttpClient()
            .withoutTls()
            .withDomain(domain)
            .withAuthProvider(NodeHttpBasicAuth.newInstance(username, password))
            .build();
```
To use a path other than `/api` to connect to ditto, the optional step `.withCustomPath('/path/to/api')` can be used.

To find out how to use the client, have a look at the [api documentation](../api/README.md#Using-the-client),
since the API will stay the same no matter what implementation is used.


### Proxy
The Node.js implementation supports setting up a proxy. 
Currently, it supports either reading directly from 'https_proxy' (or 'HTTPS_PROXY') environment variable
or manually setting the proxy settings.

```javascript
// may also omit one or more of the options
const proxyOptions = {
  url: 'PROXY-URL:PROXYPORT',
  username: 'PROXY-USERNAME',
  password: 'PROXY-PASSWORD'
}

DittoNodeClient.newHttpClient(proxyOptions)
//  ...
```
Any options that are set manually will override options that are read from an environment variable.
