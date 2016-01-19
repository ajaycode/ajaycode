#Git Commands#
 
File listing

    git ls-files

Trace changes in a file
  
    git blame <filename>

Displays all the commits made to the repository
 
    git log --oneline
    git log --oneline readme.txt

Log with pagination (-p)

    git -p log --oneline

List the files, that are a part of the commit

    git log --stat

Show configuration settings

    git config --list

Modify a setting

    git config --global user.name "Your Name"

What files have changed

     git status

What is the change, between working area and staging area?

      git diff

What is the change between staging area and the repository?
 
      git diff --staged

Add file and commit in a single operation

      git commit -a -m "your comment"

Displays the files, but won't add

      git add --dry-run

Commit parts of a file
 
      git add -p

Checkout the last committed version of readme.txt

      git checkout -- readme.txt

Show parents of the commits

      git log --parents --abbrev-commit

??
      
      git log --patch
      git log --patch-with-stat

Show details on the last commit

      git log -1

Edit the most recent commit

      git commit --amend

master = default branch
HEAD   = typically points to the last commit of the branch

Display the SHA1 id of the latest commit
 
      git rev-parse HEAD 
             or
      git rev-parse master
      Verify with git log --oneline

Revert to a specific version of your directory, i.e., HEAD moves to an older commit
 
      git checkout <SHA1id>

Get back to current state
 
      git checkout master

Tag a particular commit

      git tag <tag_name> -m "comment" <SHA1_id>

Checkout commit with a particular tag

      git checkout <tag_name> 

Show information about a tag

      git show <tag_name>

List all tags

      git tag 
??
   
      git rev-parse master~3
      git show master@{3}
      git show master^^^

Checkout a branch
      
      git checkout <branch_name>

Delete a branch

      git branch -d <branch_name>
      
Display commits across all branches

      git log --graph --decorate --pretty=online --all --abbrev-commit

Display all available branches

      git branch
      git branch -v    #-v displays the SHA1 id
Create a new branch from an existing branch
      
      git checkout -b <new_branch_to_be_created> <existing branch>
Display a record of all times, that you have created branches

      git reflog
Save uncommitted work in a branch
  
      git stash
Shows the stash

      git stash list
Reapply the work to the current branch

      git stash pop
??

      git diff <branch_name1>...<branch_name2>
Merge <filename> into <branch_name1> ?
      git diff --name-status <branch_name1>...<branch_name2> M <filename>
 
Merged file conflicts
<<<<HEAD    #Start of changes in HEAD
   code 1
=====       #Separator between conflicting changes
   code 2
>>>>bugfix  #End of bug fix changes

Use git mergetool for merges, especially 3 way merges.  Use KDiff3 (Windows) or gvimdiff(Linux)

Show the base commit between <branch_name1> and <branch_name2>
     
      git merge-base <branch_name1> <branch_name2>
Show the differences between branch1 and branch2, relative to when they first differed

      git diff <branch_name1>...<branch_name2>
List all branches in the clone's repository
   
      git branch --all

References:

[1] Learn Git in a month of lunches - Rick Umali 






 