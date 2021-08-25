# Package Manager (NPM)

**Node Package Manager** (NPM) provides 2 main functionalities −
- Online repositories for node.js packages/modules which are searchable on search.nodejs.org
- Command line utility to install Node.js packages, do version management and dependency management of Node.js packages.

To check the version of node run below command
`
npm --version
`

### Installing Modules using NPM
There is a simple syntax to install any Node.js module −

1. To install node module for a single project
`
npm install <Module Name>
`
or can replace `install` with `i` only it will work as same, the `i` represents short form of `install`
`
npm i <Module Name>
`

2. To install node module globally (for every project)
`
npm install <Module Name> -g
` or ` npm i <Module Name> -g` 

### Use the installed module
To use the module you have installed, you need to write a single line of code

`
var <Variable Name> = require('<Module Name>');
`

