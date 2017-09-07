# spawn-command-npm [![Build Status](https://secure.travis-ci.org/anuoua/spawn-command-npm.png)](http://travis-ci.org/anuoua/spawn-command-npm)
Spawn commands like `child_process.exec` does but return a `ChildProcess`.
Add local modules path to child_process that you can execute commands in `node_modules/.bin/`

## Installation

    npm install spawn-command-npm

## Usage
```js
var spawnCommand = require('spawn-command-npm'),
    child = spawnCommand('echo "Hello spawn" | base64');

child.stdout.on('data', function (data) {
  console.log('data', data);
});

child.on('exit', function (exitCode) {
  console.log('exit', exitCode);
});
```
