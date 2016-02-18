#Git Commands# 
----------

###Logs###
File listing

    git ls-files

Trace changes in a file
  
    git blame <filename>

Displays all the commits made to the repository
 
    git log --oneline
    git log --oneline readme.txt

What changed, since and until
   
    git diff --name-only "@{1 week ago}" "@{1 day ago}"
    git whatchanged --since="12/15/2016"
    git log --since="1 week ago" --until="yesterday"

What changed in the last commit

    git whatchanged -n 1

List the changes on the remote (or origin)

    git fetch origin
    git diff origin/master

Log with pagination (-p)

    git -p log --oneline

Display commits performed by author "ajay"

    git log --author="ajay"
    git log --pretty=oneline --author="ajay" #quotes are not required around the name, if it's a single word.

Display the patch, associated with each commit

    git log -p
List the files, that are altered as part of the commit. Includes the relative number of lines added/deleted from each of the files.

    git log --stat

###Git Configuration###

Show configuration settings

    git config --list

Modify a setting

    git config --global user.name "Your Name"
    git config --global user.email "me@mydomain.com"

Cache credentials (eg. avoid retyping passwords for 300 s/5 minutes)

    git config credential.helper 'cache --timeout=300'

###Changes###
What files have changed?

    git status

What is the change, between working area and staging area?

    git diff

What is the change between staging area and the repository?
 
    git diff --staged

List all files, that have changed, since your last commit:

    git diff --name-only

List changes between local and remote

    git fetch #get the changes, but do not merge the files
    git diff <local> <remote>
    eg. git diff master origin/master #for master branch

###Checkout and Commit###
Add file and commit in a single operation

    git commit -a -m "your comment"
    git commit -am "your comment"

Displays the files, but won't add

    git add --dry-run

Commit parts of a file
 
    git add -p

Update changes made on local repo onto the remote server

    git push origin master

Fetch from and merge/Receive modifications from server into local repository
   
    git pull origin master
Checkout the last committed version of readme.txt.  Also discard local (working directory) changes.  Use this, if you want to undo all local changes and get the version of the file, from the most recent commit.

    git checkout -- readme.txt
Checkout a particular commit

    git log -p --oneline #get the hash that you are interested in reverting to
    git checkout <hash> readme.txt

Cancel staged changes before committing, ie., undo changes that were staged - git add was done, but commit wasn't.  

    git reset HEAD readme.txt
    #`reset` command does not change the working directory. Working directory contains the changes made.  Use `checkout` to remove the unwanted changes
    git checkout readme.txt

Cancel a commit

    git revert HEAD
    git hist #to view the log


Show parents of the commits

    git log --parents --abbrev-commit

??
      
    git log --patch
    git log --patch-with-stat

Show details on the last commit

    git log -1

Edit the most recent commit

    git commit --amend

Move a file/directory within the repository or rename

    git mv <orig> <dest>

Remove a file/directory from the repository

    git rm <file_or_directory>

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
###Tags###

Tag a particular commit

    git tag <tag_name> -m "comment" <SHA1_id>

Checkout commit with a particular tag

    git checkout <tag_name> 

Show information about a tag

    git show <tag_name>

List all tags

    git tag 
Remove a tag

    git tag -d <tag_name>

??
   
    git rev-parse master~3  
    git show master@{3}
    git show master^^^

###Branch###

Create a new branch

    git checkout -b <branch_name>

Create a new branch from an existing branch
      
    git checkout -b <new_branch_to_be_created> <existing branch>

Checkout a branch
      
    git checkout <branch_name>

Delete a branch

    git branch -d <branch_name>
      
Display commits across all branches, in a tree format

    git log --graph --decorate --pretty=oneline --all --abbrev-commit

Display all available branches

    git branch
    git branch -v    #-v displays the SHA1 id

Display a record of all times, that you have created branches

    git reflog
Save uncommitted work in a branch
  
    git stash
Shows the stash

    git stash list
Reapply the work to the current branch

    git stash pop
Diff between the tips of two branches (note the number of dots:2)

    git diff <branch_name1>..<branch_name2>
Diff between the two branches, from their common ancestor

    git diff <branch_name1>...<branch_name2>

Dry run of a merge.  Git does not have a dry-run option.

    #Do a merge with no commit and no fast-forward.
    git merge --no-commit --no-ff <branch_name>
    #if you have to undo the commit
    git merge --abort

Merge `<filename>` into `<branch_name1>` ?

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
      git branch -a

List all remote branches

	git branch -r


####References####

1. Learn Git in a month of lunches - Rick Umali 
2. [Git How To](http://githowto.com/)
3. [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

 