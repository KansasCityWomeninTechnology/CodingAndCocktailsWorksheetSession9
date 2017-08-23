# Part 1: Initialize the Project

## Setup

1. In your Command Line Interface (aka CLI: That means Git Bash or iTerm2), navigate to your _CodingAndCocktails_ folder by typing: 

  {% label %}iTerm2/Git Bash{% endlabel %}
  ```
  cd <your home directory>/CodingAndCocktails
  ```

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
If you start typing the name of a folder or file, hit tab and it will autocomplete
  {% endhint %}
  
## package.json

1. Next we need to initialize the project which will create a _package.json_ file which will enable us to install and use some **npm** packages.  If you were here last month you might remember the _package.json_ and talking about how packages work!

  {% label %}iTerm2/Git Bash{% endlabel %}
  ```
  npm init
  ```
  
  Running this command will prompt you for values to populate the _package.json_ file.  This file holds data about your project. 

 The first prompt will be *package name: (trivia-api)**. It may not be obvious here that it is actually prompting you for input there but it is. 

  Press the **enter** key to use the default value for the first three prompts. The 4th prompt is one we want to change, **entry point: (index.js)**. For that prompt, type `server.js` followed by the **enter** key.

  Hit **enter** for the remaining prompts unless you'd like to enter your name at the Author prompt.  Make sure you also press **enter** for the last prompt **Is this ok? (yes)**
  
  ![](/npm-init.gif)

## Install Packages
1. There are a few packages that we are going to use in this project.  These are bits of code that other developers have created and we are able to pull in and use in our project so that we don't have to try to reinvent the wheel. Type:

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  npm install cors express lodash node-fetch
  ```
  
  For additional context on the packages take a look at their pages on the npm website:
  [cors](https://www.npmjs.com/package/cors)
  [express](https://www.npmjs.com/package/express)
  https://www.npmjs.com/package/lodash
  https://www.npmjs.com/package/node-fetch

5. Install **nodemon** as a dev dependency. This will restart your server when files change. Type:

  {% label %}CLI{% endlabel %}
  ```
  npm install nodemon --save-dev
  ```

6. Open Atom.

  {% label %}CLI{% endlabel %}
  ```
  atom .
  ```

7. Add script for nodemon.

  {% label %}Atom | package.json{% endlabel %}
  ```
  "nm": "nodemon server.js"
  ```

8. [Answer key](https://github.com/KansasCityWomeninTechnology/trivia-api/tree/answer-key-part-1).
