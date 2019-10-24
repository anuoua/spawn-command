# spawn-run [![Build Status](https://github.com/anuoua/spawn-run/workflows/Node%20CI/badge.svg)](https://github.com/anuoua/spawn-run/actions?workflow=Node+CI)

You can execute commands in `node_modules/.bin/` like npm run, return child_process.

## Installation

    npm install spawn-run --save-dev

## Usage

```js
var spawnRun = require('spawn-run')
var child = spawnRun(command, [options])
```

`command` like exec, and `options` like [child_process.spawn](https://nodejs.org/dist/latest-v6.x/docs/api/child_process.html#child_process_child_process_spawn_command_args_options), return `child_process`

## Example

```js
var spawnRun = require('spawn-run');
var child = spawnRun('echo "Hello spawn" | base64');

child.stdout.on('data', function (data) {
  console.log('data', data);
});

child.on('exit', function (exitCode) {
  console.log('exit', exitCode);
});
```
