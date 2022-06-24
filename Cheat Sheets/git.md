# git cheatsheet
---
## setup
```shell
git config --global user.name ""
git config --global user.email ""

git config --global color.ui auto
```

## init
``` shell
git init 
git clone <url>
```

## stage & snapshot
``` shell
git status 
git add <file>
git reset <file>
git diff # shows diff among files which are changed but not staged
git diff --staged
git commit -m ""
```

## branch & merge
```shell
git branch # lists all branches
git branch <branch-name> # creates new branch 
git checkout # switch between branches 
git merge <branch>
git log
```

## share & update 
```shell
git remote add <alias> <url>
git fetch <alias>
git merge <alias>/<branch>

git push <alias> <branch>
git pull # fetch + merge
```

## tracking path changes
```shell
git rm <file>
git mv <existing-path> <new-path> # moves + stage the move
```
---