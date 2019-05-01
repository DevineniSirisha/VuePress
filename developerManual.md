# Developer Manual
Developer’s Manual

Contents:
1.	Prerequisites
2.	Tools/services used
3.	Directions to set up a development environment
4.	Directions to run the code for testing

Prerequisites:
Platform: Node.js 
Package Manger: npm 
Framework: Adonis CLI
Version Control System: Github
Database: MySQL 
Database viewer: MySQL workbench or SQL pro
Mail Service: Mailgun account
Deployment: Heroku account.

Tools/services used:
The cost estimating app needs the following:
•	Node.js platform: It is an open source, cross-platform, JavaScript server-side environment. Node.js runs single-threaded, non-blocking, asynchronously programming, which is very memory efficient. It enables to work both frontend and backend on Java Script.
•	Adonis web framework: AdonisJs is a Node.js MVC framework that runs on all major operating systems. It offers a stable ecosystem to write server-side web applications. It provides services like BodyParser (Parse HTML request body), Lucid (SQL ORM). It also brings MVC design structure to the project.
•	Edge templating engine: It enables you to write most of the JS expressions to make pages more dynamic and its main usage is to render the data and template into HTML.
•	Bulma framework: It is the CSS framework and it is used to create, and JavaScript framework for developing responsive websites.
•	Lodash for JavaScript object iteration and manipulation: A modern JavaScript utility library delivering modularity, performance.
•	Bodyparser: Body parser is used to get the data from html form read the data and save them to the data base.
•	Mailgun: It is an API for node.js to send the mails.
•	MySQL: It is a cross-platform Structured database program. 
MySQL:
1.	Go to link https://dev.mysql.com/downloads/installer/  for windows or mysql home page and download and install right version for your Operating system. Set the password for your root directory while installing. 
2.	Once MySQL is installed we need workbench, XAMPP etc. to view the database and create one. So download SQL Workbench or XAMPP or SQL pro which you are familiar with. 
3.	Once installed, open MySQL workbench from windows start and create a new scema .  
4.	Name the database as adonis or accordingly to the DB name in your environment 
5.	Once database is set there is problem with mysql encryption version as node and mysql are implementing different version type this command and reset the password.
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password'

6.	Now open the project and install mysql in node by typing npm install mysql.
7.	Now run your migrations in your terminal Adonis migration:run. For existing DB use Adonis migration:refresh
8.	This will create tables the existing database named Adonis. Make sure the database name is adonis and password is password as we reset it to password.
9.	Now You can view all the tales in the workbench.

Mailgun API:
1.	Signup for new account at https://www.mailgun.com/.

 









2.	Complete the verification by clicking a link which is e-mailed to your email account.


3.	You will have to set some security such as Two factor authentication (2FA) and a new password for SMTP.
4.	Click on the domain on the dashboard which starts with “sandbox”.
5.	Click on the API as you wish to use API to send emails.
6.	Select the language you are using. (E.g. Node.js) 
7.	Now the API KEY is generated, COPY the API KEY and DOMAIN.

 

8.	You should add the authorized recipients and complete verification process.

  

9.	You can also add a list of your contacts to notify all of them at once.

 





10.	Now copy the route code of mailgun in to your routes.

 

11.	Now, put your API key and DOMAIN URL in the code.
 


12.	Add From & To address in the route code.
13.	That’s it! You should be able to send email now.



Heroku:
1.	Create a Heroku account on https://www.heroku.com.
2.	Click on create new app button.
 
3.	Connect to GitHub and make sure the GitHub repository is not a cloned version. 
 

4.	Click on Authorize Heroku to access GitHub.
 
5.	Search for the repository and connect.
 
6.	Click on Enable Automatic Deployment.
 
7.	Open the app by pressing Open App button on the top-left corner.

Tools used for editing and building the code:
•	MS Visual Code: It includes support for debugging, embedded Git control, syntax highlighting, intelligent code completion.
•	Command Panel: Used for running the commands that makes the application run. It supports the Linux commands.
Directions to setup environment:
Follow the below steps to run the costume designing web application:
1.	Clone this repository to your local machine or just download the zip folder,
-	https://github.com/vijaythecoder/c-g-coatings-estimator-api
2.	Node and npm package manager is prerequesite
3.	Run npm install to install all the dependencies in the package.json file once before you begin, and as new dependencies are added.
	npm install
4.	In the terminal in Visual studio or in command prompt install Adonis CLI by using this coomand 
	> npm i -g @adonisjs/cli
5.	Setup your MySQL database and if it is first time to create your database run your migrations by using command 
	Adonis migration:run
6.	

Directions to run the code for testing
1.	If it is first time we need to set the development environment first create a .env file and the copy existing. env.example file. This will set your run time environment 
2.	Run the app in the terminal inside the application where package.JSON file exists 
	> adonis serve --dev

Your Application will be opened in the default browser.
The structure of application:
- 	app – The app folder consists of the Controllers, Models, Exceptions, Listeners and middleware      
Controllers: Adonis provides two types of controllers HTTP and Websocket. Mostly we use HTTP for to talk to server-side API’s and fetch and update data to MySQL Database. 
adonis make:controller controllerName
Exceptions: Adonis provides special object to handles all the exception in a single folder called exceptions
adonis make:Exception exceptionName
Listeners : They are used to listen to the used to get the API’s from Mail service etc.
Middleware:  Provide a convenient mechanism for filtering HTTP requests entering your application. For example, Adonis includes a middleware that verifies the user of your application is authenticated.
Models : In Models we create what kind of data we need and create models for each and relate them. We can restrict or validate the data we need here once data is received to the model it checks the restrictions and act accordingly
adonis make:Model ModelName
	
- Config: Configuration files are provided by Adonis and they are used to set what type we want to use like In Auth.js they provide code for all kind of authentication we can choose any and change according to our requirement. 
Database : In Database we have migrations and seeds 
Migration: migrations are used to define schemas like what type of datatype for each entity  we need in each table 
Adonis make: migration migrationName 
Seeder : Seeders are used to create sample data for existing models and how many samples we need.
adonis make:seed seederName
Adonis seed seederName to get sample data of particlur seed.
Adonis seed to get sample data of all seeders defined
Factory.js : this is used to define sample data in general terms like name, number, address etc. Based on these changes sample data is created
Resources: They have all the views and Adonis use Edge template engine. So all views are with .edge extentions.
Start It has routes.js Where we define the routes for each URI and connect them to the Controller to handle the Events.
Test folder has all the test files. Adonis provides different kinds of testing like unit and functional 
Create a text file by Adonis make: test operations
Adonis test is used to run the test environment.

