# Ditto JavaScript DOM client

It is an extended version of the official JavaScript API built and maintained purely for research purposes. Please contact @rdautov if you have any questions.

Implementation of the Eclipse Ditto JavaScript API that uses functionality of DOM environments. It is published as an ES6 module. You could also use a CDN like [UNPKG](https://unpkg.com/) to directly use it
in an HTML document (although "_very experimental_", use the `?module`-flag when importing from UNPKG).

## Using

```shell
npm i --save  sintef-ditto-javascript-client-dom
```

Create an instance of a client:

```javascript
const domain = 'localhost:8080';
const username = 'ditto';
const password = 'ditto';

// could also use newWebSocketClient() for the WebSocket implementation
const client = DittoDomClient.newHttpClient()
            .withoutTls()
            .withDomain(domain)
            .withAuthProvider(DomHttpBasicAuth.newInstance(username, password))
            .build();
```
To use a path other than `/api` to connect to ditto, the optional step `.withCustomPath('/path/to/api')` can be used.

To find out how to use the client, have a look at the [api documentation](../api/README.md#Using-the-client),
since the API will stay the same no matter what implementation is used.
