## Requirements

* npm
* yarn
* lerna (optional)

It's recomended to have lerna cli in your machine, for that instal the lerna package globally with the command `npm install -g lerna`

## Usage

Upon cloning the repo run `lerna bootstrap`.  
To run the scripts from each project (packages/*/package.json), you can run them on the root folder with the command `lerna run $SCRIPT --scope=$PROJECT`.  
Example running the `start` script for the packages/`mobile` project: `lerna run start --scope=mobile`.

You can also run the script via `yarn` in the projects respective directory. This is recommended if you want more feedback from the script you want to run.  
`cd packages/mobile`  
`yarn start`

If you want to add new packages you should use `lerna` in the root directory.  
To add a new package globally, use `lerna add $PACKAGE`.  
To add a new package only for a specific project use `lerna add $PACKAGE --scope=$PROJECT`.  
Example `lerna add react` to add react globally and `lerna add react-dom --scope=web` to add react-dom to the `web` project.