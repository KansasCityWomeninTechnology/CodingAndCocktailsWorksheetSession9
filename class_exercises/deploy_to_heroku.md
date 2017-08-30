# Deploy to Heroku

1. In Google Chrome, navigate to [https://signup.heroku.com](https://signup.heroku.com) and create an account.

2. Download & Install [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

  Windows devices you'll likely want to choose the 64-bit link unless you have an ancient computer.  Grab a mentor if you're unsure which link to click!

3. In Git Bash or iTerm2, login to Heroku with the Heroku CLI

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  heroku login
  ```
  You will be prompted for your email address and password that you signed up for Heroku with. If this is successful you will be shown the following message: 
  
  > Logged in as email@example.com

4. Create a new empty application on Heroku.

  Replace **name** with a name for your application. The **name** will be the subdomain in your application's URL: **http://name.herokuapp.com**

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  heroku create name
  ```

5. The previous command created the application on Heroku, created a remote repo for the Heroku application & set it as a remote named **heroku**. You should have 2 remotes now, `heroku` and `origin`, each with a (fetch) and a (push).  In Git Bash or iTerm2, to confirm the remotes type:

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git remote -v
  ```

6. In Git Bash or iTerm2, push the commit you created earlier to the Heroku remote, which deploys the API on Heroku

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git push heroku master
  ```

7. The output includes deployment details, including the URL. You'll see a message like

  >https://cocktail-trivia-api-2017.herokuapp.com/ deployed to Heroku

8. In Postman, Ensure the verb is set to GET, enter your newly created URL and add `/api` to the end.  Push the "**Send**" button to check out your API at your Heroku URL.

  If you don't get a response, grab a mentor to help troubleshoot!
  
9. Try out some of the URLs you can put together from the [https://cocktail-trivia-api.herokuapp.com](https://cocktail-trivia-api.herokuapp.com/) form.
