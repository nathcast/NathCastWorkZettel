202403121431
Status: #idea #documentation #protocols
Tags: #GIT

# GIT and GITHUB
## Create  Github Repo from an existing folder 

**Initialize Local Repository**

- first, initialize Git in root directory with
```
git init
```
- create a .gitignore file and list in there what we want to ignore

- Add all Files for version control with
    
 ```
git add -A

```

- Create a commit with a message of your choice 
```
git commit -m 'AddingBaseCode'

```

**Initialize Remote Repository**

- Create a project on GitHub and copy the URL of your project. as shown below:

[![enter image description here](https://i.stack.imgur.com/98pPx.png)](https://i.stack.imgur.com/98pPx.png)
From there, GIT hub provides a handy set of commands to run and I follow that. 

**Link Remote repo with Local repo**

- Now use copied URL to link your local repo with the remote GitHub repo. When you clone a repository with git clone, it automatically creates a remote connection called **origin** pointing back to the cloned repository. The command remote is used to manage a set of tracked repositories.
```
git remote add origin [https://github.com/hiteshsahu/Hassium-Word.git](https://github.com/hiteshsahu/Hassium-Word.git)
```


**Synchronize**

- Now we need to merge local code with remote code. This step is critical otherwise we won't be able to push code on GitHub. **You must call 'git pull' before pushing your code.**
```
git pull origin master --allow-unrelated-histories
```


**Commit your code**

- Finally, push all changes on GitHub

```
git push -u origin master
```
**Note**: Now Github uses "main" as the default branch. If your project use "main" instead of "master simply replace "master" with "main" from the above commands

---
## References
https://stackoverflow.com/questions/3311774/how-to-convert-existing-non-empty-directory-into-a-git-working-directory-and-pus
