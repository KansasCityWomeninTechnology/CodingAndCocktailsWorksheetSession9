# Part 1

0. Download and install [Postman](https://www.getpostman.com/).

1. In your _CodingAndCocktails_ directory create a new folder named _trivia-api_.

2. In your CLI, navigate to _CodingAndCocktails/trivia-api_ folder. Type:

  {% label %}CLI{% endlabel %}
  ```
  cd <your home directory>/CodingAndCocktails/trivia-api
  ```

  {% hint style='tip' %}

  - Your home directory is:
    - Mac: _/users/<yourUsername>_
    - Windows: _C:/Users/<youUsername>_
  - Command to change folders: ``cd <folderToGoTo>``
  - You can also use **~** as a shortcut in CLI for your home directory: ``cd ~``
  - Command to make a folder: ``mkdir <newFolder>``
  - Most command line applications are not case sensitive, but a few are!

  {% endhint %}

3. Initialize the _trivia-api_ directory to create _package.json_, so we can install some **npm** packages. Type:

  {% label %}CLI{% endlabel %}
  ```
  npm init
  ```

4. You will be prompted for values to populate the _package.json_. The first prompt will be *package name: (trivia-api)**.

  For all but one prompt, you'll hit the **enter** key to use the default value. The 4th prompt is the one we care about, **entry point: (index.js)**. For that prompt, type `server.js` followed by the **enter** key.

  Hit **enter** for the remaining prompts. [Including for the last prompt **Is this ok? (yes)**]

4. Install our packages. Type:

  {% label %}CLI{% endlabel %}
  ```
  npm install cors express lodash node-fetch
  ```
  https://www.npmjs.com/package/cors
  https://www.npmjs.com/package/express
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
