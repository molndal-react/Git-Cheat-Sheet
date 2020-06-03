
## Git Cheat Sheet

#### Single Git Commands
Initialize a git repo in the current directory

    # git init

Add a remote called "origin"

    # git remote add origin https://github.com/your-username-here/your-repo-here.git

Add all untracked changed files to staging, ready to be committed
    
    # git add -a

Commit with a message
    
    # git commit -m "some message here"

Push from local branch "master" up to remote branch "origin"
    
    # git push origin master

Pull from remote branch "origin" down to local branch "master"
    
    # git pull origin master

Force push "master" branch to remote "origin" forcing the remote to accept your changes 
    
    # git push --force origin master
    
Force pull and reset all files to match origin. (Won't mess with files in .gitignore)    
   
    # git fetch --all
    # git reset --hard origin/master    

Removes untracked files (not those ignored). Such as those .orig files that are left after resolving conflicts
    
    # git clean -f -n    // do this command first, with "n" flag to see what would be removed
    # git clean -f       // this command actually removes the files

View remotes

    # git remote -v

View current branch you are on

    # git branch -l

Switch to a branch

    # git checkout your-branch-here

Delete a branch
    
    # git checkout other_than_branch_to_be_deleted
    // Deleting local branch
    # git branch -D branch_to_be_deleted
    // Deleting remote branch
    # git push origin --delete branch_to_be_deleted

Rebase the current branch off of some other branch (most of the time "some-other-branch" will be "master")
   
    # git branch -l                  // shows you are currently on some-branch
    # git rebase some-other-branch   // now rebase off of some-other-branch

Create and push a tag up 

    # git tag
    # git tag -a v1.0.1 -m "something here about it"
    # git push origin v1.0.1

Delete a tag

    # git tag -d v1.0.1
    # git push origin :refs/tags/v1.0.1

#### Common Git Scenarios REBASE

If conflicts occurs then checkout to your branch and do following steps

    $ git pull origin develop --rebase
    $ Fix conflicts and save
    $ git add -a
    $ git commit -m "updated my package"
    $ git rebase --continue
    $ If rebase went through then continue with
    $ git push -f
    
