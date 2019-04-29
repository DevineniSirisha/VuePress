# Structure of the application
---

- **app:**
 The app folder consists of the Controllers, Models, Exceptions, Listeners and middleware      
- **Controllers:** Adonis provides two types of controllers HTTP and Websocket. Mostly we use HTTP for to talk to server-side API’s and fetch and update data to MySQL Database.
```
adonis make:controller controllerName
```
- **Exceptions:** Adonis provides special object to handles all the exception in a single folder called exceptions
```
adonis make:Exception exceptionName
```
- **Listeners:** They are used to listen to the used to get the API’s from Mail service etc.
- **Middleware:** Provide a convenient mechanism for filtering HTTP requests entering your application. For example, Adonis includes a middleware that verifies the user of your application is authenticated.
- **Models:** In Models we create what kind of data we need and create models for each and relate them. We can restrict or validate the data we need here once data is received to the model it checks the restrictions and act accordingly.
```
adonis make:Model ModelName
```	
- **Config:** Configuration files are provided by Adonis and they are used to set what type we want to use like In Auth.js they provide code for all kind of authentication we can choose any and change according to our requirement. 
- **Database:** In Database we have migrations and seeds 
- **Migration:** migrations are used to define schemas like what type of datatype for each entity  we need in each table 
```
adonis make: migration migrationName 
```
- **Seeder:** Seeders are used to create sample data for existing models and how many samples we need.
```
adonis make:seed seederName
```
Adonis seed seederName to get sample data of particlur seed.
Adonis seed to get sample data of all seeders defined
- **Factory.js:** This is used to define sample data in general terms like name, number, address etc. Based on these changes sample data is created
- **Resources:** They have all the views and Adonis use Edge template engine. So all views are with .edge extentions.
Start It has routes.js Where we define the routes for each URI and connect them to the Controller to handle the Events.
- **Test:** Test folder has all the test files. Adonis provides different kinds of testing like unit and functional Create a text file by typing 
```
adonis make: test operations
```
Adonis test is used to run the test environment.

