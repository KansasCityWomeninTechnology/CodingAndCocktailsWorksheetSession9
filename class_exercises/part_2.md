# Part 2: Connecting to an API

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

  {% label %}Atom | server.js{% endlabel %}
  ```
  var app = express();
  ```
  
4. Next, press enter to add a `port` variable on the next line and set it to `process.env.PORT || 8080`: 

  {% label %}Atom | server.js{% endlabel %}
  ```
  var port = process.env.PORT || 8080;
  ```
  
  {% hint style='info' %}
The `process.env.PORT` will be populated by Heroku later when the application is deployed and because we use the `||` to indicate "OR" the code will fallback to `8080` locally when it sees that `process.env.PORT` is not populated locally.
  {% endhint %}

4. The next step is to initiate the router.  This means we're setting up the piece of code that will direct a user to the right location when they visit the application.  Place your cursor at the end of the line of code that sets the port and press enter twice.  Then create a variable named `apiRouter` and set it to your router instance like below: 

  {% label %}Atom | server.js{% endlabel %}
  ```
  var apiRouter = express.Router();
  ```

5. Next, add the default route.  Press enter twice from the end of the line that initiates the router and type the following:

  {% label %}Atom | server.js{% endlabel %}
  ```
  apiRouter.get('/', function(req, res) {
    res.json({ message: 'hooray! your API is working!' });
  });
  ```
  
  This code is saying that when someone requests the root route (`apiRouter.get('/'`), respond (`res`) with a JavaScript Object Notation formatted piece of data (`.json`) with a key of `message` and a value of `hooray! your API is working!`. 
  
  !Challenge! Grab a mentor and tell them what you would change if you wanted to respond to a user hitting a /data route.

4. Next you'll configure the application by adding several methods to it.  This is called "chaining."

  1. Ensure there is a blank line between the end of the close of the routing function and your cursor.  Type: 

  {% label %}Atom | server.js{% endlabel %}
  ```
  app
  ```
  
  2. Enable calling to the API from any origin - remember this is called "CORS.".  
  
    1. With your cursor at the end of the `app` line, press enter to move to the next line.
    
    2. Press tab to indent the code.  This is a common practice when chaining methods to make it easier to read the code!
    
    3. Type: 
    
    {% label %}Atom | server.js{% endlabel %}
    ```
    .use(cors())
    ```
    
  3. Tell the application to use the API router for any URL that starts with `/api`.
  
     1. Press enter. Atom should automatically align your indentation with the `.use(cors())` line from above.  This next line should be indented just as far as that line is.  Type:  

      {% label %}Atom | server.js{% endlabel %}
      ```
      .use('/api', apiRouter)
      ```

  4. Tell the application which port to listen for API requests on.  `8080` is a common port to use here. Press enter to move to a new line and type: 
    
    {% label %}Atom | server.js{% endlabel %}
      ```
      .listen(port, function() {
        console.log('API Magic happening on port ' + port);
      });
      ```

5. Run the application using the `nodemon` script you created in Part 1 so that when you save changes to code, the API will re-run with the changes.

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  npm run nm
  ```

6. Open **Postman**

  1. Make sure **GET** is selected in the HTTP dropdown.

  2. In the field that says **Enter request URL**, type: `http://localhost:8080/api`

  3. Click on the **Send** button.  
  
  4. You should see the `"message": "hooray! your API is working!"` data returned from your API.

7. Click to check your work against the [Part 2 Answer key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-2).
