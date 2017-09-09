# Part 6: Deploy to Heroku

1. In Google Chrome, navigate to [https://signup.heroku.com](https://signup.heroku.com) and create an account.

2. Install Heroku CLI.
   Click on the arrow below (^) on the section that corresponds to your Operating System.
   
   **Cloud9/Chromebook users skip this step - it already comes installed on Cloud9**
   
  <!--sec data-title="Mac" data-id="section5" data-show=true data-collapse=true ces-->
    Install Heroku CLI via Homebrew.  In iTerm2 type:
   
    {% label %}iTerm2{% endlabel %}
    ```
    brew install heroku
    ```
    {% hint style='danger' %}
If you see warnings, grab a mentor to troubleshoot with the information on [the heroku website](https://devcenter.heroku.com/articles/heroku-cli#macos-homebrew)
    {% endhint %}
    
    To verify Heroku CLI installation type:
    {% label %}iTerm2{% endlabel %}
    ```
    heroku --version
    ```
    This should display a message similar to the following:
    > heroku-cli/6.13.5 (darwin-x64) node-v8.2.1
  <!--endsec-->

  <!--sec data-title="Windows" data-id="section6" data-show=true data-collapse=true ces-->
    [Click here to download the installer](https://cli-assets.heroku.com/heroku-cli/channels/stable/heroku-cli-x64.exe) and run through the install process.
    
    To verify Heroku CLI installation, type: 
    {% label %}Git Bash{% endlabel %}
    ```
    heroku --version
    ```
    This should display a message similar to the following:
    > heroku-cli/6.13.5 (darwin-x64) node-v8.2.1
  <!--endsec-->

3. Login to Heroku: 

  <!--sec data-title="Mac & Cloud9/Chromebooks" data-id="section8" data-show=true data-collapse=true ces-->
    In iTerm2/Cloud9 Terminal, login to Heroku with the Heroku CLI:
  
    {% label %}iTerm2/Cloud9 Terminal{% endlabel %}
    ```
    heroku login
    ```
    
    You will be prompted for your email address and password that you signed up for Heroku with. If this is successful you will be shown the following message:
    
    > Logged in as youremail@example.com
  <!--endsec-->

  <!--sec data-title="Windows" data-id="section9" data-show=true data-collapse=true ces-->
    In Git Bash type: 
    
    {% label %}cmd.exe{% endlabel %}
    ```
    start cmd
    ```
    
    to open your current directory in cmd.exe
    
    In cmd.exe, type:
    
    {% label %}cmd.exe{% endlabel %}
    ```
    heroku login
    ```
    
    You will be prompted for your email address and password that you signed up for Heroku with. If this is successful you will be shown the following message:
    
    > Logged in as youremail@example.com
    
    Close cmd.exe & go back to Git Bash
  <!--endsec-->

4. Create a new empty application on Heroku to use for the API.

  Replace **app-name** with a name for your application. The **app-name** will be the subdomain in your application's URL: **http://app-name.herokuapp.com**

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  heroku create app-name
  ```
  
  This command creates the application on Heroku, creates a remote Git repository (repo) for the Heroku application & set that repo as a remote named `heroku`. 

5. You should have 2 remotes now, `heroku` and `origin`, each with a (fetch) and a (push). To confirm the remotes, in Git Bash or iTerm2, type:

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
  
9. Try out some of the URL endpoints you can put together from the [https://cocktail-trivia-api.herokuapp.com](https://cocktail-trivia-api.herokuapp.com/) form like you did earlier.  Just change the pieces after `/api`.

10. High Five! You just created and deployed an API using Node.js! 
