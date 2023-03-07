MVC -> MODEL VIEW CONTROLLER 

- CLASS SLIDES 
    - STEP ONE OF LEARNING TO USE REACT 
    - SEPERATION OF CONCERN 
        - DESIGN PRINCIPLE, SEPERATE THINGS BASED OF OFF WHAT THAT CODE IS DOING
            - IN A RESUTRANT, YOU HAVE CHEF, SERVER, AND CUSTOMER. WE DONT EXPECT A CUSTOMER TO GO A MAKE THE FOOD. MAKES SENSE TO SEPERATE THESE THINGS OUT. 
    - IT IS A FRAMEWORK IS AN ARCHITERURAL PATTERNT THAT ADHERES THE SEPRATION OF CONCERN PRINCIPLE
    - MVC STANDS FOR : 
        - MODELING THE DATA, DATA LAYER WHICH UPDATES THE VIEW
        - VIEW IS PRESENTATION, UI/UX PIECE
        - CONTROLLER HANDLE USER INPUT, GO DO A MODEL, GO SHOW THIS TO THE USER, RESPONSE TO USER INTERACTION
        - its the interface between Models and Views 
    - TEMPLETE ENGINE : 
        - PEICE OF SOFTWARE THAT COMPLIES DATA AND TEMPLATES TO GENERATE SOMETHING LIKE HTML, FEED DATA INTO HTML (IE, AT THIS LIST TAG STICK SOMETHING IN THERE)
        - PLACEHOLDERS FOR WHERE WE WANT TO PUT DATA 
        - FUCNTIONS
        - CONTIONAL RENDERING AND LOOPING 
        - TEXT REPLACEMENT 
    - ADVANTAGES 
        - MAKES JOBS EASIER 
    - HANDLEBARS.JS 
        - EXTENTION OF THE TEMPLATING LANGUAGE MUSTACHE 
        - LOGICLESS TEMPLATING LANGUAGE
            - INTENTIONALLY BAREBONES 
        - COMPLIES TEMPLATES SNIPPETS INTO ONE AND REPLACES VARIBALES WITH DATA 
        - JSUT THE BASICS, DO NEED TO EVENT HANDLE, OR LISTENING 
        - GREAT INTO TO TEMPLATE LANGUAGES, 
        - HOW CAN WE LEARN TO IMPLEMENT 
            - HELPING US BUIDING SOMETHING FROM SCRATHC, DEBUG A BROKEN APP, REVERCE ENGINEER BROKEN CODE.
        - {{{EXCECUTE FUNCTION}}}(3) VS {{VARIBALE}}(2)
    - WHAT THE MINI PROJECT WILL BE 
        - FUND MY PROJECT PAGE 
        - IT WILL REQUIRE A LOGIN AND PASSWORD, WHETHER TO SIGN UP OR LOGIN
    - WHAT WE WILL BE LEARNING THIS WEEK SUMMED UP :
        - ORGANIZATION OF CODE 
        - MVC 
        - HANDLEBARS.js

- QUICK NOTES: 
    - CONTROLLER, MODELS AND VIEWS IN SEPERATE FOLDERS 
        - MODELS HAVE SEQUELIZE 
        - CONTROLLERS IS BASICALLY SIMILAR TO ROUTES, WHEN I HIT THIS END POINT I WANT THIS TO HAPPEN 
        - VIEWS HOLDS OUT HTML 
        - SERVER.JS HANDELS OUR MIDDLEWARE
    - TEMPLATING IS...
        - HANDLEBARS.JS IS HELPING US TAKE OUR DATA, AND THEN PLACE IT INTO OUR HTML TO THEN VIEW
        - MAIN.HANDLEABRS IS THE TEMPLATE, THE ETC.HANDLEBARS IS ANOTHER TEMPLATE THAT WE STICK INTO MAIN, KEEPING THE SAME LAYOUT AND THEN CHANGING THE DATA INTO IT. MIAN IS THE ENTRY POINT FOR THE ETC FILE, HAS TO START AT MAIN. 
        - COOKIES - small files that websites put on your PC to store info about your preferences. (IE. A CART THAT YOU HAVE START TO PURCHASE BUT NOT CHECKED OUT)

- OVERALL CONCEPTS FROM EACH ACTIVITES

    - 01: 
        - SHOWS THE FILE SET UP, DESCRIBES IN FIRST NOTE OF QUICK NOTES
    - 02: 
        - IMPLEMENTATION OF MVC AND HANDLEBARS.JS, COMMENTING OUT DIFFERENT ASPECTS 
    - 03: 
        - IN THE DISH-ROUTES.JS ON LINE 44, WE CAN SEE (DISH/:NUM) ARRAY (WE ARE PUTTING IN THE NUMBER WHILE IN HTTP;LOCALHOST VIEW), AND FEED THAT INFO IN THE DISH_NAME OF THE DISH.HANDLEBARS FILE. WE ARE PUTTING IN ANY NUMBER FROM THE ORDER CAUSE WE SET THE PARAMS.NUM -1 CAUSE IT STARTS AT 0
    - 04: 
        - CREATE A ROUTER.GET(DISH/:NUM, (REQ,RES) => {}) ROUTE TO ALLOW DISH NAMES TO RENDER ON THE PAGE. 
        - RES.RENDER IS DOING THE JOB OF RENDERING THE STUFF ON THE MAIN.HANDLEBARS USING EXPRESS. 
        - LINES OF CONTROLLER/DISH-ROUTES 3,5 IS DOING THE SET UP TO CONNECT THE DOTS, 
        - 12,13 TURNS RES.RENDER INTO HANDLEBARS, RES.RENDER IS APART OF EXPRESS, OVERWRITING WITH THE HANDLEBARS BEHAVIOR, WITH THE SET UP, WE SAY WITH THE RENDER, DISPLAY WITH HANDLEBARS
    - 05: 
        - PLACEHOLDERS
        - CONTROLLERS HOLDS OUR ROUTE, PASSED IN OUR WHOLE DISHES OBJECT {DISHES: dishes} the same as {dishes}
        - *FOR YOU LOOP IN HANDLEBARS*
            router.get('/dish/:num', async (req, res) => {
                return res.render('dish', dishes[req.params.num - 1]);
                 for (const dish of dishes){
                   dish.id
                  }
                });
        *IS THE SAME AS*
            {{#each arrayWeWant as |currentItteration|}}
              //soemthing in here//
              <p>
              {{currentiteration.id}}.
              {{currentiteration.dish_name}}
              </p>
              //soemthing in here//
            {{/each}} 
    - 06: 
        - WORKED ON USING BUILT IN HELPERS https://handlebarsjs.com/guide/builtin-helpers.html#if
    - 07: 
        - BRINGING IN DATABASES AGAIN 
        - GRABBING INFO FROM DATABASE AND PLACES INTO OUR MVC FOLDERS AND PRESENTING EVERYTHING IN VIEW 
        - DISHDATA.GET({PLAIN: TRUE}) : FORMAT IS PLAIN, AND THUS TRUE. GIVING US STERILIZED DATA
    - 08: 
        - DEBUGGING, MAIN VIEW IS NOT DISPLAYING THE FOOD ITEMS WE WANT IT TO 
        - NEED TO "Build out this route so that it serializes all of the dish objects that it receives." IN DISH_ROUTES.JS
        - BUILD A LOOP FOR GETTING ALL DISHES, MAP ALL OF THEM, AND RETURN AN ARRAY, THEN RENDER DISHES
    - 09: 
        - HANDLING INPUTS FROM A FORM AND PLACING IT INTO A PREMADEHTML WITH {{DISH_NAME}}, {{DESCIRPTION}}, & {{GUEST_NAME}}
    - 10: SKIPPED, LOOK BACK ON THE SOLVED
    - 11: 
        - WENT OVER HOW YOU CAN INSERT TINY BIT SIZED PEICES OF INFO SO THAT ITS EASIER TO DIGEST. THESE ARE CALLED PARTIALS 
    - 12: 
        - SEEING HOW TO IMPLEMENT PARTIALS INTO OUR OWN HANDLEBARS FOLDERS. {{> partial_something}}, the > is using parsing, where once it reads ">" and then knows that after that character it knows that "partial_something" is a partial
    - 13: 
        - skipped, custom helpers
    - 14: 
        - skipped, custom helpers 
    - 15: 
        - SESSIONS, ALSO COOKIES, THIS WILL BE SAVING ACTIVITY LOCATED ON THE PAGE 
    - 16: 
        - WHAT WENT WRONG FOR ME WHEN STARTING: LOG IN STEPS
                - npm i 
                - node seeds/index.js 
                - then go in and souce the database and use the database we want 
        - req.session is a bucket that we can stick things in that will be avaliable for a user accross that session 
        - https://www.npmjs.com/package/express-session -> good link to info about express session 
            - we are using the package express-session
    - 17: 
        - connect session sequalize = new dependency which helps us track the session 
        - const sess = {
            secret: "super secret cookie", 
            cookie: {
                maxAge: 24 * 60 * 60 * 1000
            },
            resave: false, 
            saveUninitalized: false, 
            store: new SequelizedStore{
                db: sequelize
            }
        }; 
        - placing middleware in a new file and requiring it in our routes
    - 18: 
    - 19: 
    - 20: 
    - 21: 
    - 22:
        - SHOWING HOW TO DISPLAY SEQUELIZE DATA AND IMPLEMENT INTO THE HANDLEBARS 
    - 23: 
    - 24: 
    - 25: 
        - .eslintignore (E~S~lint)
            - similar to .gitignore
        - helps with debugging and displaying problems in the problems tab of the terminal
        - in package.json, there is a command line that you can run that will find the problems for you,
    - 27:
        - installing prettier 
            - npm install prettier eslint-config-prettier --save-dev
        - the rest of the settings to style prettier the way you like, there is a point where we introduce eslint to prettier, and how to make them not fight eachother by introducing them into each others .json's 
        - user settings 
         -> format
         -> on save 
    - 28: 
        - mini-project 
        - introduced full MVC framework 


CHALLENGE 
    - creating a work press site for any dev to use 
    - 
