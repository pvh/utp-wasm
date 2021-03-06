# utp-wasm

An emscripten WASM build of libutp, as an alternative
to utp-native when you are in an enviroment where you cannot load
a native extension

NOTE: This is much slower than the native binding

## Usage

```js
const utp = require('utp-wasm')

const sock = utp()

sock.on('connection', function (connection) {
  // a simple echo server
  connection.pipe(connection)
})

sock.listen(20000)
```

## API

Shares the same api as [utp-native](http://github.com/mafintosh/utp-native).

## Building

To build this first fetch the libutp dep

```sh
npm run fetch-libutp
```

Then install emscripten and do

```sh
npm run emscripten
```

## License

MIT
