# Version control
- It is a system that tracks changes to files, enabling collaborative development and ensuring project integrity.

## Distributed version control systems (DVCS) :
- It enable users to work with complete repository copies, promoting decentralized collaboration, flexible branching, merging, and offline access.
- exemple:  Git, Mercurial.
- ![](https://github.com/Charan-SV-2001/GitHub/blob/main/images/dvcs.png)

## Centralized version control systems (CVCS):
- It rely on a central repository for version management, where users check out files for modification and commit changes back to the central server.
- exemple:  Subversion (SVN).
- ![](https://github.com/Charan-SV-2001/GitHub/blob/main/images/cvcs.png)

# Git

## Git Workflow
<img src="https://github.com/user-attachments/assets/85465a0f-483a-483e-9c36-d4c2e55d5ee2" />

## Git Commands

  ### Start a new repository
  
| Command                      | Description                                      |
| ---------------------------- | ------------------------------------------------ |
| **git init**                 | Create a new repository in the current directory |
| **git clone** \<url> \<dir>  | Clone a remote repository                        |

  ### Git History Commands

| Command                       | Description                                      |
|-------------------------------|--------------------------------------------------|
| `git log`                     | Show commit logs                                 |
| `git log --oneline`           | Show commit logs with one line per commit        |
| `git show`                    | Show the changes of the last commit              |
| `git shortlog`                | Summarize `git log` output by author             |
| `git blame <file>`            | Show who changed which line in a file            |

  ### Local Changes Commands

| Command                         | Description                                                 |
|---------------------------------|-------------------------------------------------------------|
| `git status`                    | List which files are staged, unstaged, and untracked        |
| `git add <file>`                | Add a file to the staging area                              |
| `git add -p`                    | Interactively choose hunks of a file to add to the staging area |
| `git diff`                      | Show unstaged changes                                       |
| `git diff --staged`             | Show staged changes                                         |
| `git commit`                    | Commit staged changes using the default editor             |
| `git commit -m <message>`       | Commit staged changes with a message provided on the command line |
| `git commit --amend`            | Amend the last commit                                       |
| `git reset HEAD <file>`         | Unstage a file                                              |
| `git checkout -- <file>`        | Discard local changes in a file                             |

  ### Branches Commands

| Command                         | Description                                             |
|---------------------------------|---------------------------------------------------------|
| `git branch`                    | List local branches                                     |
| `git branch -r`                 | List remote branches                                    |
| `git branch <branch>`           | Create a new branch                                     |
| `git checkout <branch>`         | Switch to a branch                                      |
| `git checkout -b <branch>`      | Create a new branch and switch to it                   |
| `git merge <branch>`            | Merge a branch into the active branch                  |
| `git branch -d <branch>`        | Delete a branch                                         |


  ### Tags Commands

| Command                     | Description                     |
|-----------------------------|---------------------------------|
| `git tag`                  | List tags                      |
| `git tag <tag>`            | Create a tag                   |
| `git tag -a <tag>`         | Create an annotated tag        |
| `git tag -s <tag>`         | Create a GPG-signed tag        |
| `git tag -d <tag>`         | Delete a tag                   |
| `git show <tag>`           | Show the tag data              |

  ### Collaboration Commands

| Command                                  | Description                                                 |
|------------------------------------------|-------------------------------------------------------------|
| `git remote -v`                          | List remote repositories                                    |
| `git remote add <name> <url>`            | Add a new remote repository                                 |
| `git fetch <remote>`                     | Download all changes from a remote repository but don't integrate them |
| `git pull <remote>`                      | Download changes and directly merge/integrate them          |
| `git pull <remote> <branch>`             | Download changes and directly merge/integrate a remote branch |
| `git push <remote> <branch>`             | Upload local changes to a remote repository                 |
| `git push <remote> --delete <branch>`    | Delete a remote branch                                      |
| `git push <remote> --tags`               | Push tags to a remote repository                            |

  ### Stashing Commands

| Command               | Description                                              |
|-----------------------|----------------------------------------------------------|
| `git stash`           | Stash the changes in a dirty working directory away      |
| `git stash list`      | List all stashes                                         |
| `git stash pop`       | Apply the last stash and delete it                       |
| `git stash apply`     | Apply the last stash but don't delete it                 |
| `git stash drop`      | Delete the last stash                                    |
| `git stash clear`     | Delete all stashes                                       |


