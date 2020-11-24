# reverseEngineeringCode

# UNIT 14 Sequelize Homework: Reverse Engineering 

## USER STORY 
    -   AS A developer  I WANT a walk-through of the codebase  SO THAT I can use it as a starting point for a new project

## Passport Application
    -   This app is an authentication application
    -   This app enables you to signup, login, and logout to the passport authenticatio system.
    -   This app stores the data in MYSQL DB.
    -   This app provides a secure way to login and logout from a system

## Library used
    -   Node JS
    -   Express JS
    -   Express Session [Link https://www.npmjs.com/package/express-session]
    -   MYSQL DB
    -   PASSPORT [Link https://www.npmjs.com/package/passport]
    -   SEQUELIZE [Link https://www.npmjs.com/package/sequelize]

## Technologies used
    -   Node JS
    -   Express JS
    -   Passport
    -   MySQL DB
    -   ORM (sequelize)
    -   HTML
    -   JAVASCRIPT

## GETTING STARTED
    -   1. clone the repository using command git clone GIT_REPO_URL.git
    -   2. install MySQL DB
    -   3. create DB `passport_demo`
    -   4. update database username and password in config/config.js
    -   5. install node dependencies by running command `npm install`
    -   6. start the application with `npm start`
    -   7. go to http://localhost:8080 to use the application

## FILES
.
        ├── Develop
        │   ├── config
        │   │   ├── config.json
        │   │   ├── middleware
        │   │   │   └── isAuthenticated.js
        │   │   └── passport.js
        │   ├── models
        │   │   ├── index.js
        │   │   └── user.js
        │   ├── package.json
        │   ├── package-lock.json
        │   ├── public
        │   │   ├── index.html
        │   │   ├── js
        │   │   │   ├── login.js
        │   │   │   ├── members.js
        │   │   │   └── signup.js
        │   │   ├── members.html
        │   │   ├── signup.html
        │   │   └── stylesheets
        │   │       └── style.css
        │   ├── routes
        │   │   ├── api-routes.js
        │   │   └── html-routes.js
        │   └── server.js
        ├── README.md
        └── Unit 14 Sequelize Homework.docx

        8 directories, 19 files

## config
    -   config.json : the file use to configure the database details.
    -   passport.js : this file used the passport package of Node JS. We are using authentication with a passport. It has many strategies and we are using Local Strategy i.e  Telling passports we want to use a Local Strategy. In other words, we want login with a username/email and password

    -   models/index.js and models/user.js files are required by passport.js

    -   isAuthenticated.js the file used to check if a user/request is authenticated .i.e the user already logged in and session is active and has not yet logged out.


## MODELS
    -   index.js : The Index model used to connect to DB and query USER data.
    -   user.js : The User model used for each member. This model is serialized to save to DB and de-serialize to use for the application. We are using the bcrypt package to encrypt the password before saving it to DB.

    -   config.json file is required by these js files.

## Routes
    -   We have two routes defined 
        - html-routes.js:  one for html-routes.js which is used to return views based on url and login status of the member.
        - api-routes.js : the api-routes.js is used for API authentication from any third party apps etc.
        - If a user is logged in then we show the member view with logout action.
        - If a user is not logged in we show login /signup based on request             
 
## SERVER.js
    -  server.js: This is the main file which configure almost everything all configs, PORTS and middlewares routes syncs database etc.
    -  server.js : this is the main js file which combines everything and starts the server.
    This file requires  passport.js
    this file requires models/index.js
    this file requires models/user.js
    this file requires routes/html-routes.js
    this file requires routes/api-routes.js

## PUBLIC 
    -  	This folder contains the html views and respective js file and css.

### js: 
    -   login.js - this will call the login api on click of button on submit and if success redirect to members page
    -   members.js - this will call the logout api and logout a user and show the login page
    -   signup.js - this will call the signup api and create a user and logged in and show the member page.

### html : 
    -   index.html : this is default view of login screen
    -   members.html : this is logged in view . if we want to add anything to logged in view we will edit this file.
    -   signup.html : this is a signup view. if we want to edit or add new fields in signup we will edit this page for signup view.
    
    -   All these files depend on style.css and login.js members,js and signup.js files.
	-	To create more HTML files, we will need to create a JS and add the files to the route.

### CSS:
    -  style.css : this is style for the app. if we want to change color or appearance and override existing style we will edit this file. 
           
## ORM
    -  We are using npm package sequelize for the ORM (Object Relational Mapper) which can sync DB and serialize and deserialize the User Data from DB to user and from user to DB.

## Package.json
    -  This is a node package manager config file.
    -  If we want to edit any version of dependencies or add new dependencies we will edit this file. The file is auto generated if we use npm.



