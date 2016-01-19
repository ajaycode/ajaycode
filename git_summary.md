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

      
 




 