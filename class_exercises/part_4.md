# Part 4

1. In the _app_ folder, create a new file named _quiz.js_.

2. Copy the contents [from here](https://github.com/KansasCityWomeninTechnology/trivia-api/blob/answer-key-part-4/app/quiz.js) & paste into your _app/quiz.js_ file.

// TODO: WALK THROUGH CODE OR BREAK IT DOWN INTO MORE STEPS

3. Import this file into your _app/routes/quiz_routes.js_.

  {% label %}Atom | app/routes/quiz_routes.js{% endlabel %}
  ```
  var quiz = require('./../quiz.js');
  ```

4. Let's add a couple more routes to this file, to use the methods that are in _app/quiz.js_.

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

5. Use the form at `https://cocktail-trivia-api.herokuapp.com/` to determine a possible endpoint for your API

6. Use Postman to hit one of your new routes. [Use the path from `/api` on from the previous step to determine an eligible path for your endpoint.

7. [Answer Key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-4)
