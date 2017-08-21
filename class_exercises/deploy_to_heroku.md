# Deploy to Heroku

1. Create an account on [Heroku](https://signup.heroku.com)

2. Download & Install [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

3. Login with Heroku CLI

  {% label %}CLI{% endlabel %}
  ```
  heroku login
  ```

4. Create an empty application on heroku.

  Replace **name** with a name for your application. The **name** will be the subdomain in your application's URL: **http://name.herokuapp.com**

  {% label %}CLI{% endlabel %}
  ```
  heroku create name
  ```

5. This created the application on heroku, created a remote repo for the heroku application & set it as a remote named **heroku**. You should have 2 remotes, let's confirm.

  {% label %}CLI{% endlabel %}
  ```
  git remote -v
  ```

6. Push to heroku remote, which deploys the API
  {% label %}CLI{% endlabel %}
  ```
  git push heroku master
  ```

7. The output includes deployment details, including the URL. You'll see a message like `https://cocktail-trivia-api-2017.herokuapp.com/ deployed to Heroku`
