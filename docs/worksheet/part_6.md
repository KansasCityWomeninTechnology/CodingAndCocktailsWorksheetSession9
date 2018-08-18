# Deploy to Heroku

1. In Chrome, navigate to [https://signup.heroku.com](https://signup.heroku.com) and create an account.

2. Install Heroku CLI.
   Click on the arrow below (^) on the section that corresponds to your Operating System.
      
  <!--sec data-title="Mac" data-id="section5" data-show=true data-collapse=true ces-->
    Install Heroku CLI via Homebrew.  In iTerm2 type:
   
    {% label %}iTerm2{% endlabel %}
    ```bash
    brew install heroku
    ```
    {% hint style='danger' %}
If you see warnings, grab a mentor to troubleshoot with the information on [the heroku website](https://devcenter.heroku.com/articles/heroku-cli#macos-homebrew)
    {% endhint %}
    
    To verify Heroku CLI installation type:
    {% label %}iTerm2{% endlabel %}
    ```bash
    heroku --version
    ```
    This should display a message similar to the following:
    > heroku-cli/6.13.5 (darwin-x64) node-v8.2.1
  <!--endsec-->

  <!--sec data-title="Windows" data-id="section6Win" data-show=true data-collapse=true ces-->
    [Click here to download the installer](https://cli-assets.heroku.com/heroku-cli/channels/stable/heroku-cli-x64.exe) and run through the install process.
    
    To verify Heroku CLI installation, type: 
    {% label %}Cmder{% endlabel %}
    ```bash
    heroku --version
    ```
    This should display a message similar to the following:
    > heroku-cli/6.13.5 (darwin-x64) node-v8.2.1

    {% hint style='danger' %}
If Cmder can't find `heroku` try closing Cmder and re-opening it. Applications installed after a CLI window is already opened may not immediately be available on the system PATH.
    {% endhint %}
  <!--endsec-->

  <!--sec data-title="CodeAnywhere" data-id="section6Chromebook" data-show=true data-collapse=true ces-->
    Install Heroku by typing the following command in your terminal and pressing `Enter`.

    {% label %}CodeAnywhere Terminal{% endlabel %}
    ```bash
    wget -O- https://toolbelt.heroku.com/install-ubuntu.sh | sh
    ```

    To verify Heroku CLI installation, type: 
    {% label %}CodeAnywhere Terminal{% endlabel %}
    ```bash
    heroku --version
    ```

    This should display a message similar to the following:
    > heroku-cli/7.9.3 linux-x64 node-v10.9.0
  <!--endsec-->

3. Login to Heroku: 
    {% label %}iTerm2/Cmder{% endlabel %}
    ```bash
    heroku login
    ```
    
    * You will be prompted for your email address and password that you signed up for Heroku with. If this is successful you will be shown the following message:
    
    > Logged in as youremail@example.com

4. Create a new empty application on Heroku to use for the API.

  Replace **app-name** with a name for your application. The **app-name** will be the subdomain in your application's URL: **http://app-name.herokuapp.com**

  {% label %}Cmder/iTerm2{% endlabel %}
  ```bash
  heroku create app-name
  ```
  
  This command creates the application on Heroku, creates a remote Git repository (repo) for the Heroku application and set that repo as a remote named `heroku`. 

5. You should have 2 remotes now, `heroku` and `origin`, each with a (fetch) and a (push). To confirm the remotes, in Cmder or iTerm2, type:

  {% label %}Cmder/iTerm2{% endlabel %}
  ```bash
  git remote -v
  ```

6. In Cmder or iTerm2, push the commit you created earlier to the Heroku remote, which deploys the API on Heroku

  {% label %}Cmder/iTerm2{% endlabel %}
  ```bash
  git push heroku master
  ```

7. The output includes deployment details, including the URL. You'll see a message like

  >https://cocktail-trivia-api-2017.herokuapp.com/ deployed to Heroku

8. In Postman, ensure the verb is **GET**. Enter your newly created URL and add `/api` to the end. Press the **Send** button to check out your API at your Heroku URL.

  If you don't get a response, grab a mentor to help troubleshoot!
  
9. Try out some of the URL endpoints you can put together from the [https://cocktail-trivia-api.herokuapp.com](https://cocktail-trivia-api.herokuapp.com/) form like you did earlier.  Just change the pieces after `/api`.

10. High Five! You created and deployed an API using Node.js!

 ![](/assets/images/hf.gif) 
