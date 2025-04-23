# Section 1 -Introduction to Version Control,Git and Github

- Git typically refers to the entire project , while git is the actual program used 

- Git comes pre-installed on macOS and Linux

- `git --version` => checks the version of GIt installed 

- We can check the current configuration with the commands 
  
  - `git config user.name`
  
  - `git config user.email`
  
  - If it comes as blank it means no name or email has been registered

- The configuration commands are 
  
  - `git config --global user.email "you@example.com"`
  
  - `git config --global user.name "Your Name"``
  
  - to set your account's default identity.
    Omit --global to set the identity only in this repository.

- `git init`
  
  - This command initializes a git repository on our local machine
  
  - we only need to run this command once per project 
  
  - upon creating a repository with git init we will create a hidden .git file 
  
  - The .git file is a hidden file that manges the versioning of the files inside the git repository 
  
  - upon creating a git repository all the folders/directories inside the top level Git repository will also be part of that repository meaning all the changes are tracked

- git status
  
  - This command will report back the status of our git repository 
  
  

-  Cloning a public github repository created online
  
  - `git clone https://github.com/SuvadeepMukherjee/my-second-repo.git`

- Cloning a private github repository 
  
  - Create a Personal Access Token(PAT) on GIthub.com , when using git clone reference the PAT 
  
  - ![](../assets/pat.png)

               `git clone https//token@github.com/account/repo.hit`

                for example 

                `

`git clone https://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@github.com/SuvadeepMukherjee/private-repo.git``
