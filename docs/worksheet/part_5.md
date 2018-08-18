# Push to GitHub

1. Log in to GitHub by navigating to [https://github.com](https://github.com/).
   {% hint style='tip' %}
Don't have Git or a GitHub account? Follow the instructions in [Setup instructions](/setup) to install Git and create your GitHub account.
   {% endhint %}

2. Create a new repository named **trivia-api** on github.com.

  1. In Chrome, navigate to [https://github.com](https://github.com/)
  
  2. In the upper-right corner, press <span class="octicon octicon-plus"></span> and then select **New repository**.

    {% hint style='danger' %}
Make sure **Initialize this repository with a README** is **unchecked**.

![](/assets/images/no-readme.PNG)
  {% endhint %}

3. In Cmder or iTerm2, initialize the "trivia-api" directory as a local Git repository (aka repo).

  {% label %}Cmder/iTerm2{% endlabel %}
  ```bash
  git init
  ```
   {% hint style='tip' %}
Feel free to grab a mentor if you didn't have the opportunity to attend the Git session or if you need a refresher!
   {% endhint %}

4. In Atom, right click on the "trivia-api" folder in the left side **Project** pane and choose **New File**. Name this file _.gitignore_ (**notice the filename starts with a .**) 

5. Double click on that file in the left side **Project** pane to open it for editing and in that file type:

  {% label %}Atom | .gitignore{% endlabel %}
  ```
  node_modules/
  ```

6. You must connect the repository from GitHub (on the internet) to this repository you now have locally on your computer. This is called adding a remote repository. 

  {% hint style='tip' %}
For more information on working with remotes read [Git Basics - Working with Remotes from the Pro Git book](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
  {% endhint %}

  1. In Chrome on the GitHub site make sure you have your `trivia-api` repository open.
  
  2. Click on the <span class="octicon octicon-clippy"></span> button to copy the URL.
     ![](/assets/images/gitClone.png)

  3. In Cmder or iTerm2, type the following to add the remote:
  
    {% label %}Cmder/iTerm2{% endlabel %}
    ```bash
    git remote add origin https://github.com/<your_github_username>/trivia-api.git
    ```
    Replace the git URL with the URL you copied from the GitHub site in step 6.i. above.

7. Check which directories/files are unstaged (that Git doesn't yet know about). Type:

  {% label %}Cmder/iTerm2{% endlabel %}
  ```bash
  git status
  ```
  
  Your files should display under a header of "Untracked files:" and should be red in color.

8. Stage the files so Git knows which files to deal with.  In this case we want all of them so we just add all the files in the current directory. The current directory can be referenced as: `.`.  Type:

  {% label %}Cmder/iTerm2{% endlabel %}
  ```
  git add .
  ```

9. Check to ensure all of your files are staged and ready to be committed.

  {% label %}Cmder/iTerm2{% endlabel %}
  ```bash
  git status
  ```
  
  Now, your files should display under a header of "Changes to be committed:" and should be green in color.

10. Commit the files so Git understands what group of changes to deal with.  Feel free to change the commit message (the part in the quotation marks) if you'd like!

  {% label %}Cmder/iTerm2{% endlabel %}
  ```bash
  git commit -m "Mom, look, my first API!"
  ```

11. Push these changes up to the GitHub website (the origin remote you created in step 6) and set the upstream (`-u`) this is the the gatekeeper of the project or the source of truth to which you wish to contribute to) to the remote's `master` branch. 

  {% label %}Cmder/iTerm2{% endlabel %}
  ```bash
  git push -u origin master
  ```
  
12. Your API now exists on GitHub!
