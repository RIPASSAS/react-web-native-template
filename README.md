## Requirements

* npm
* yarn
* lerna (optional)

It's recommended  to have lerna cli in your machine, for that install the lerna package globally with the command `npm install -g lerna`, you can also use lerna commands just by having a `npx` prefix. `npx lerna bootstrap`.

## Usage

Upon cloning the repo run `lerna bootstrap`.  
To run the scripts from each project (packages/*/package.json), you can run them on the root folder with the command `lerna run $SCRIPT --scope=$PROJECT`.  
Example running the `start` script for the packages/`mobile` project: `lerna run start --scope=mobile`.

You can also run the script via `yarn` in the project's respective directory. This is recommended if you want more feedback from the script you want to run.  
`cd packages/mobile`  
`yarn start`

If you want to add new packages you should use `lerna` in the root directory.  
To add a new package globally, use `lerna add $PACKAGE`.  
To add a new package only for a specific project use `lerna add $PACKAGE --scope=$PROJECT`.  
Example `lerna add react` to add react globally and `lerna add react-dom --scope=web` to add react-dom to the `web` project.

## Info

This monorepo setup relies on the yarn workspaces functionality to make it possible to share the same node dependencies throughout the projects, this way there shouldn't be any dependencies duplicated unless specified. This is called hoisting.  
However due to specific limitations of react-native projects, the node dependencies cannot currently be hoisted to the root directory. This my change in the future.


Lerna is used to allow the use of local packages in order for us to be able to share code between projects.  
In this case we have a project named `core` where we write all the platform agnostic code. This is later added as a dependency through `lerna add @proj/core` (the name of the package is defined in packages/core/package.json).