# Day 3 - Working with others

#### Branches

branches allow us to organize a repository and split it apart so multiple people can work on it or so a solo developer can work on different aspects of a project on a seperate work

A branch represents an independent line of development

Branches serve as an abstraction for the edit/stage/commit process

They are a way to request a brand new working directory , staging area and project history

When we create a branch , all GIt needs to do is create a new pointer , it doesnt change the repository in ny other way 

Branches are just pointers to commits 

Upon creating a new repo with `git init` we create a new branch called the master branch(or main branch)

This is a Branch just like any other but its simply the first one created 

##### Master vs Main

Github has changed the nomenclature for this initial branch to be main branch while Git is still using master branch 

We can also rename any branch 

#### Branches and Commits

Git stores a branch as a reference to a commit 

In this sense , a branch represents the tip of a series of commits -its not a container for commits 

The history for a branch is extrapolated through the commit relationships 

#### Head

a head is simply a reference to a commit object 

we can think of Head as pointing to a specific commit in a branch that we are currently viewing 

using HEAD tells us which branch reference we are currently "checking out"

we can always switch back out head to some other branch(which is a pointer to a commit reference)

`git branch` => Reports back the branches we have 

`git branch new_branch` => Creates a new branch called new_branch 

`git switch new_branch`  => Switches  to new_branch

#### Renaming a branch

`git switch branch_to_rename`

`git branch -m new_name`

Note => We must be checked out on the branch we will rename 

#### Deleting a Branch

`git branch -d branch_to_delete_name` 

Note => We can not delete a branch we are checked out at , We also will get a warning if the branch is not merged .We can confirm we want to do this anyways with -D 

#### Fast-Forward Merge

A new branch is created but the original branch it stemmed from has no additional commits 

#### Merge with no conflicts

There can be no conflicts for example the branch only focussed on files not in the receiving branch , thus the merge simply adds the nw files to the receiving branch

Git will created a commit for you ,It will also request for you to name the commit with a default name of "Merge branch branch_name"

#### Merge with conflicts

However there will be instances where there will be conflicts for example changes in the file on lines that are different between the branches .These are known as merge conflicts and we need to resolve(fix) the conflicts between the branches in order to merge them 

#### How to merge ?

Switch to master 

`git merge new-branch`
