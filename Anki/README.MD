# Anki Notes

---

## 01-command-line-commands

#### Q1:Explain the following terminal commands : pwd,ls,cd Desktop,clear, cd..

**Answer**:

| command    | function                             |
| ---------- | ------------------------------------ |
| pwd        | print working directory              |
| ls         | lists all files in current directory |
| cd Desktop | change folder to desktop             |
| clear      | clears the command line              |
| cd..       | moves back one directory             |

---

## 02-introduction

#### Q1:Write the command for initializing a git repository, checking status of a git repository,cloning a public repository,cloning a private repository

**Answer**:

| functionality                       | git command               |
| ----------------------------------- | ------------------------- |
| initializing a git repository       | git init                  |
| checking status of a git repository | git status                |
| cloning a public repo               | git clone https://url     |
| cloning a private repo              | git clone https://pat@url |

---

## 03-git-basics

#### Q1:Write the git commands for the following

- adding a single file 

- adding multiple files 

- adding all files 

- git log - detailed

- git log - overview

- remote branches 

- add a remote branch 

- renaming a remote branch

- removing a remote branch 

- changing name of a branch 

- pushing to main
  
  **Answer**: 

| functionality                        | git command                                              |
| ------------------------------------ | -------------------------------------------------------- |
| adding a single file                 | git add fileName                                         |
| adding multiple files                | git add fileName1 fileName2                              |
| adding all files                     | git add .                                                |
| git log - detailed                   | git log                                                  |
| git log - overview                   | git log --oneline                                        |
| Get the remote branch                | git remote -v                                            |
| add a new remote branch called orgin | git remote add origin url                                |
| rename a remote branch               | git remote rename old new                                |
| remove a remote branch               | git remote remove origin                                 |
| pushing to a remote branch           | git push -u origin main                                  |
| renaming a branch                    | First switch to that branch <br/><br/>git branch -M main |

#### Q2:What does git fetch and git pull do ?

**Answer**:

- Using git fetch will download changes from the Github 
  remote repository however we will not see those changes be part of the 
  files we have in the working directory

- fetch allows us to grab additional work done on the remote
   master branch without needing to merge it in our working directory 
  files

- Using git pull makes sense when we want to directly grab changes from 
  the remote branch and directly merge them into our current branch

---

## 04-Working-with-others

#### Q1:Write the git commands for the following

- Report back the branches we have 

- Create a new_branch called new_branch

- switch back to that new_branch
  
  **Answer**:
  
   
  
  | functionality                             | git commands          |
  | ----------------------------------------- | --------------------- |
  | report back the branches we have          | git branch            |
  | Create a new_branch called new_branch     | git branch new_branch |
  | switch back to a branch called new_branch | git switch new_branch |

#### Q2:How to rename a branch ?

**Answer**:

1. git switch branch_to_rename

2. git branch -m new_name

#### Q3:Deleting a branch

**Answer**:To delete a branch `git branch -d branch_to_delete_name`

#### Q4:How to merge ?

**Answer**: 

1. Switch to master/main

2. git merge new_branch'

------

## 05-undoing-changes

#### Q1:How can we move to a particular commit ?

**Answer**: 

git log --oneline

git checkout ####### (First 7 digits of hash)

Note => we are simply exploring the historical commit .If w start making changes here they wont be prerserved since HEAD is not pointing at a branch reference.However we could create a new branch at this point in time , reattaching HEAD to a branch again

#### Q2:What does git restore do ?

**Answer**:ultimate Ctrl + z (restore files to their previous commit)

#### Q3:Restore 2 commits back  from the most recent commit in the file myFile.txt?

**Answer**: `git restore --source HEAD ~2 myFile.txt`

#### Q4:How does git reset work ?

**Answr**:

- `git reset #######` => removes commits in front of the specified hash , files unchanged
- `git reset ####### --hard` => removes commits in front of the specified hash , files also changed

#### Q5:git revert

**Answer**: 

Forward-moving undo operation that offers a safe method of undoing changes .Instead of deleting or orphaning commits in a commit history , a revert will create a new commit that ignores the changes specified 

`git revert #######`

---

## 06-Git-and-Github-in-practise

#### Q1:Discuss the following commands `git stash`, `git stash pop` and `git stash apply`

**Answer**:

| git commanad    | functionality                                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| git stash       | Temporarily shelves (or stashes) , we have made to our working copy so we can work on something else and then come back and re-apply later on |
| git stash pop   | get back those preserved changes                                                                                                              |
| git stash apply | applies the saved changes but doesnt pop them out                                                                                             |
