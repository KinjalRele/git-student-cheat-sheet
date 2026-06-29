# Git Student Cheat Sheet

A quick-reference guide to common git commands I used as a student.

## Simple Terminal Commands

```
pwd                  # print current directory
ls                   # list files in current directory
ls -la               # list all files (including hidden) with details
cd <folder>          # change directory
cd ..                # go up one directory
mkdir <name>         # create a new directory
rm <file>            # delete a file
rm -r <folder>       # delete a folder and its contents
mv <old> <new>       # move or rename a file/folder
cp <source> <dest>   # copy a file
clear                # clear the terminal screen
```

## Branches

```
git branch                  # list branches
git status                  # see which branch you're on
git checkout <name>         # switch branches
git checkout -b <name>      # create a branch and check it out at the same time
```

## Creating Files

```
touch <filename.type>       # create a new file
vi <filename.type>          # create/edit a file in vi
code <filename.type>        # create/edit a file in VS Code
```

## Local Repo Basics

```
git init                    # create a local repo
git add <name.type or *>    # add changes to the staging area
git commit -m "comments"    # commit staged changes with a message
git log                     # view commit history
git diff                    # see unstaged changes
git stash                   # temporarily shelve changes
git stash apply               # reapply stashed changes
```

## Remote Repos

```
git remote add origin <url (SSH)>   # point your local repo to a remote repo
git remote rm origin                 # remove an existing origin (if it exists)
git push origin master               # push local changes to the remote master branch
git push origin <local branch name>  # push your local branch to the remote
git pull origin <main/master>        # pull the latest changes from the remote's main/master branch
```

> Remember to switch to the correct branch before pulling.

## Advanced Commands

```
git log --oneline --graph         # compact, visual commit history
git diff <branch1> <branch2>      # compare two branches
git rebase -i HEAD~n              # interactively squash/edit the last n commits
git cherry-pick <commit>          # apply a specific commit to the current branch
git reset --soft <commit>         # undo commits, keep changes staged
git reset --mixed <commit>        # undo commits, keep changes unstaged
git reset --hard <commit>         # undo commits, discard changes (destructive!)
git revert <commit>               # safely undo a commit by creating a new inverse commit
git blame <file>                  # see who last changed each line of a file
git tag <name>                    # mark a release/version point
git fetch                         # get remote changes without merging them (vs. pull)
git branch -d <name>              # delete a branch (safe, only if merged)
git branch -D <name>              # force delete a branch
git log -p <file>                 # see the history of changes to a specific file
git config --global user.name "Your Name"     # set your git identity
git config --global user.email "you@email.com"
```

## Merging

```
git merge <branch name>     # merge a branch into the current branch (only works if current branch is master)
```

## Tips

- Make sure you're in the correct directory before checking branches!
- `Ctrl + Shift + P` opens the command palette in VS Code (use "Open Preview" for `.md` files).
- Use a `.gitignore` file to exclude files (e.g. `node_modules/`, `.env`) from being tracked.

## Pulling and Pushing to an Existing Repo

1. Create a new directory:
   ```
   mkdir nameOfTheDirectory
   ```
2. Go to that directory:
   ```
   cd nameOfTheDirectory
   ```
3. Initialize it as a git repo:
   ```
   git init
   ```
4. Set the origin (remove it first if it already exists: `git remote rm origin`):
   ```
   git remote add origin SSHkey
   ```
5. Stay on the main/master branch and pull it first:
   ```
   git pull origin main
   ```
   (Do this whenever you need to update your local repo with remote — make sure you're on the main/master branch!)
6. Create your branch:
   ```
   git checkout -b yourBranchName
   ```
7. Make your changes, then add and commit:
   ```
   git add filename.filetype   # or `git add *` to add all
   git commit -m "message"
   ```
8. Push to your remote branch:
   ```
   git push origin yourBranchName
   ```
9. Go to GitHub and create a PR.

## Updating Your Branch with Main

```
git checkout main/master
git pull origin main/master
git checkout yourbranch
git rebase main/master
git push origin yourbranch   # now update GitHub
```
