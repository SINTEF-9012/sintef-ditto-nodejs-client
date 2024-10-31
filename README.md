# Ditto JavaScript client
[![npm node](https://img.shields.io/npm/v/@eclipse-ditto/ditto-javascript-client-node?label=npm%3A%20node)](https://www.npmjs.com/package/sintef-ditto-javascript-client-node)
[![npm dom](https://img.shields.io/npm/v/@eclipse-ditto/ditto-javascript-client-dom?label=npm%3A%20dom)](https://www.npmjs.com/package/sintef-ditto-javascript-client-dom)

This module is an extended version of the official TypeScript library to facilitate working the the REST-like HTTP API and web socket API of Eclipse Ditto. This project is used solely for research and academic purposes.

### How to use it
Install `sintef-ditto-javascript-client-dom` for the DOM (browser) implementation, 
`sintef-ditto-javascript-client-node` for the NodeJS implementation.

More information can be found in the descriptions of the subpackages:
* [sintef-ditto-javascript-client-api](./lib/api/README.md) for some general information on the API of the client
* [sintef-ditto-javascript-client-dom](./lib/dom/README.md) for the DOM implementation
* [sintef-ditto-javascript-client-node](./lib/node/README.md) for the NodeJs implementation

### Compatibility with [Eclipse Ditto](https://github.com/eclipse-ditto/ditto)

The newest release of the JavaScript client will always try to cover as much API
functionality of the same Eclipse Ditto version as possible. There might
however be missing features for which we would be very happy to accept contributions.

### Coding
```
npm install
npm run build
npm run lint
npm test
# or npm run test:watch
```

### Troubleshooting
If you get strange errors, it would be best cleaning all dependencies and
starting from the beginning again:
```
npm run clean
# by hand delete node_modules in the root folder, or use a tool like rm, rimraf, etc.
npm install
npm run build
# ...
```
It is important to know that during install and build some extra processes
are triggered.

### Internals
This project is using [lerna](https://github.com/lerna/lerna) to split up the
client into different packages. This way we can have standalone codeable 
subprojects (`api`, `dom` and `node`) but still are able to control dependencies,
build processes or release processes globally.

For automatically generating barrel files, [barrelsby](https://github.com/bencoveney/barrelsby)
is used during the build process.
