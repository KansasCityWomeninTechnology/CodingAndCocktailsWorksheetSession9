# Part 2

1. Create a new file in _trivia-api_ and name it _server.js_.

2. Include the **cors** and **express** packages in our _server.js_ file.

  {% label %}Atom | server.js{% endlabel %}
  ```
  var cors = require('cors');
  var express = require('express');
  ```

3. Set `app` to an instance of `express` and set `port`

  {% label %}Atom | server.js{% endlabel %}
  ```
  var app = express();
  var port = process.env.PORT || 8080;
  ```

  The `process.env.PORT` will be populated by Heroku later and will fallback to `8080` locally.

4. Initiate router

  {% label %}Atom | server.js{% endlabel %}
  ```
  var apiRouter = express.Router();
  ```

5. Create your first route.

  {% label %}Atom | server.js{% endlabel %}
  ```
  apiRouter.get('/', function(req, res) {
    res.json({ message: 'hooray! your API is working!' });
  });
  ```

4. We're going to chain some methods

  {% label %}Atom | server.js{% endlabel %}
  ```
  app
    .use(cors())
    .use('/api', apiRouter)
    .listen(port, function() {
      console.log('API Magic happening on port ' + port);
    });
  ```

  Use cors package to enable all cors.  
  Use API router for any URL starting with `/api`.  
  Tell the app which port to listen to for API requests.

5. Fire up your server

  {% label %}CLI{% endlabel %}
  ```
  node server.js
  ```

  OR use the script

  {% label %}CLI{% endlabel %}
  ```
  npm run nm
  ```

  and any changes to code [when you save], will re-run the API with the changes

6. Open **Postman**

  1. Make sure **GET** is selected

  2. In the field that says **Enter request URL**, enter `http://localhost:8080/api`

  3. Hit **Send** button

7. [Answer key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-2)
