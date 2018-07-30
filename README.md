b3coind-rpc.js
===============

[![NPM Package](https://img.shields.io/npm/v/b3coind-rpc.svg?style=flat-square)](https://www.npmjs.org/package/bitcoind-rpc)
[![Build Status](https://img.shields.io/travis/bitpay/bitcoind-rpc.svg?branch=master&style=flat-square)](https://travis-ci.org/bitpay/bitcoind-rpc)
[![Coverage Status](https://img.shields.io/coveralls/bitpay/bitcoind-rpc.svg?style=flat-square)](https://coveralls.io/r/bitpay/bitcoind-rpc?branch=master)

A client library to connect to Bitcoin Core and B3Coin RPC in JavaScript.

## Get Started

b3coind-rpc.js runs on [node](http://nodejs.org/), and can be installed via [npm](https://npmjs.org/):

```bash
npm install b3coind-rpc
```

## Examples

```javascript
var run = function() {
  var bitcore = require('bitcore');
  var RpcClient = require('b3coind-rpc');

  var config = {
    protocol: 'http',
    user: 'user',
    pass: 'pass',
    host: '127.0.0.1',
    port: '5647',
  };

  var rpc = new RpcClient(config);

  var txids = [];

  function showBlockCount(callback){
    rpc.getBlockcount(function (err, ret) {
        callback(err,ret);
    });
  }

  showBlockCount(function(err,ret){
    if(err){
      console.log(err);
    }else{
      console.log(ret.result);
    }
  });
  
  
```

## License

**Code released under [the MIT license](https://github.com/bitpay/bitcore/blob/master/LICENSE).**

Copyright 2013-2018 BitPay, Inc.
