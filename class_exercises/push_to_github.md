# Push to GitHub

1. Make sure you have created your GitHub account from [the tools setup](https://codingandcocktailskc.gitbooks.io/coding-cocktails-the-tools/content/user-accounts---github-slack--codecademy.html) and are logged in to [https://github.com](https://github.com/)

2. Create a new repository named **trivia-api** on github.com.

  1. In Google chrome, navigate to [https://github.com](https://github.com/)
  
  2. In the upper-right corner, click **+**, and then click **New repository**.

    {% hint style='danger' %}
Make sure **Initialize this repository with a README** is **unchecked**.

    ![](/assets/images/no-readme.PNG)
  {% endhint %}

2. In Git Bash or iTerm2, initialize the _trivia-api_ directory as local Git repository (aka repo).

  {% label %}Git Bash/iTerm2{% endlabel %}
  ```
  git init
  ```

3. In Atom, right click in the left side Project pane and choose "**New File**." Name this file _.gitignore_ (**notice the filename starts with a .**) 

4. Double click on that file in the left side Project pane to open it for editing and in that file type:

  {% label %}Atom | .gitignore{% endlabel %}
  ```
  node_modules/
  ```

5. You must connect the repository from GitHub (on the internet) to this repository you now have locally on your computer. This is called adding a remote repository. 

  {% hint style='tip' %}
For more information on working with remotes read [Git Basics - Working with Remotes from the Pro Git book](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
  {% endhint %}

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
