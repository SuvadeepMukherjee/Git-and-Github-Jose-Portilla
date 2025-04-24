# Day 2 - Starting to use Git

`git status` => checks the status of current git repository 

`git init` => initializes a git repository 

`git add file_one.txt` => adds file_one.txt to the staging area

`git add file_one.txt file_two.txt` => adds file_one.txt and file_two.txt to the staging area

`git add . ` => adds all files to the staging area 

`git log` => It will show a list of all the commits made to a repository including the hash,message and metadata

- Note => Press q to quickly exit out of git log

`git remote -v` => checks for remote branches ,if there is no connection to a remote branch then we wont see a URL 

`git remote add name https://url.git` => adds a remote branch using the git remote command syntax

By convention we call this remote branch the origin branch 

`git remote add origin https://url.git`

`git remote rename <old> <new>` => To rename remote branch

`git remote remove <name>` => To remove remote branch

`git push -u origin main/master` => push  the main/master branch to the remote branch called origin with the above command 

Note => GIthub has officially changed the naming convention of its master branch to main branch 

`git branch -M main` =>  change the branch name to main

There are 2 options of getting repository changes from a remote branch(like the remote branch on Github) 

- git pull

- git fetch

git fetch

- Using git fetch will download changes from the Github remote repository however we will not see those changes be part of the files we have in the working directory 

- fetch allows us to grab additional work done on the remote master branch without needing to merge it in our working directory files 

- using git fetch makes sense when we are working with others and want to see what changes they have made but arent ready to overwrite your own files yet 

- Also if we are simply working by yourself and we may want to just fetch remote changes without overwriting our latest work 

- When using fetch we will just use 
  
  - git fetch 

- But we can specify to fetch specific branches using 
  
  - git fetch <remote> <branch>
  
  - git fetch origin

git pull

- Using git pull makes sense when we want to directly grab changes from the remote branch and directly merge them into our current branch 

- This means we will literally update the files in our working directory to match up and merge with the remote branch 

- In general we should pull before pushing to a remote branch to make sure we are in sync with `git pull`

- Example walkthrough 
  
  - `git fetch` 
  
  - `git checkout origin/master` (Checks out whats happening in the remote branch origin/master  )
  
  - Then after we have seen the changes we can go back to `git switch master` (our local branch)
  
  - `git pull`  => pull the changes in origin  



 


