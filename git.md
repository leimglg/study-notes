Git Notes
=====================================

Add user name and email  
`git config --global user "mlei"`  
`git config --global email "leimglg@gmail.com"`  

Check the user name and email  
`git config --global --list`  

Create a locale repsitory
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

Change the last message  
`git commit --amend -m "Right message"`  

Romove a tracked file  
`git rm --cached file_to_romove`  

Romove a tracked folder  
`git rm -r --cached folder_to_romove`  

Git recover a file to last staged status
`git reset HEAD file_to_unstage`


