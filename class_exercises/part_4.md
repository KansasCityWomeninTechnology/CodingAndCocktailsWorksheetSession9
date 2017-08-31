# Part 4: More API Data

1. In Atom, in left side Project panel, right click on the _app_ folder, and pick "**New File**." Name it _quiz.js_.

2. Copy the contents [from this file on GitHub](https://github.com/KansasCityWomeninTechnology/trivia-api/blob/answer-key-part-4/app/quiz.js) & paste them into the _app/quiz.js_ file.

  // TODO: WALK THROUGH CODE OR BREAK IT DOWN INTO MORE STEPS

3. Import the newly created _quiz_ file into the _app/routes/quiz_routes.js_ file using a variable named `quiz`. Can you remember how to do this? If you need more direction, expand the section below by clicking on the arrow (^).

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

6. In Postman, ensure the verb is still set to GET, update the route using everything after `/api` in the previous step to hit that route in your for your endpoint.

7. Check your work with the [Part 4 Answer Key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-4).
