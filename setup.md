# Directions to setup and run the application
---
## Setup Environment
Follow the below steps to run the costume designing web application:
1.	Clone this repository to your local machine or just download the zip folder,
 https://github.com/vijaythecoder/c-g-coatings-estimator-api
2.	Node and npm package manager is prerequesite
3.	Run npm install to install all the dependencies in the package.json file once before you begin, and as new dependencies are added.
```	
npm install
```
4.	In the terminal in Visual studio or in command prompt install Adonis CLI by using this coomand 
```
> npm i -g @adonisjs/cli
```
5.	Setup your MySQL database and if it is first time to create your database run your migrations by using command 
```
Adonis migration:run
```
---
## Run the application

1.	If it is first time we need to set the development environment first create a .env file and the copy existing. env.example file. This will set your run time environment 
2.	Run the app in the terminal inside the application where package.JSON file exists 
```
> adonis serve --dev
```

Your Application will be opened in the default browser.

