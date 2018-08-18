# Homework {#homework}

The more you practice, the better you’ll get. Reinforce what you’ve learned tonight with the following tutorial.

{% hint style='tip' %}
##### Hey Slacker!

Remember, we're here to help.
Join the KCWiT #codingandcocktails Slack Channel: [kcwit.slack.com](http://kcwit.slack.com)
{% endhint %}

## Find a tutorial about REST
[Learn REST: A RESTful Tutorial](https://www.restapitutorial.com/)

## Explore free APIs
Use Postman to make requests on free, open APIs such as
   * [JSONPlaceholder](https://jsonplaceholder.typicode.com/)
     Use the endpoints in the Resources section and the verbs listed in Routes section. More [detailed examples found on their GitHub page](https://github.com/typicode/jsonplaceholder#how-to). All the resources tie together using ids.
   * Are you a Star Wars fan? Try out [The Star Wars API](https://swapi.co/). 

## Find a tutorial to create an API
[Build a RESTful API using Node and Express 4](https://scotch.io/tutorials/build-a-restful-api-using-node-and-express-4)

## Challenge yourself by using other frameworks
Re-implement the API we created tonight using a different framework. Try your hand at [**sails**](https://sailsjs.com/) or [**nest**](https://nestjs.com/). Both frameworks are built on top of **express** and both frameworks offer their own **CLI** (**C**ommand **L**ine **I**nterface) to make it easy to get going.

### sails
[sails](https://sailsjs.com/) is a popular **MVC** (**M**odel **V**iew **C**ontroller, a common pattern used to create graphical applications) framework for Node.js. It's a heavier weight framework built to support enterprise software. It sounds scary, but they make it easy to put together an API quickly. 

sails uses a syntax we're already familiar with-- JavaScript and`require` for dependencies so code changes to fit our API into the sails framework is minimal.

1. Follow their [Getting Started guide](https://sailsjs.com/get-started) to install the CLI, create a empty project, start it up using `sails lift`, and see what you get out of the box.

1. Since we're creating an API, reference [their documentation for "Actions and controllers"](https://sailsjs.com/documentation/concepts/actions-and-controllers) to add the routes.

{% hint style='tip' %}
You'll need to install some dependencies, such as `lodash` and `node-fetch` for the _quiz.js_ code to work correctly.
You will not need to make any changes to _quiz.js_ or _quiz_fixture.js_.
{% endhint %}

You can [check out the changes made to support the API starting from an empty sails application by looking here](https://github.com/KansasCityWomeninTechnology/trivia-api/commit/a6f1f687569a9890005be12511731e5d8a522e2b).

If you want to see the whole application, [check out the Answer Key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/bonus-sails).


### nest
[nest](https://nestjs.com/) is a newer, lighter weight **MVC** framework that uses ES6 syntax and Typescript in format resembling [Angular](https://angular.io). We will use Angular, Typescript, and ES6 import syntax next month, so you can get leg up by taking on this challenge!

1. Follow their [Introduction](https://docs.nestjs.com/) to install the CLI, create an empty project, start it up, and see what you get out of the box.

1. To add new routes, reference [their documentation for "Controllers"](https://docs.nestjs.com/controllers).

1. To support ES6 export/import syntax, changes were made in the _quiz.js_ and _quiz_fixture.js_. Notice you'll use `import` instead of `require`. Read about `import` statements from the [MDN reference guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import). 
   * Copy _quiz.ts_ file from our [GitHub repository using this link](https://raw.githubusercontent.com/KansasCityWomeninTechnology/trivia-api/f233b076132a3a3b1f0444df21ab528e0c38b8c5/src/quiz.ts). 
   * Copy _quiz_fixture.ts_ from our [GitHub repository using this link](https://raw.githubusercontent.com/KansasCityWomeninTechnology/trivia-api/f233b076132a3a3b1f0444df21ab528e0c38b8c5/src/quiz_fixture.ts).

{% hint style='tip' %}
You'll need to install some dependencies, such as `lodash` and `node-fetch` for the _quiz.ts_ code to work correctly.

Depending on whether you have lint packages installed on your IDE, you may see a lot of lint errors. Don't worry about them-- your API will still work fine.

nest scaffolds an `AppController` and `AppService`. We don't need those so we can remove them and replace with our own `QuizController`.
{% endhint %}

You can [check out the changes made to support the API starting from an empty nest application by looking here](https://github.com/KansasCityWomeninTechnology/trivia-api/commit/f233b076132a3a3b1f0444df21ab528e0c38b8c5).

If you want to see the whole application, [check out the Answer Key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/bonus-nest).