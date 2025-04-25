# Day-4 Going back and undoing changes

#### git checkout

- This is actually  a very versatile command so versatile in fact that developers complained it was used for many different actions , thus new git commands were created such as git switch 

- A checkout is the act of switching between different versions of a target entity 

- The git checkout command can operate on 3 different entities : files,commits and branches

- For example we could use git checkout branch_name instead of git switch branch_name to checkout a new branch 

- Unlike git switch however checkout can operate on commits meaning we can checkout historical commits

- We can checkout a particular commit by specifying its hash , we can get hashes from the git log command and we can also see the abbreviated hash using 
  
  - git log --oneline 

- Then we can provide the hash as 
  
  - git checkout ####### (FIrst 7 digits of hash)

- Typically our HEAD points to the branch which points to the latest commit 

- ![](../assets/01-head-pointing-to-branch.png)

- Upon calling git checkout a9jd3h7 we detach the HEAD to a previous commit 

- ![](../assets/2.png)

- We can think of this as travelling back in history to what our code looked like when we ran this commit 

- This command does not undo previous work , we are simple exploring the historical commit 

- If we are starting to making changes here , we are simply exploring the historical commit 

- This command does not undo previous work , we are simply exploring the historical commit 

- If we start making changes here , they wont be preserved since HEAD is not ponting at a branch reference

- However we could create a new branch at this point in time , reattaching HEAD to a branch again

- After we have seen this commit history we can go back to a particular branch by doing `git checkout master` if we want to go to master branch 

#### git restore

- we can restore a file to its state at the previous most recent commit using the `git restore` command : `git restore fileName`

- We can not undo a git restore command since our changes were not committed 

- Think of this command as an ultimate "Cltr+z" restoring files to their previous commit 

- Typically speaking git restore will restore the file back to the HEAD which typically we have pointing to the most recent commit in the branch 

- This actually gives us even more flexibility in our restore procedure , we can restore a file to any commit in the log 

- we state the Number of commits from the HEAD to go back to 
  
  - `git restore --source HEAD~N file.txt`
  
  - example `git restore --source HEAD~2 myFile.txt`

- Finally git restore allows us to unstage files that we had already added to the staging area using git add 

- We can do this with 
  
  - `git restore --staged fileName`

#### git reset

- git reset alllows us to remove commits and reset the branch 

- There are 2 main types of git reset calls
  
  - ``git reset #######``
    
    - removes commits in front of the specified hash called files unchanged 
  
  - `git reset ####### --hard`
    
    - removes commits and the changes in the files

- This means when  we do git reset we wont notice a change in the files themselves we just reset the commits 

- This is useful if we accidentally committed to the wrong branch (for example maybe we forgot to run git switch right after creating a new branch , accidentally committing to the original branch)

- In the case where we just want to undo everything , including changes and have the branch files look like they did at a previous commit we have to add the flag `--hard`
  
  - For example `git reset f3h9702 --hard`
  
  - Technically we can try to recover a commit before GIt does its garbage collection , however we should operate under the assumption that a `--hard` reset is not recoverable 

#### git revert

- The git revert command will create a new commit that undoes from previous commits but keeps these commits in the branch 

- A git reset goes back and removes th commits (and changes if it is --hard)

- A git revert creates a new commit that matches the historical state of a previous commit 

- git revert doesnt change the project history which makes it a safe operation for commits that have already been published to a shared repository 

- A git revert creates a new commit that matches the historical state of a previous commit 

- The git revert command is a forwad-moving undo operation that offers a safe method of undoing changes .Instead of deleting or orphaning commits in a commit history , a revert will create a new commit that ignores the changes specified 

- git revert is a safer alternative to git reset in regards to losing work 

- Syntax : `git revert #######` 


