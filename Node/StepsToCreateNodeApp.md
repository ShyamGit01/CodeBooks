# Steps to Create new Node App
There are 2 types of method we can use to start a new node app

## Create New App
1. Default Method
  1. This is a time consuming method where we have to install, create required files manually.
  2. Create a Folder with your project Name.
  3. Open **terminal** or **CMD prompt** and change the working directory to your project folder.
  4. Run `npm init -y` to initialize npm(Node Package Manager).
  5. It will automatically fill all details like Project Name, Licence, Author etc.
  6. Or you can set those manually by run `npm init`.
  7. After Installation complete install your required packages.

2. Using `Express Generator`
  1. This is a time saving method where all the basic required file, packages will include initialy.
  2. Create a Folder with your project Name.
  3. Open **terminal** or **CMD prompt** and change the working directory to your project folder.
  4. Run `npx express-generator` (It is an module of node which will make an complete project setup for us).
  5. Run `npm i` or `npm install` (It will install node_modules and also all the dependent packages in our project).

## Run the App
To run the app we also prefer 2 methods

1. Basic or General Method
  1. For basic method it is time consumig for developer but prefered for server implementation. 
  2. Run `npm start` or `node <filename.js>` on terminal in the project folder.
  3. The drawback is while developing an API developer tests many time and any changes made with the project it needs to be save and start the server again and again


2. Nodemon Method
  1. This is a time efficient for developers.
  2. Add nodemon with the project by run `npm i nodemon -D` (-D for install as devDependency).
  3. Go to *package.json* file present in the the project and copy paste the *start* in *scripts*.
  4. Rename the new *start* with *dev* and save.
  5. Now run the server by `npm run dev`.
  6. No matter how many changes you made after saving the changes the server will automatically run.



[⬅ Go Back(Basics of Node)](https://github.com/ShyamGit01/CodeBooks/blob/main/Node/BasicNode.md#introduction-to-node-) 
