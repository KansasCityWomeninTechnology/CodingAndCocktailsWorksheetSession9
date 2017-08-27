# Part 1: Initialize the Project

## Setup

1. In your Command Line Interface (aka CLI: That means Git Bash or iTerm2), navigate to your _CodingAndCocktails_ folder by typing: 

  {% label %}iTerm2/Git Bash{% endlabel %}
  ```
  cd <your home directory>/CodingAndCocktails
  ```
  
  Then press **enter**. You will need to press enter after any command you enter in the command line.

  {% hint style='tip' %}
  #### Command line woes?
  - Your home directory is:
    - Mac: `/users/<yourUsername>`
    - Windows: `C:/Users/<yourUsername>`
  - Command to change folders: `cd <folderToGoTo>`
  - Command to make a folder: `mkdir <newFolder>`
  - You can also use **~** as a shortcut in CLI for your home directory: ``cd ~``

  Revisit the command line worksheet from March:
  [bit.ly/CnCMarWork](http://bit.ly/CnCMarWork)
  {% endhint %}

2.  Make a new folder named _trivia-api_. 

  {% label %}iTerm2/Git Bash{% endlabel %}
  ```
  mkdir trivia-api
  ```

3.  Move into that new folder.

  {% label %}iTerm2/Git Bash{% endlabel %}
  ```
  cd trivia-api
  ```

  {% hint style='tip' %}
If you start typing the name of a folder or file, hit tab and it will autocomplete.  

Above if you had typed `cd tri` and then hit tab it would have completed to `cd trivia-api` for you!
  {% endhint %}
  
## package.json

1. To start the project, we need to initialize it.  Doing this will create a _package.json_ file which will enable us to install and use some **npm** packages and store data about the project.

  {% hint style='info' %}
If you were here last month, you might remember the _package.json_ and talking about how packages work! 
  {% endhint %}

  Type:

  {% label %}iTerm2/Git Bash{% endlabel %}
  ```
  npm init
  ```
  
2. This command will prompt you for values to populate the _package.json_ file.

 The first prompt is `package name: (trivia-api)`. It may not be obvious that it is prompting you for input there but it is. 

  Press the **enter** key to use the default value for the first three prompts only. 
  
3. The 4th prompt is one we want to change, `entry point: (index.js)`. For that prompt, type `server.js` followed by the **enter** key.

  Hit **enter** for the remaining prompts unless you'd like to enter your name at the `author:` prompt.  Make sure you also press **enter** for the last prompt `Is this ok? (yes)`
  
  ![](/npm-init.gif)

## Install Packages
1. There are a few packages that we are going to use in this project.  These are bits of code that other developers have created and we are able to pull in and use in our project so that we don't have to try to reinvent the wheel. Type:

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  npm install cors express lodash node-fetch
  ```
  {% hint style='info' %}
For additional context on the packages being used take a look at their pages on the npm website:
  * cors: https://www.npmjs.com/package/cors
  * express: https://www.npmjs.com/package/express
  * lodash: https://www.npmjs.com/package/lodash
  * node-fetch: https://www.npmjs.com/package/node-fetch
  {% endhint %}

5. Install the `nodemon` package as a dev dependency. This package will allow you to restart your server when files change without having to manually do so. Type:

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  npm install nodemon --save-dev
  ```
  
  {% hint style='tip' %}
DevDepencency: A tool that is used only during the development of your project.  This is something that is not necessary to run your application 

Dependency: A tool or piece of code that is required to make your application work.
  {% endhint %}

6. Open Atom via the command line

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  atom .
  ```
  {% hint style='danger' %}
Command not found

If Atom doesn't open (but you know it's installed), your system likely doesn't recognize the `atom` command.

You can configure your system to recognize the command (ask a mentor for help) or you can follow these steps to open it manually:
  1. From your applications or start menu, open Atom
  2. In Atom: File >> Open... (Mac) or Open Folder... (Windows)
  3. Open the packagesproject folder
  4. Click the Open button
  {% endhint %}

7. Add an npm script to enable you run nodemon quickly in the command line.  To add an npm script it must go inside the curly braces after the `scripts` label.
  * At the end of the line that starts with the `"test":` key, add a comma `,`
  * On the next line, type out the following to add the nodemon script:

  {% label %}Atom | package.json{% endlabel %}
  ```
  "nm": "nodemon server.js"
  ```

8. Great work!  Compare your `package.json` with the Part 1 [Answer key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-1).
