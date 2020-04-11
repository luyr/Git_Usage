# GIT USAGE
## Basic & Common
- Difference between . and * when using `git add`
``` Shell
git add .  # ignore files according to .gitignore
git add *  # add all files
```
- Remove files in the staging area  
`git rm --cached  <file>`

- Add remote repository  
`git remote add origin <url>`

- Check status 
```Shell
git status
git status -s       # brief version
```

- Check log  
```Shell
git log
git log --oneline    # brief version
git log --oneline --graph    # with branch graph
``` 

- Check what is changed
``` Shell
git diff            # for unstaged file
git diff --cached   # for files in staging area
git diff HEAD       # for all files
```

## Roll Back Related

- When you forget something after commit
```Shell
git commit --amend
git commit --amend --no-edit  # not change commit message
```

- From staged to unstaged  
`git reset <file name>`

- Roll back (delete commit)
```shell
git reset --hard <commit id>
git reset --hard HEAD        # back to current commit
git reset --hard HEAD^       # back to last commit
git reset --hard HEAD^^      # back to the second previous commit
git reset --hard HEAD~3      # back to the third previous commit
```

- Back to current commit
```shell
git reflog  # check all the commit(including deleted ones)
git reset --hard <commit id>
```

 
 - Roll back single file (won't delete commit)  
`git checkout <commit id> -- <file>`  


## Branch
- Create a branch  
```shell
git branch <branch name>  
git check -b <branch name>  # switch to the new branch after creating
```

- Delete branch  
`git branch -d <branch name>`

- Check all branches  
`git branch`

- Switch branch  
`git checkout <branch name>`

## Merge and Rebase
- Merge branch  
```shell
git merge <branch name>  # no message
# with message
git merge <branch name> --no-ff -m "message" <branch name>
```

- Rebase(High Risk)
```shell
git rebase <branch to base>
git rebase --continue/skip/abort  # after solving conflicts
```

## Stash Area
```Shell
git stash   # put modification into stash
git stash pop   # withdraw modification
```