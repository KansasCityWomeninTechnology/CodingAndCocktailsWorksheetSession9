# Part 4: More API Data

1. In Atom, in left side Project panel, right click on the _app_ folder, and pick "**New File**." Name it _quiz.js_.

2. Copy the contents [from this file on GitHub](https://github.com/KansasCityWomeninTechnology/trivia-api/blob/answer-key-part-4/app/quiz.js) & paste them into the _app/quiz.js_ file.

  {% hint style='info' %}
##### Let's walk through this code!
  
The first object (set to the variable `categoryMap`) is simply a mapping of quiz category name to a number for later use.
  
Next, we require in a couple packages to use - `node-fetch` and `lodash`

Next we create three functions:

  1. `getQuiz` - Gets the data to use as our quiz.
      1. Calls the function that creates the trivia URL to use and stores that into a variable.  
      2. Makes a request to that URL using the [`node-fetch` package](https://www.npmjs.com/package/node-fetch)
      3. Gets the response in JSON (JavaScript Object Notation) format
      4. Sends that result to change the data format into the response format that we want to use for our quiz. 
  
  2. `getTriviaURL` - Builds the URL for the quiz we've specified.
      1. First logs data to the console: 
        * The count of questions to return
        * The category to get questions for
        * The difficulty level to use for this quiz
      2. Then the function builds out the correct URL using the initial `categoryMap` data and the count/category/difficulty options to return the URL to the caller.
  
  3. `reformatQA` - Accepts one data format and transforms it into another.
      1. The map method applies a function to each piece of data passed in to the function
      2. Sets up the incorrect answers to have a `correct` value of `false` and a `text` of the `answer`
      3. Adds the correct answers with a `correct` value of `true` and a `text` of the `correct_answer`
      4. Returns an object of the question `text` and uses the `shuffle` method from the `lodash` library to change the order of the answers to show as options.
  {% endhint %}

3. Import the newly created _quiz.js_ file into the _app/routes/quiz_routes.js_ file using a variable named `quiz`. Can you remember how to do this? If you need more direction, expand the section below by clicking on the arrow (^).

  <!--sec data-title="Hint #1" data-id="section4" data-show=true data-collapse=true ces-->
    {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
    ```
    var quiz = require('./../quiz.js');
    ```
  <!--endsec-->

4. In Atom, add a couple more routes to _quiz_routes.js_ to use the methods that were created in _app/quiz.js_.

  {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
  ```
  apiRouter.get('/category/:category', function(req, res) {
    quiz
      .getQuiz(req.params)
      .then(function(result){res.json(result);});
  });

  apiRouter.get('/category/:category/difficulty/:difficulty', function(req, res) {
    quiz
      .getQuiz(req.params)
      .then(function(result){res.json(result);});
  });
  
  apiRouter.get('/category/:category/difficulty/:difficulty/count/:count', function(req, res) {
    quiz
      .getQuiz(req.params)
      .then(function(result){res.json(result);});
  });
  ```

5. In Google Chrome, navigate to [https://cocktail-trivia-api.herokuapp.com](https://cocktail-trivia-api.herokuapp.com/) and fill out the form to create an endpoint, or URL that you can use in Postman to view data returned from your API routes.

6. In Postman, ensure the verb is still set to GET, update the route using everything after `/api` in the previous step to hit that route for your endpoint.

  For example, if you choose "Music", "Easy" and 10 your generated URL would look like:
  
  ```
  //cocktail-trivia-api.herokuapp.com/api/category/entertainment-music/difficulty/easy
  ```
  
  You would take `/category/entertainment-music/difficulty/easy` and tack it onto the end of your `http://localhost:8080/api` URL to make your request to: `http://localhost:8080/api/category/entertainment-music/difficulty/easy`.
  
  <!--sec data-title="Chromebooks Only: Cloud9 Instructions" data-id="sectionPostman3" data-show=true data-collapse=true ces-->

  * If you still have your tab open, update the end of the URL to reflect the category/difficulty/count configuration of your choosing.
  
  * You should see the new data from _quiz.js_ returned from your API in the browser screen
<!--endsec-->

7. Check your work with the [Part 4 Answer Key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-4).
