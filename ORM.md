ORM (OBJECT RELATIONAL MAPPER) NOTES -> 

- ASYNC + AWAIT 
    - can have await functions with multiple awaits in then 
    - try -> away 
      catch -> error 
    - 12/Unsolved/Routes/API/userroutes
        great place to look at updated get/update/delete methods using what we know right now
    - work on 14 on our own 
    - best to make a burner email and password 


- CLASS SLIDES 
  - lean heavily on object orientated programming in ORM. 
      - OOP = programming paradign based on the concept of "objects", which can contain data and code: data in the form of fields, and code and form procedures. 
          1. everything is organised using objects instead of functions
          2. objects can inhereit properties and methods from other objects 
          3. multiple objects can be created from the same blueprint classes or conductor functions 
  - ORM will try to translate the data models and tables and turn them into class/objects in javascript which are easier to read.
  - Sequlize is the lirbary that does the translation for us (object relational mapper) and it is installed with npm 
      1. sequalize allows you to model your data as javascript classes 
      2. it abstracts SQL queries into simpler object methods 
      3. provides built in validation checks for securing data
      4. makes it easier to visualize and join relational data 
  

  - HOW TO SET UP SEQUILIZE 
    1. npm i --save mysql2@2.2.5
    2. npm i --save sequelize@6.3.5
    3. and also add in express
    (there is also npm i --save-dev example@1.1.1, and this will save it in your devDependences instead of regualar)
    4. you will add this connect in your connection.js file, or even your server.js, this is called a connection object, the capital S Sequelize is for classes. after the database, root, and password, it is an object 
       1.  
        const Sequelize = require('sequelize');
        
        cosnt sequelize = new Sequelize(        
          'example_db', 
          'root', 
          'password',
           {
            host: '127.0.0.1', 
            dialect: 'mysql', 
            port: 3306
           }
        );

        module.exports = sequelize
    
        and then in your server.js file, you will import it 
       2. 
        and then in your server.js file, you will import it using: 

        const sequelize = require('./config/connection'); 
      
       3. 
        then you will import this notation, this is basically saying sync up with the database(lay of the land). 
        
        sequelize.sync().then(() => {
          app.listen(PORT, () => console.log("Now listening"));
          )}; 

      4. source the schema.sql using => SOURCE schema.sql in mysql
      5. run => npm start in your terminal 



  - CONCEPTS FROM EACH VIDEO 

    - 01: how to set up sequelize and get listening on a port to look at a specific database 
    - 02: 