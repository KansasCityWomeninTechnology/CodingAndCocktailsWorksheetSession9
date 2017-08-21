# Push to GitHub

1. Create a new repository named **trivia-api** on github.com.

  1. via website

    Make sure **Initialize this repository with a README** is **unchecked**.

    ![](/assets/images/no-readme.png)

  2. Or via curl

  {% label %}CLI{% endlabel %}
  ```
  curl -u 'your_github_username' https://api.github.com/user/repos -d "{\"name\":\"trivia-api\"}"
  ```

  Replace `your_github_username` with your GitHub username [keep the quotes].

2. Initialize _trivia-api_ directory as local Git repo.

  {% label %}CLI{% endlabel %}
  ```
  git init
  ```

3. Create _.gitignore_

  {% label %}Atom | .gitignore{% endlabel %}
  ```
  node_modules/
  ```

4. Add repository from GitHub as a remote repository.

  {% label %}CLI{% endlabel %}
  ```
  git remote add origin https://github.com/your_github_username/trivia-api.git
  ```

5. See all the directories/files that are unstaged [and at this point are not even being tracked by Git]

  {% label %}CLI{% endlabel %}
  ```
  git status
  ```

6. Add files

  {% label %}CLI{% endlabel %}
  ```
  git add .
  ```

7. See the files that are staged & ready to be committed

  {% label %}CLI{% endlabel %}
  ```
  git status
  ```

8. Add commit

  {% label %}CLI{% endlabel %}
  ```
  git commit -m "Mom, look, my first API!"
  ```

9. Push and set upstream to remote's master branch

  {% label %}CLI{% endlabel %}
  ```
  git push -u origin master
  ```
