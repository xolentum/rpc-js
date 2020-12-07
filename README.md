# Xolentum RPC JS

## About 

[![NPM](https://nodei.co/npm/@xolentum/xolentum-rpc-js.png)](https://nodei.co/npm/@xolentum/xolentum-rpc-js/)

Javascript library to interact with RPC Daemon and RPC Wallet.\
All requests are queued. Most functions are async.

There is no need to connect and disconnect the underlying socket anymore.

The library supports HTTP, HTTPS and digest authentication.

The library use an axios interceptor to implement digest authentication.

Digest authentication is activated as soon as a username and a password is supplied during object creation.

Once initialized simply use the query functions.


### Daemon RPC without Digest Authentication

Please refer to the [documentation](https://xolentum.github.io/rpc-js/module-RPCDaemon.html) and look at the unit tests.
```javascript
const rpcDaemon = require('@xolentum/xolentum-rpc').RPCDaemon

const daemonClient = rpcDaemon.createDaemonClient({
  url: 'http://127.0.0.1:13580'
})
// When using a self signed certificate with HTTPS you need to set the function sslRejectUnauthorized to false.
daemonClient.sslRejectUnauthorized(false)
```


### Daemon RPC with Digest Authentication

Please refer to the [documentation](https://xolentum.github.io/rpc-js/module-RPCDaemon.html) and look at the unit tests.
```javascript
const rpcDaemon = require('@xolentum/xolentum-rpc').RPCDaemon

const daemonClient = rpcDaemon.createDaemonClient({
  url: 'http://127.0.0.1:13580',
  username: 'user',
  password: 'pass'
})
// When using a self signed certificate with HTTPS you need to set the function sslRejectUnauthorized to false.
daemonClient.sslRejectUnauthorized(false)
```


### Wallet RPC without Digest Authentication

Please refer to the [documentation](https://xolentum.github.io/rpc-js/module-RPCWallet.html) and look at the unit tests.
```javascript
const rpcWallet = require('@xolentum/xolentum-rpc').RPCWallet

const walletClient = rpcWallet.createWalletClient({
  url: 'http://127.0.0.1:20000'
})
// When using a self signed certificate with HTTPS you need to set the function sslRejectUnauthorized to false.
walletClient.sslRejectUnauthorized(false)
```


### Wallet RPC with Digest Authentication

Please refer to the [documentation](https://xolentum.github.io/rpc-js/module-RPCWallet.html) and look at the unit tests.
```javascript
  const rpcWallet = require('@xolentum/xolentum-rpc').RPCWallet

  const walletClient = rpcWallet.createWalletClient({
  url: 'http://127.0.0.1:20000',
  username: 'user',
  password: 'pass'
})
// When using a self signed certificate with HTTPS you need to set the function sslRejectUnauthorized to false.
walletClient.sslRejectUnauthorized(false)
```

### Generate JSDoc documentation

```sh
npm run generate-docs
```

### Get unit tests list

```sh
npm test
```

## License

[BSD-3-Clause License](LICENSE)

Copyright (c) 2020, The Xolentum Project  
Copyright (c) 2019, The ArQmA Network
