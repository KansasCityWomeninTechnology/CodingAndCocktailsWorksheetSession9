# Part 3: Using API Data

1. In _trivia-api_ directory, create a folder named _app_.

2. In _app_, create a folder named _routes_.

3. In _app/routes_, create 2 files: _index.js_ & _quiz_routes.js_.

4. Open  _app/routes/quiz_routes.js_ in Atom & add:

  {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
  ```
  var express = require('express');
  var apiRouter = express.Router();

  // Replace with route

  module.exports = apiRouter;
  ```

5. Let's move our original route from _server.js_ to _quiz_routes.js_.

  Copy [& delete] the route you added in _server.js_ and paste it in _quiz_routes.js_ [look for the comment `Replace with route` for where to place it].

  _quiz_routes_ should look like the following:

  {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
  ```
  var express = require('express');
  var apiRouter = express.Router();

  apiRouter.get('/', function(req, res) {
    res.json({ message: 'hooray! your API is working!' });
  });

  module.exports = apiRouter;
  ```

  Notice the code is indented and there are blank lines above and below the route, to make the code easier to read.

6. Open  _app/routes/index.js_ in Atom & add the following:

  {% label %}Atom | app/routes/index.js{% endlabel %}
  ```
  var quizRoutes = require('./quiz_routes');

  module.exports = function(app, db) {
    app.use('/api', quizRoutes);
    // Other groups of routes could go here some
  };
  ```

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
