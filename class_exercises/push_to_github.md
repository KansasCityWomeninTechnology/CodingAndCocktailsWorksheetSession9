# Push to GitHub

1. Make sure you have created your GitHub account and are logged in to [https://github.com](https://github.com/)

2. Create a new repository named **trivia-api** on github.com.

  1. Via Github.com website
  
    In the upper-right corner of any page, click **+**, and then click **New repository**.

    {% hint style='danger' %}
Make sure **Initialize this repository with a README** is **unchecked**.

    ![](/assets/images/no-readme.PNG)
  {% endhint %}  

  2. Or via curl

    {% label %}Git Bash/iTerm2{% endlabel %}
    ```
    curl -u 'your_github_username' https://api.github.com/user/repos -d "{\"name\":\"trivia-api\"}"
    ```

    Replace `your_github_username` with your own GitHub username but keep the quotes.

2. Initialize the _trivia-api_ directory as local Git repository (aka repo).

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git init
  ```

3. In Atom, create a _.gitignore_ file in the root directory of the project and in that file type:

  {% label %}Atom | .gitignore{% endlabel %}
  ```
  node_modules/
  ```

4. You must connect the repository from GitHub to this repository you now have locally on your computer. This is called adding a remote repository. 

  1. In Google Chrome on the GitHub site make sure you have your `trivia-api` repository open.
  
  2. Click on the green **"Clone or download"** button and then the clipboard icon to copy the URL.

  3. In your Command Line Interface (CLI aka Git Bash or iTerm2), type the following to add the remote
  
    {% label %}Git Bash/iTerm2{% endlabel %}
    ```
    git remote add origin https://github.com/your_github_username/trivia-api.git
    ```

5. Check which directories/files that are unstaged - that Git doesn't yet know about. Type:

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git status
  ```

6. Stage the files so Git knows which files to be dealing with.  In this case we want all of them so we just add all the files in the current directory: `.`.  Type:

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git add .
  ```

7. Check to ensure all of your files are staged & ready to be committed.

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git status
  ```

8. Commit the files so Git understands the group of changes to deal with.  Feel free to change the commit message (the part in the quotation marks) if you'd like!

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git commit -m "Mom, look, my first API!"
  ```

9. Push these changes up to the GitHub website (your remote/cloud) and set the upstream (original source) to remote's `master` branch. 

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git push -u origin master
  ```
  
10. Your API now exists on GitHub!
