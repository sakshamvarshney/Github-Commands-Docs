# GitHub Commands Documentation

**@author: Saksham Varshney**

## Pre-requisite
Install git-Bash

### git init
To Initialize an empty git repository locally

	git init
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/1.png)

### git remote
To Check whether local repository connected with remote repository

	git remote -v
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/2.png)

### git remote add origin
To Connect local repository with remote repository

	git remote add origin repository URL
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/6.png)

### git status
To Check local untracked / staged changes that are yet to commit

	git status
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/3.png)

### git add
To Track changes or move local changes to staged area

	git add . // Dot is for track all the changes
	git add fileName // It is use for move specific file to staged area
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/4.png)

### git commit
To Commit local changes

	git commit -m commitMessageInQuotes
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/5.png)

### git push
To Move / Push local changes to Remote Repository

	git push origin master // If move local changes to remote master branch
	git push origin branchName // If move local changes to remote other than master branch
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/7.png)

### git clone
To Clone any repository from remote to locally

	git clone repository URL
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/11.png)

### git branch
To Check Total branch in repository

	git branch // It will list all the available branches
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/8.png)

### Create New branch
	git checkout -b newBranchName
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/9.png)

### Switch to master branch
	git checkout master
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/12.png)

### Switch to any specific branch
	git checkout branchName
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/10.png)

### Check all local and remote commit
	git log // It will list all the commits with commit id and commit message
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/13.png)

### git pull
	git pull origin master // Use this command if no conflicts exists
	git pull --rebase origin master // Use this command if conflict exists after than fix the conflicts

---

### git diff
This command can be use in many ways

To check the differences which are not yet staged with HEAD pointed commit

	git diff
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/14.png)

To check the differences which are staged with HEAD pointed commit

	git diff –-staged
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/15.png)

To check the differences from one branch with other branch

	git diff branchOneName branchTwoName
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/16.png)

---

### git reset
This command can be use in many ways

To unstages the file changes but preserves the file contents locally

	git reset // This command is for reset all the staged changes
	git reset fileName // This command is for reset the specific file staged changes
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/17.png)

To undo unstaged / staged changes and delete the file content as well

	git reset --hard
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/18.png)

**Note:** Can not use hard reset with specific file

To Undo the commit but preserves the changes locally

	git reset commitId
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/19.png)

	git reset HEAD~indexNumber // 0th index where HEAD is currently pointed, 1st for 2nd latest commit
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/20.png)

To Undo the commit and delete the file content as well

	git reset --hard commitId
	git reset --hard HEAD~indexNumber

---

### git stash
**Note:** Pre-requisite: At least one commit should exist

#### To store all the tracked / untracked changes file temporarily
	git stash
	git stash save stashMessageInQuotes // The only difference between these two commands is with second one we can stash changes with message while first one we cannot	
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/21.png)

#### To get all the lists of stashed changesets
	git stash list
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/22.png)

#### To restores the most recently stashed files
	git stash pop // This command will delete the entry from stash list
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/24.png)

	git stash apply // This command will not delete the entry from stash list
![](https://github.com/sakshamvarshney/Github-Commands-Docs/blob/master/Screenshots/23.png)

#### To restores the specific stashed files
	git stash pop stash@{indexNumber}
	git stash apply stash@{indexNumber}

#### To compare the stash changes from HEAD pointed commit
	git stash show -p // It will compare the most recent stash changes with HEAD pointed commit
	git stash show -p stash@{indexNumber} // It will compare the specific stash changes with HEAD pointed commit

#### To delete the stashed changes from stash list
	git stash drop // It will delete the most recent stashed changeset
	git stash drop stash@{indexNumber} // It will delete the specific stashed changeset

#### To delete all the stashed changes from the stash list at once
	git stash clear

---

## Tips & Tricks
VS Code can be launch in GitHub Repository

**Steps:**

**a. First way:**

	1. Go to GitHub Remote Repository
	2. Press . or > button from Keyboard
	3. It will launch the VS Code Remotely
	
**b. Second way:**

	1. Go to GitHub Remote Repository
	2. Replace https://github.com from repository URL with https://github.dev

---
Commit code with different different peoples email id or user name even if they are not a part of that Remote Repository

	git config --global user.email EmailIdInQuotes
	git config --global user.name usernameInQuotes

**Note:**

	1. This will work for Private & Public both Repository
	2. This will work for any branch [master or any other specific branch]

---