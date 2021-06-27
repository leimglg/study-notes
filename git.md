Git Notes
=====================================

User name and email
-------------------------------------

Add user name and email  
`git config --global user.name "mlei"`  
`git config --global user.email "leimglg@gmail.com"`  

Check the user name and email  
`git config --global --list`  

Create a local repository
-------------------------------------

convert the current directory to a repository  
`git init`  

Add a file to track  
`git add file_to_commit`  

Stage tracked files  
`git commit -a`  

Commit with a message  
`git commit -m "Message"`  

To do the above two steps  
`git commit -am "Message"`  

Check git status  
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

Veiw log of commits  
`git log`  

Push the local repository to github
-------------------------------------
Initialize the remote repository on github  
`git remote add origin https://github.com/leimglg/study-notes`  

Push for the first time  
`git push --set-upstream origin master`  

Push  
`git push`  

Clone and pull a repository from github
-------------------------------------

Clone a repository from github (for initiating)  
`git clone repository_address`  

Check if the remote file is different  
`git fetch`  

Pull a repository from github (for updating changes made by others)  
`git pull`  



