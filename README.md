## bb-vm

[![Build Status](https://travis-ci.org/FBDY/bb-vm.svg?branch=develop)](https://travis-ci.org/FBDY/bb-vm) [![Greenkeeper badge](https://badges.greenkeeper.io/FBDY/bb-vm.svg)](https://greenkeeper.io/)

## Installation
This requires you to have Git and Node.js installed.

To install as a dependency for your own application:
```bash
npm install @bbge/vm
```
To set up a development environment to edit @bbge/vm yourself:
```bash
git clone https://github.com/FBDY/bb-vm.git
cd bb-vm
npm install
```

## Running the Development Server
Open a Command Prompt or Terminal in the repository and run:
```bash
npm start
```

## Playground
To view the Playground, make sure the dev server's running and go to [http://localhost:8073/playground/](http://localhost:8073/playground/) - you will be directed to the playground, which demonstrates various tools and internal state.

## Abstract Syntax Tree

#### Overview
The Virtual Machine constructs and maintains the state of an [Abstract Syntax Tree](https://en.wikipedia.org/wiki/Abstract_syntax_tree) (AST) by listening to events emitted by the [bb-blocks](https://github.com/FBDY/bb-blocks) workspace via the `blockListener`. Each target (code-running object, for example, a sprite) keeps an AST for its blocks. At any time, the current state of an AST can be viewed by inspecting the `vm.runtime.targets[...].blocks` object.

#### Anatomy of a Block
The VM's block representation contains all the important information for execution and storage. Here's an example representing the "when key pressed" script on a workspace:
```json
{
  "_blocks": {
    "Q]PK~yJ@BTV8Y~FfISeo": {
      "id": "Q]PK~yJ@BTV8Y~FfISeo",
      "opcode": "event_whenkeypressed",
      "inputs": {
      },
      "fields": {
        "KEY_OPTION": {
          "name": "KEY_OPTION",
          "value": "space"
        }
      },
      "next": null,
      "topLevel": true,
      "parent": null,
      "shadow": false,
      "x": -69.333333333333,
      "y": 174
    }
  },
  "_scripts": [
    "Q]PK~yJ@BTV8Y~FfISeo"
  ]
}
```

## Testing
```bash
npm test
```

```bash
npm run coverage
```
