EXPRESS NOTES 

DAY 1 -> 

    CLASS NOTES 
        - Express is primary server frame work
        - built on top of node.js (which is how we run java outside the browser)
        - build server side APIs 
        - lightweight framwork for node.js that allows you to write APIs, handle http requests, and implement middleware into your server-side applications 
        - backend 
        - what is a route??
            - a lot like traffic lanes, they allow us to send http methods 
            - https methods include get, post, put, delete 
        - REST API -> representational state transfer, arch for creating web service like API 
        - app.post example (callback functions)
            - app.post ('/api/reviews', (req, res) => {
                const newReview = req.body 
                writeToFile(destination, newReview)

                res.json('${req.method} recieved!');
             }); 
        - how does this relate to the front end? 
            - we can fetch from our own APIs
        - EADDRINUSE 
            - this could mean that you have another temrinal running in the background thats already using localhost with whatever port you chose. 
        - DOMAIN: http://localhost:3003/ 
        - you should understand a req and res is 2 halves of something you have to have. if a request is sent and nothing is sent back then that would tell you you have an error. 
    

    HOW TO GET STARTED 
        - you will beign with making sure you have the updated express in your package.json by running npm i (npm install)
        - then you will start the server and import express 
            const express = require('express');
            const path = require('path');
                - module from node, allows us to pay attention to specific places in our file system 
            const app = express();
                - use app to define the routes 
            const PORT = 3001; 
                - different programs can run on different ports, window into computor 
        - THEN use node filename.js, and this will allow you to listen on the port 



    MIDDLEWARE 
        - used to serve up static files 
            - app.use(express.static("public"));
        - used on 09, under server.js, this is where we implied middleware to say anything that is in that public folder you can just turn around and serve up, so all the routes in publics will be create and we can go through all of them without having to create each round for example in the server-static.js
        - called middleware becaue its saying before any of the routes are created, go through this middleware(for example kanye interuppting taylor swift at the grammys), 
            - (req, res, next) ... 
        - EXPRESS.JSON, I WANT SOME JSON BACK, IT WILL HANDLE THAT USECASE  
        - there is also express.urlencoded, this parses the incoming request with urlencoded data



    EXAMPLES USING THE CALLBACK FUNCTIONS, GET + POST + DELETE ARE ALL METHODS OF POST REQUESTS
        - EXAMPLE WITH APP.GET
            app.get("/send" (req,res) => {
                res.sendFile(path.join( __dirname, "public/sendfile.html"))
            })
                - when someone used get and then /send, we want to send a file with (.sendFile) then path module will the join with "__dirname" (which will tell you the current directory you are in and then add "public/sendFile.html)
                - you can do the same thing with "/routes"
        - EXAMPLE WITH APP.LISTEN
            app.listen(PORT, () => {
                console.log('App is listneing on port http://localhost:${PORT}')
            }
        - EXAMPLE WITH APP.GET, RES.SEND, SEND CHUNCKS OF HTML IN THE RESPONS 
            app.get('/' (req, res) => {
                    res.send('<p> API ....')
            }); 
        - EXAMPLE USING RES.JSON TO EXPECTJSON AND USE IT AS JSON (HEADERS), ALSO USE WHEN YOU CREATE YOUR OWN API 
            app.get('/api' (req, res) => {
                    res.json({
                        term: "api",
                        description: "aonjuifcbsnoja;v" 
                    });
            }); 
        - localhost:3001/api/terms/?key=value 
            - key=value - query parameters
            - these will automatically trans by express,on req obj at req.query 
        - differnce in term and category 
        - post requests are used for when you want to create something new, "post it to that endpoint" 
        - to add a new post method to a string, not just code over it but add ANOTHER ONE, you will (20-STU-DATA-PERSISTENCE)

            fs.readFile('./db/review.json', utf8, (err, data) => {
                if (err) {
                    console.error(err)
                } else {
                    const parsedReviews = JSON.parse(data);
                    parsedReviews.push(newReview);
                
            const reviewString = JSON.stringify(parsedReviews, null, 2);
            
            fs.writeFile('./db/review.json', reviewString, (err) => 
                err 
                ? console.error(err)
                : console.log(
                    'Review for #{newReview.product} has been written to JSON file'
                )
            );
        }
    });

    INSOMNIA 
        -  used to call API without having to use the browser
        - "a lot less annoying" - grady 
        - clean enviorment to only test your API, clean way to view

    

    ***ALL ACTIVITY NOTES ARE IN THE SPECIFIC ACTIVITIES IN EITHER SOLVED OR UNSOLVED IN UPPERCASE***



    OTHER 
        - TERMS.JSON ON ACTIVITY 6 HAS A LOT OF GOOD TERMS TO LOOK AT 
