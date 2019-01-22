
<img src="images/anoluke.png" width="100px"> 

#Git Cheatsheet

"...How many anosluke you need for feel the force..."


## Basic commands

### Create

##### Git init

Create a new git repo in our working directory

	$ git init
	
### Link

#####  Add to remote repository

This command takes a remote name and a repository URL

    $ git remote add origin https://github.com/try-git/try_git.git
    
### Show

##### Checking for changes or status

What are the files changed in working directory?

    $ git status 
    
##### History

So we've made a few commits. Now let's browse them to see what we changed.

Fortunately for us, there's git log. Think of Git's log as a journal that remembers all the changes we've committed so far, in the order we committed them.

    $ git log   
    
History of changes for file with diffs
	 
	$ git log -p <file>

##### What is diferent to the last commit?

Take a look at what is different from our last commit by using the git diff command.
In this case we want the diff of our most recent commit, which we can refer to using the HEAD pointer.
    
    $ git diff HEAD
    
##### Diference between id commits

Complete conflicts diff between too commits with too ids

	$ git diff <id-A> <id-B>
    
##### To view a merge conflicts

Complete conflicts diff

	$ git diff
	
Against base file

	$ git diff --base <file>
	
Against your changes

	$ git diff --ours <file>
	
Against other changes
	
	$ git diff --theirs <file>
    
##### Staged Differences

If run git diff with the --staged option you can see the changes you just staged. 

    $ git diff --staged    

### Add, remove files

##### Adding Files with change status to Stage

To tell Git to start tracking changes made to <file.extension>, we first need to add it to the staging area by using git add.

    $ git add .
    $ git add <file.extension>    
    $ git add '*.txt'
    
##### Remove Files of Stage, resetting the Stage

You can unstage files by using the git reset command

	$ git diff --staged
    
##### Remove file to directorie tree 

    $ git rm <file.extension>    
    $ git rm '*.txt'     
    
** importan! ** this command remove file to the working tree    

    
##### Update remote repository changes

We can check for changes on our Git repository and pull down any new changes.
The -u tells Git to remember the parameters, so that next time we can simply run git pull and Git will know what to do.

    $ git pull -u origin <branch>  
    
### Branch
    
##### Switching branch

When developers are working on a feature or bug they'll often create a copy (aka. branch) of their code they can make separate commits to. Then when they're done they can merge this branch back into their main master branch.

	$ git branch <branche>
	
##### Create and switch to new branch

You can create and switch to new branche

	$ git checkout -b <branche>
	
##### List branch

You can list the branch in your repository with.

	$ git branch 
	$ git branch -av	
		
##### Merge Branch

When you have to merge your changes from the **<branch-B>** into the **<branch-A>**.

1. Go to **<branch-A>**
	
       $ git checkout <branche-A>
	
2. Merge **<branche-B>** in my current branch

	   $ git git merge --no-ff <branche-B>

##### Delete branch

You can list the branch in your repository with.

	$ git branch -d <branche>
	
### Update

##### Fetch latest changes from origin

**important!** this does not merge them

	$ git fetch origin <branche>	
	
##### Pull latest changes from origin

Does fetch followed by a merge

	$ git pull origin <branche>
	
	
### Publish

##### Committing

To store our staged changes we run the commit command with a message describing what we've changed. 

    $ git commit -m "Commit example file to can push" 

##### Push the changes to remote repository

The push command tells Git where to put our commits when we're ready, and boy we're ready.

The name of our remote is origin and the default local branch name is master. The -u tells Git to remember the parameters, so that next time we can simply run git push and Git will know what to do.

    $ git push -u origin <branch>

##### tagging version

	$ git tag v1.0
 
### Revert  

##### Undo the state of file to last commit state

Files can be changed back to how they were at the last commit

- <file> : name of file
- <id> : id version of a file

Now the commands posibles are:
	
	$ git checkout -- <file>
	$ git checkout <id>
	$ git checkout <id> <file>      
	
##### Undo the last commit

	$ git revert HEAD
	
##### Return to the last commited state

** important!: you cannot undo a hard reset **

	$ git reset --hard    
    
## Git flow

### New feature

[What happend if I need to do a new feature in the code?](flow/feature.md)

## Git Reference

### Documentation

[Pro git book english](http://git-scm.com/book/en/v2)

[Pro git book spanish](http://git-scm.com/book/es/v2)

[A git guide example](http://rogerdudler.github.io/git-guide/)

### Tutorials
[git immersion tutorial ](http://gitimmersion.com/)



## Humor with git

##### shit it was me

[git blame ](humor/shititwasme.md)

[git rebase ](humor/gitrebaseoriginmaster.md)

	
