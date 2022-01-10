Git Notes
=====================================

Summarize
-------------------------------------
`repository`: a container for a project that is tracked by Git, use `git init` to initialize a repository, which whill create a __.git__ folder that contains all the tracking information. Local repository is an isolated repository stored on your own computer. Remote repository is stored outside of your isolated local system, usually on a remote server. It's especially useful when working in teams.  

`track`: The timelines and modifications of the files you are tracking. You can start tracking files using `git add <filename>` or `git add .`    

`stage`:  a place that holds all the files that ready to be commited. Only staged files can be commited. You can stage a file using `git add <filename>` or `git add .`  

`commit`: a "snapshot" of the code at a particular time. when you made substantial changes to a extent, you would like to do a 'commit' to leave a message about what you did with `git commit -m "message"`. Only the staged files will be committed. And you can always go back and forth between commits using `git checkout <branchname/commit-hash>`  
You can stage all the tracked files and commit using `git commit -am "message"`  

`checkout`: checkout the files at certain commit, if checkout a branch, will switch to the latest commit of the branch. `git checkout <branchname/commit-hash>`  

`status`: all the changes in the repository, file modifications, untraked files, `git status`  

`log`: view the commit history and all the messages you leave when committing, including time, author, message, file change, `git log`  

`branch`: use another branch to make modifications that won't affect current branch, you can merge the modifications later. Use `git branch` to list the branches, `git branch <newbranch>` to create a new branch, `git checkout <branch>` to switch between branches, `git branch -d  <branchname>` to delete a branch  

`merge`: merge the code changes that you made in an individual branch to a different branch, `git merge <branchname>` to merge a branch to current branch  

`stash`: you can stash your uncommitted changes, switch to another branch or commit, then apply the stash. This can be used when you made modifications to a wrong branch and haven't commit yet. `git stash` will remove the uncommitted changes and store the changes in a "__stash__", `git stash list` will list all the __stashes__, `git stash pop` to apply and delete all the stash, and `git stash pop 1` to apply and delete a particular stash. `git stash apply` to apply stashes, `git stash drop` to delete the stashes.  

Important
-------------------------------------
set line ending to unix style
`git config --global core.autocrlf true`

use `git config --global core.editor "nvim"` to set the default editor to nvim  

User name and email
-------------------------------------

Add user name and email, this is used to identify who you are when you commit something
`git config --global user.name "mlei"`  
`git config --global user.email "leimglg@gmail.com"`  

Check the user name and email  
`git config --global --list`  

Create a local repository
-------------------------------------

convert the current directory to a repository. Will create a __.git__ folder containing all the tracking data  
`git init`  

Add a file to track, will also stage the file, use `git add .` to add all the files listed in `git status`
`git add file_to_commit`  

List all tracked files  
`git ls-files`  

Stage tracked files. Only staged files can be committed using `git commit -m "message"`  
`git commit -a`  

Commit with a message  
`git commit -m "Message"`  

To do the above two steps  
`git commit -am "Message"`  

Check git status, show file changes, which files are modified, which files are untracked
`git status`  

Change the last message  
`git commit --amend -m "Right message"`  

Romove a tracked file  
`git rm --cached file_to_romove`  

Romove a tracked folder  
`git rm -r --cached folder_to_romove`  

View blame info  
`git blame file_to_blame`  

Return a file to last staged status  
`git reset HEAD file_to_unstage`  

View log of commits history, including the time, author, message
`git log`  

Back to state at certain commit, `<commit-hash>` is the code listed using `git log`, ie. "12c4a4776ff20256a02f8809aaf0ea2c23b9ca67" is a hash  
This command will create a new branch  
`get checkout <commit-hash>`

Branch  
-------------------------------------
create a new branch  
`git branch <branchname>`  

Switch to the latest commit of a branch, `<branch>` is the branch name
`get checkout <branchname>`  

Delete a branch by name  
`git branch -d <branchname>`  

Merge a branch to current branch  
`git merge <branchname>`  

Stash
--------------------------------------
you can stash your uncommitted changes, switch to another branch or commit, then apply the stash. This can be used when you made modifications to a wrong branch and haven't commit yet.  

remove the uncommitted changes and store the changes in a "__stash__"  
`git stash`  

list all the __stashes__  
`git stash list`  

`git stash pop`  
apply and delete all the stash  

apply and delete a particular stash  
`git stash pop 1`  

apply all stashes  
`git stash apply`  

delete all stashes  
`git stash drop`  


Push the local repository to github
-------------------------------------
If asked password, input token  

Initialize the remote repository on github (requires config token elsewhere)  
`git remote add origin https://github.com/leimglg/study-notes`  

If already initialized, change the url with a token  
`git remote set-url origin https://<token>@github.com/<username>/<repo>`  

Push for the first time  
`git push --set-upstream origin master`  

Push  
`git push`  

Save the username and password  
`git config credential.helper store`  

Clone and pull a repository from github
-------------------------------------

Clone a repository from github (for initiating)  
`git clone repository_address`  
`git clone https://<tokenhere>@github.com/<user>/<repo>.git`  

Check if the remote file is different (possible changes made by others)  
`git fetch`  

Pull the repository from github (for updating changes made by others)  
`git pull`  

Pull from github and overwrite everything local
------------------------------------------------------------

Fetch to update all origin/master to latest  
`git fetch --all`  
Reset with origin/master  
`git reset --hard origin/master`  

