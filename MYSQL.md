<!-- CLASS 2/13 -> mysql  -->

-- SQL query interacts with a database, using th enames of tables, coloumns and relationships between the tables 

COMMAND LINE COMMANDS 
- to login : this will prompt the password 
    -- mysql -u root -p 
 
- create database 
     -- CREATE DATABASE example;

- to drop a database 
    -- DROP DATABASE IF EXISTS example.sql;

- touch on an existing file 
     -- SOURCE example.sql;

- using this command opens the file, same thing as touch, but you still need to open and then edit it, to USE will allow prompt you with database changed
    -- USE example.sql;

- to show databases 
    -- SHOW example.sql/db;
- and then to show all of them 
    -- SHOW DATABASES; 

- to select/show in the command line,
    -- select database();  

- create a table (INT is interger, same as number, only whole) (VARCAR is varibale characters)
    -- CREATE TABLE example (
        -- id INT, 
        -- name VARCHAR(100) 
        -- );

- to show the tables 
    -- SHOW tables; 

- to grab info from a table (* = all)
    -- SELECT * FROM produce 

    OR 

    -- SELECT name FROM produce 

- to tell whats inside 
    -- DESCRIBE produce; 

- to insert into produce for example 
    -- INSERT INTO produce (id, name)
        -- VALUES (1, "apple"); 

    OR 

    -- INSERT INTO produce (id, name)
        -- VALUES 
            (1, "apple")
            (2, "banana")
            (3, "orange"); 

- how to delete data 
    -- DELETE from produce 
        -- WHERE id = 2; 

- to update a table, you can do multiple, this is where you would put the commas between them 
    -- UPDATE produce 
        -- SET name = "strawberry"
        -- WHERE id = 1; 

- to count the nunber of rows 
    -- SELECT COUNT(*) from example; 

- to create primary and foregin keys 
        CREATE TABLE instructors (
            id INT NOT NULL,
            first_name VARCHAR(30),
            last_name VARCHAR(30),
            <!-- PRIMARY KEY (id) -->
        );

        CREATE TABLE courses (
            id INT,
            course_title VARCHAR(30) NOT NULL,
            instructor_id INT,
            order_details TEXT,
            <!-- this will be referencing the primary key we made in the instructors table-->
            <!-- <!-- FOREIGN KEY (instructor_id) REFERENCES instructors(id) ON DELETE SET NULL -->
        );
   
- JOIN(s)
    --  select all FROM (a) JOIN (b) ...(need to be continued )



GENERAL NOTES: 
    -- it is convention to write all command functions in UPPERCASE, commands in caps (SOURCE) and requests are in lowercase (sample_db)  
    -- would run it once at the begining of a project to set everything up then you would run API calls from on there 
    --  CRUD 
        create
        read 
        update 
        delete 
    -- schema.sql is basically the whole database file 
    -- the seeds.sql is all the insert a lot of data into a row, primarily used in a developmental enviorment 
    -- 127.0.0.1 is basically local host/computors home address. 
    -- WE USE THIS 'DROP DATABSE IF EXISTS' SO WE DO NOT CREATE ANOTHER DATABASE OR ERROR OUT 
        DROP DATABASE IF EXISTS
