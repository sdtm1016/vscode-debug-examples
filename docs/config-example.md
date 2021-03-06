# Head first configurations

- [Simplest launch mode](#simplest-launch-mode)
- [Simplest attach mode](#simplest-attach-mode)
- [Use npm](#use-npm)
- [Use nodemon](#use-nodemon)


### Simplest launch mode


This is the simplest configuration, debugging Node.js using the `launch` mode, which is less used in real development scenarios.

`.vscode/launch.json`

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Debug Node App",
      "program": "${workspaceRoot}/app.js"
    }
  ]
}
```

Example: [minimal-node-app](/JavaScript/minimal-node-app/README.md)


### Simplest attach mode

The simplest configuration of the `attach` mode, the `attach` mode is used to debug a started program, here use `npm srcript` to start a node service.

`package.json`

```json
{
  "scripts": {
    "dev": "node --nolazy --inspect app.js"
  }
}
```

`.vscode/launch.json`

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "attach",
      "name": "Attach",
      "port": 9229
    }
  ]
}
```


Example: [minimal-attach](/JavaScript/minimal-attach/README.md)


### Use npm

`package.json`

```json
{
  "scripts": {
    "dev": "node --nolazy --inspect app.js"
  }
}
```

`.vscode/launch.json`

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "use npm",
      "runtimeExecutable": "npm",
      "runtimeArgs": ["run-script", "dev"],
      "console": "integratedTerminal",
      "port": 9229
    }
  ]
}
```


Example: [use-npm](/JavaScript/use-npm/README.md)


### Use nodemon

`.vscode/launch.json`

```json
{
   "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Use nodemon",
      "runtimeExecutable": "nodemon",
      "program": "${workspaceFolder}/app.js",
      "restart": true,
      "console": "integratedTerminal",
      "internalConsoleOptions": "neverOpen"
    }
  ]
}
```

Example: [use-nodemon](/JavaScript/use-nodemon/README.md)
