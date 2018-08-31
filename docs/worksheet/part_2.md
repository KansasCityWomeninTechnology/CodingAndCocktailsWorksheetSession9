# Connecting to an API

1. In Atom, right click anywhere on the left side section of the screen where the "trivia-api" folder and the _package.json_ file are displayed. 

2. Select **New File** and name it _server.js_.
   {% hint style='tip' %}
You are creating the _server.js_ file in the "trivia-api" folder. You will see it right underneath _package.json_.
   {% endhint %}

3. In order to use a package in your project, you must require it in to the file you want to use it in. Typically you set a variable equal to this require statement to give it a place from which the package can be used and accessed.

  Utilize the **cors** and **express** packages in the _server.js_ file by adding the following two lines to the top of the _server.js_ file:

  {% label %}Atom | server.js{% endlabel %}
  ```js
  var cors = require('cors');
  var express = require('express');
  ```

4. Place your cursor at the end of the line requiring `express` in to the _server.js_ file and press `Enter` twice. Create an `app` variable and set it to an instance of express by typing: 

  {% label %}Atom | server.js{% endlabel %}
  ```js
  var app = express();
  ```
  
4. Next, press `Enter` to add a `PORT` variable on the next line and set it to `process.env.PORT || 8080`: 

  {% label %}Atom | server.js{% endlabel %}
  ```js
  var port = process.env.PORT || 8080;
  ```
  
  {% hint style='info' %}
The `process.env.PORT` will be populated by Heroku later when the application is deployed and because we use the `||` to indicate "OR" the code will fallback to `8080` locally when it sees that `process.env.PORT` is not populated locally.
  {% endhint %}

4. The next step is to initiate the router.  This means we're setting up the piece of code that will direct a user to the right location when they visit the application.  Place your cursor at the end of the line of code that sets the port and press `Enter` twice.  Then create a variable named `apiRouter` and set it to your router instance like below: 

  {% label %}Atom | server.js{% endlabel %}
  ```js
  var apiRouter = express.Router();
  ```

5. Next, add the default route.  Press `Enter` twice from the end of the line that initiates the router and type the following:

  {% label %}Atom | server.js{% endlabel %}
  ```js
  apiRouter.get('/', function(req, res) {
    res.json({ message: 'hooray! your API is working!' });
  });
  ```
  {% hint style='info' %}
This code is saying that when someone requests the root route (`apiRouter.get('/')`), respond (`res`) with a JavaScript Object Notation formatted piece of data (`.json`) with a key of `message` and a value of `hooray! your API is working!`. 
  {% endhint %}
  
  {% hint style='tip' %}
**Challenge!** Grab a mentor and tell them what you would change if you wanted to respond to a user calling a `/data` route.
  {% endhint %}

4. Next you'll configure the application by adding several methods to it using **chaining**.

  1. Ensure there is a blank line between the end of the close of the routing function (the routing function ends with a `});`) and your cursor.  Type: 

    {% label %}Atom | server.js{% endlabel %}
    ```js
    app
    ```
  
  2. Enable calling to the API from any origin - remember this is called **CORS**.  
  
    1. With your cursor at the end of the `app` line, press `Enter` to move to the next line.
    
    2. Press `Tab` to indent the code.  This is a common practice when chaining methods to make it easier to read the code!
    
    3. Type:
      {% label %}Atom | server.js{% endlabel %}
      ```js
      .use(cors())
      ```
    {% hint style='tip' %}
Move your cursor to the end of the line-- outside of the final closing parenthesis. Some IDEs will do this for you, but some may not.

When chaining commands, you want each command on a separate line.
    {% endhint %}
    
  3. Tell the application to use the API router for any URL that starts with `/api`.
  
     1. Press `Enter`. Atom should automatically align your indentation with the `.use(cors())` line from above.  This next line should be indented just as far as that line is.  Type:  

        {% label %}Atom | server.js{% endlabel %}
        ```js
        .use('/api', apiRouter)
        ```

  4. Tell the application which port to listen for API requests on.  `8080` is a common port to use here. Press `Enter` to move to a new line and type: 
    
      {% label %}Atom | server.js{% endlabel %}
      ```js
      .listen(port, function() {
        console.log('API Magic happening on port ' + port);
      });
      ```

5. Save the file then run the application using the `nodemon` script you created in the last section so that when you save changes to code, the API will re-run with the changes.

  {% label %}Cmder/iTerm2{% endlabel %}
  ```bash
  npm run nm
  ```
  
  To cancel the running server, press the `ctrl` + `c` keys.

6. Open **Postman**

  <!--sec data-title="Chromebooks Only: CodeAnywhere Instructions" data-id="sectionPostman" data-show=true data-collapse=true ces-->

  1. Inside CodeAnywhere, open the tab named "KCWIT" that is not your terminal. Find the section that says "To access an application running on your Container..." and open the link in a new tab.
     {% hint style='info' %}
If you closed this tab, reopen it by right clicking on **KCWIT** container and select **Info**.
     {% endhint %}
  
  2. In the new tab, add the port and the route we created to the URL. Your new URL may look something like 
  `http://KCWIT-gracehopper624801.codeanyapp.com:8080/api`
  
  3. You should see the `"message": "hooray! your API is working!"` data returned from your API in the browser screen
  
  You can skip the rest of the steps until the Answer key.

  <!--endsec-->

  1. Make sure **GET** is selected in the HTTP dropdown.
    ![](/assets/images/postman.png)

  2. In the field that says **Enter request URL**, type: `http://localhost:8080/api`

  3. Click on the **Send** button.  
  
  4. You should see the `"message": "hooray! your API is working!"` data returned from your API.

7. Click to check your work against the [Part 2 Answer key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-2).
