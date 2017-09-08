# Part 3: Using API Data

1. In Atom, right click on the left side Project pane and pick "New Folder".  Name the new folder _app_.

2. Right click on the newly created _app_ folder and pick "New Folder". The prompt for the folder name should already show `app/` (Mac) or `app\` (Windows).  Name the new folder _routes_.

3. Right click on the newly created _app/routes_ folder and pick "New File".  Name it _index.js_ & repeat to also create a file named _quiz_routes.js_ in the _app/routes_ folder.

4. In the left side Project pane, double click on the _app/routes/quiz_routes.js_ file to open it for editing and in the file, type: 

  {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
  ```
  var express = require('express');
  var apiRouter = express.Router();

  // Replace with route

  module.exports = apiRouter;
  ```
  
  Similar to what we did in Part 2, this code is requiring in the express package and creating an instance of the router here.

5. Next, move the original route from _server.js_ to _quiz_routes.js_.

  1. Cut (Windows: `ctrl` + `x`, Mac: `cmd` + `x`) the route you added in _server.js_ (that's the entire `apiRouter.get...` section).
  
  2. In _quiz_routes.js_, look for the comment `Replace with route` that you wrote and select it.
  
  3. Paste (Windows: `ctrl` + `v`, Mac: `cmd` + `v`) the code that you cut from _server.js_ there.  

    _quiz_routes.js_ should look like the following:

    {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
    ```
    var express = require('express');
    var apiRouter = express.Router();

    apiRouter.get('/', function(req, res) {
        res.json({ message: 'hooray! your API is working!' });
    });

    module.exports = apiRouter;
    ```

    {% hint style='info' %}
Notice the `res.json` code is indented and there are blank lines above and below the route, to make the code easier to read and maintain.
    {% endhint %}

6. In Atom, double click on the _app/routes/index.js_ file in the left side Project pane to open it.  

7. In _app/routes/index.js_, create a variable named `quizRoutes`.

8. In the same way that you require in packages, you can require in other files from your own project as long as they're exporting something.  Note the `module.exports = apiRouter;` code at the bottom of _app/routes/quiz_routes.js_.

  Set the value of the `quizRoutes` variable to require in the _app/routes/quiz_routes.js_ file.  
  
  {% hint style='tip' %}
In order to tell the require statement where to look for the file (in the same directory where the _index.js_ file is located) use `./`. 

To learn more about file paths read [HTML File Paths on w3schools](https://www.w3schools.com/html/html_filepaths.asp).  File paths are the same across JavaScript, HTML, CSS, and in the command line (Git Bash or iTerm2). 
  {% endhint %}
  
  If you're stuck here grab a mentor or open up the hint section below by clicking on the arrow (^) below for more detail.

  <!--sec data-title="Hint #1" data-id="section0" data-show=true data-collapse=true ces-->
  {% label %}Atom | app/routes/index.js{% endlabel %}
  ```
  var quizRoutes = require('./quiz_routes');
  ```
  <!--endsec-->

9. Now we'll export a function to tell the app to use the `quizRoutes` router for the `/api` route.  We'll then be able to import this for use in another area of this application. 

  1. With your cursor at the end of the line importing the `quiz_routes` module, press enter twice.

    This will add a blank line to increase the code readability and then give us space to add the next block of code. 

  2. Type `module.exports =` This is necessary to export a module (or small block of code) and set it to what you want to export as your module to use in another area of your application. 
  
    {% hint style='info' %}
Keeping code modularized allows for:
* A more organized application
* Easier troubleshooting
* Isolation of pieces of code from eachother
* Easier testing of specific areas of code  


**Caution**: There is some difference in JavaScript written on the server side in Node.js. `module.exports` is one example that is only available in the server-side Node environment.  This is not natively available in your browser (Google Chrome, Microsoft Edge, Firefox, etc) so without additional tools like Webpack or Browserify you wouldn't see this in client-side/front-end JavaScript code.
    {% endhint %}
   
  3. We want to export a function here.  Do you remember what a function structure looks like? Give it a try and then expand the section below by clicking on the arrow (^) to expand the section and check yourself. This function should take two parameters: `app` and `db`.
  
    <!--sec data-title="Hint #2" data-id="section1" data-show=true data-collapse=true ces-->
      {% label %}Atom | app/routes/index.js{% endlabel %}
      ```
      module.exports = function(app, db) {

      };
       ```
    <!--endsec-->

  4. In the body of that function (that means inside the opening and closing curly braces `{}`!), type `app.use('/api', quizRoutes);`. 
  
    You could also add other groups of routes in this same area but this is all we'll be using in this application.  

10. Now that we've rearranged the routes, we need to incorporate them in _server.js_.

  1. In Atom, open the _server.js_ file.  Before the chained methods on `app`, import the new routes folder on it's own line surrounded by blank lines to help increase readability. 
    {% label %}Atom | server.js{% endlabel %}
    ```
    require('./app/routes')(app, {});
    ```

  2. Next, cleanup a couple of things that we now use in _app/routes/index.js_ or _app/routes/quiz_routes.js_. Remove the following lines:
    {% label %}Atom | server.js{% endlabel %}
    ```
    var apiRouter = express.Router();
    ```
    {% label %}Atom | server.js{% endlabel %}
    ```
    .use('/api', apiRouter)
    ```
    
  3. Save your files.

11. In Git Bash or iTerm2, make sure your server is still running.  If you need to restart type `npm run nm`.  To cancel hit the `ctrl` + `c` keys.

12. In Postman, make sure your route is still set to `http://localhost:8080/api`, the verb is still set to GET and press the "Send" button.  Make sure you still get a response here.  If you don't get a response, try to troubleshoot or grab a mentor for some help! 

  <!--sec data-title="Chromebooks Only: Cloud9 Instructions" data-id="sectionPostman9" data-show=true data-collapse=true ces-->
1. If you still have your tab open, just go to it and refresh the page to ensure your data still shows.
  
2. If you need to re-open your application, open a new tab and navigate to http://< your-workspace-name-yourusername>.c9users.io:8080/api
  
3. You should see the `"message": "hooray! your API is working!"` data returned from your API in the browser screen
  <!--endsec-->
  
16. Let's add a new route & serve a static JSON file for the response.

  1. In Atom, in the left side Project pane, create a new file in the _app_ folder and name it _quiz_fixture.js_.

  2. Copy all the contents from [this linked file](https://github.com/KansasCityWomeninTechnology/trivia-api/blob/answer-key-part-3/app/quiz_fixture.js) & paste that content into _quiz_fixture.js_.

  3. Import this new file into a variable named `sampleQuiz` in the the _app/routes/quiz_routes.js_ file.  If you need further hints open the section below by clicking on the arrow (^) to open.
  
      <!--sec data-title="Hint #3" data-id="section3" data-show=true data-collapse=true ces-->
        {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
        ```
        var sampleQuiz = require('./../quiz_fixture.js');
        ```
      <!--endsec-->

  4. Add this new sample quiz route to _app/routes/quiz_routes.js_ below the root route `/` function with a blank line separating them for readibility.
  
    {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
    ```
    apiRouter.get('/sample', function(req, res) {  
        res.json(sampleQuiz);
    });
    ```
    
17. In Postman, update your route to the one you just added `http://localhost:8080/api/sample`, the verb should still be set to GET and press the "Send" button.  Make sure you get a response here.  If you don't get a response, try to troubleshoot or grab a mentor for some help! 

  <!--sec data-title="Chromebooks Only: Cloud9 Instructions" data-id="sectionPostman2" data-show=true data-collapse=true ces-->

  1. If you still have your tab open, just go to it, add `/sample` to the end of the URL and press enter.
  
  2. You should see the new data from _quiz_fixture.js_ returned from your API in the browser screen
<!--endsec-->

15. Check your code with the [Part 3 Answer Key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-3).
