
de-cryptonight
> node bindings for moneroV7 cryptonight hashing

### Requirements

node-cryptonight requires [Boost](http://www.boost.org)

##### Ubuntu

    sudo apt-get install libboost-all-dev

##### Mac

    brew install boost
    
    
##### Windows Visual Studio 

  Please refer to this site. https://studiofreya.com/cpp/boost/
    
* [Buiilding Boost 1.64, 1.65, 1.66 with Visual Studio 2017](https://studiofreya.com/2017/04/23/building-boost-1-64-with-visual-studio-2017/) 
* [Use Boost 1.64 in Visual Studio 2017](https://studiofreya.com/2017/05/17/how-to-use-boost-1-64-in-visual-studio-2017/)
* [Building Boost 1.62 with Visual Studio 2015](https://studiofreya.com/2016/09/29/how-to-build-boost-1-62-with-visual-studio-2015/)
* [Use C++ Boost library in Visual Studio 2013/2015](https://studiofreya.com/2016/06/25/how-to-use-cpp-boost-library-in-visual-studio/) 
* [Boost build scripts for Windows](https://github.com/Studiofreya/boost-build-scripts)
    
    
### Installation

    npm install --save node-cryptonight
   
### Testing

Code is linted with [standard](https://github.com/standard/standard) and tested with [Jest](https://github.com/facebook/jest). Run `npm test` to lint and run tests.

### Usage Examples

##### Synchronous Hashing

```js
const cryptonight = require('node-cryptonight').hash
const hash = cryptonight(Buffer.from('This is a test'))
console.log(hash) // <Buffer a0 84 f0 1d 14 37 ..>
```

##### Asynchronous Hashing

```js
const cryptonight = require('node-cryptonight').asyncHash
cryptonight(Buffer.from('This is a test'), hash => {
  console.log(hash) // <Buffer a0 84 f0 1d 14 37 ..>
})
```

##### Promise Wrapper Example

```js
function cryptonight(data) {
  return new Promise((resolve, reject) => {
    require('node-cryptonight').asyncHash(data, hash => {
      resolve(hash)
    })
  })
}

cryptonight(Buffer.from('This is a test'))
  .then(console.log) // <Buffer a0 84 f0 1d 14 37 ..>
```

### See Also

* [node-cryptonight-lite](https://github.com/ExcitableAardvark/node-cryptonight-lite)

### License

Released under the 3-Clause BSD License. Contains code from the Monero project. See `LICENSE` for more information.

