
# Lerna Monorepo

A brief description of how to start Lerna Monorepo in your project

1. create a monorepo folder
2. create folder for UI - 
	```npx create-react-app web-client```
3. create folder for APIs
4. Then install lerna 
	```npm i --g lerna and npm i -D lerna```
5. to initialize lerna firstly add 
	a) "workspaces": ["packages/*"] and then
	b)  npx lerna init
6. change version on lerna.json from 0.0.0 to 1.0.0
7. add below info in package.json
	"name": "root",
	"version": "1.0.0",
8. create packages folder if not created
9. drag web-client folder inside packages
10. create new folder inside packages with the name of server-api
11. then use ```npm init --yes```
12. create index.js and write basic code of api
13. in order to remove ```"node_modules"``` from ```"packages folder"``` but go to web-client folder and then use => ```npx learna clean -y```


## In order to start server with one command use below settings

1. go to "server-api folder" and in package.json add below command
```
scripts:{
	"start" : "node index.js", 
	"test" : "echo testing Node Server"
}
```
2. and in web-client folder ```package.json```
``` 
"test" : "echo testing React App"
```

3. Now go to root level ```package.json``` and add below commands
```
 "scripts": {
    "start": "lerna run start",
    "test": "lerna run test",
    "diff": "lerna diff"
  }
```
4. Now go to command prompt and run ```npm run start``` => both server will start

Note - if you face any issue for any dependency, use npm i on the root level

