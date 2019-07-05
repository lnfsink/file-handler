## File Handler
`file-handler-sync` can synchronously read and write files by line

## Install

Using npm:

```shell
$ npm install file-handler-sync
```

Using yarn:

```shell
$ yarn add file-handler-sync
```

## Usage

```javascript
const handler = require('file-handler-sync')

let reader = handler.read('example/input.txt', {
  bufferSize: 1024 * 1024, // 1M Default
  encoding: 'utf8' // Default
})
let writer = handler.write('example/output.txt', {
  cacheLines: 1000 // Cache some lines before writing to the file
})
for (let line of reader) {
  writer.writeLine(line)
}
writer.close()
```