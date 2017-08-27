# Part 2

1. In Atom, right click anywhere on the left side section of the screen where the `trivia-api` folder and the `package.json` file are displayed. 

2. Select `New File` and name it _server.js_.

3. In order to use a package in your project, you must require it in to the file you want to use it in. Typically you set a variable equal to this require statement to give it a place from which the package can be used and accessed.

  Utilize the **cors** and **express** packages in the _server.js_ file by adding the following two lines to the top of the _server.js_ file:

  {% label %}Atom | server.js{% endlabel %}
  ```
  var cors = require('cors');
  var express = require('express');
  ```

4. Place your cursor at the end of the line requiring `express` in to the _server.js_ file and press enter twice. Create an `app` variable and set it to an instance of express by typing: 

to an instance of `express` and set `port`

  {% label %}Atom | server.js{% endlabel %}
  ```
  var app = express();
  ```
  
4. Next, press enter to add a `port` variable on the next line and set it to `process.env.PORT || 8080`: 

  {% label %}Atom | server.js{% endlabel %}
  ```
  var port = process.env.PORT || 8080;
  ```
  
  The `process.env.PORT` will be populated by Heroku later when the application is deployed and because we use the `||` to indicate "OR" the code will fallback to `8080` locally when it sees that `process.env.PORT` is not populated locally.

# TODO: Start back here

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
