# Part 3: Using API Data

1. In Atom, right click on the left side Project pane and pick "New Folder".  Name the new folder _app_.

2. Right click on the newly created _app_ folder and pick "New Folder". The prompt for the folder name should already show `app/`.  Name the new folder _routes_.

3. Right click on the newly created _app/routes_ folder and pick "New File.  Name it _index.js_ & repeat to also create a file named _quiz_routes.js_ in the _app/routes_ folder.

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

  Notice the `res.json` code is indented and there are blank lines above and below the route, to make the code easier to read and maintain.

6. In Atom, double click on the _app/routes/index.js_ file in the left side Project pane to open it.  

7. In _app/routes/index.js_, create a variable named `quizRoutes`.

8. In the same way that you require in packages, you can require in other files from your own project as long as they're exporting something.  Note the `module.exports = apiRouter;` code at the bottom of _app/routes/quiz_routes.js_.

  Set the value of the `quizRoutes` variable to require in the _app/routes/quiz_routes.js_ file.  
  
  In order to tell the require statement where to look for the file (in the same directory where the _index.js_ file is located) use `./`. To learn more about file paths read [HTML File Paths on w3schools](https://www.w3schools.com/html/html_filepaths.asp).  File paths are the same across JavaScript, HTML, CSS, and in the command line (Git Bash or iTerm2). 
  
  If you're stuck here grab a mentor or open up the hint section below by clicking on the arrow (^) below for more detail.

  <!--sec data-title="Hint" data-id="section0" data-show=true data-collapse=true ces-->
  {% label %}Atom | app/routes/index.js{% endlabel %}
  ```
  var quizRoutes = require('./quiz_routes');
  ```
  <!--endsec-->

9. Now we'll export a function to tell the app to use the `quizRoutes` router for the `/api` route

module.exports = function(app, db) {
app.use('/api', quizRoutes);
// Other groups of routes could go here some
};



  

7. We need to incorporate our new routes placement in _server.js_.

  1. Before the chained methods on `app`, import the new routes folder.

    {% label %}Atom | server.js{% endlabel %}
    ```
    require('./app/routes')(app, {});
    ```

  2. Then we need to remove a couple of things that we now use in _app/routes/index.js_ or _app/routes/quiz_routes.js_. Remove the following lines:

    {% label %}Atom | server.js{% endlabel %}
    ```
    var apiRouter = express.Router();
    ```

    {% label %}Atom | server.js{% endlabel %}
    ```
    .use('/api', apiRouter)
    ```

8. Use Postman to make sure your route still returns a response at `http://localhost:8080/api` [Make sure node server is still running.]

9. Let's add a new route & serve a static JSON file for the response.

  1. Create a new file in the _app_ folder and name it _quiz_fixture.js_.

  2. Copy all the contents from [this file](https://github.com/KansasCityWomeninTechnology/trivia-api/blob/answer-key-part-3/app/quiz_fixture.js) & paste into _quiz_fixture.js_.

  3. Import this new file into the _app/routes/quiz_routes.js_ file:

    {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
    ```
    var sampleQuiz = require('./../quiz_fixture.js');
    ```

  3. Add this new route to _app/routes/quiz_routes.js_.

    {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
    ```
    apiRouter.get('/sample', function(req, res) {
      res.json(sampleQuiz);
    });
    ```

10. Use Postman to hit your new endpoint `http://localhost:8080/api/sample`.

11. [Answer Key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-3)
