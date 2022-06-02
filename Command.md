# Github Note

## Basic
``` bash
git switch <branch_name>

#to move file to staging Area
git add <filename> 

#check the differences between Working Tree and Staging Area
git diff

#disregarded changes 
git checkhout -- <filename>


#commit files
git commit -m '<msg>'

#show the differences between stagin Area and recent commit
git diff --staged

#remove committed files and the file in working tree
git rm <filename>

#get recent commit file 
git reset HEAD <filename>


#check certain file in git log
git log -- <filename>

# restored file to both staging area and working tree
git checkout <commit log number> -- <filename>

# commit the restored file
git commit -m '<msg>'

git config user.name justin6302971
git config user.email justin6302971@hotmail.com

# View existing remotes
git remote -v

# update remotes
git remote set-url origin <new_remote_url>
```




## Branch basic

``` bash 
# list branches
git branch

# create new branch call feature/test
git branch feature/test

# check which branch you are in 
git status 

# switch to feature/test
git checkout feature/test

# merge feature/test branch to current branch
git merge feature/test

# adding : to delete remote branch
git push origin :feature/branch

# delete local branch
git branch -d feature/branch

# switching to the local branch and rename it
git checkout <old_name>
git branch -m <new_name>

# push the new remote branch
git push origin -u <new_name>

# delete old remote branch
git push origin --delete <old_name>

#lists branches merged into master
git branch --merged master 

# lists branches merged into HEAD (i.e. tip of current branch)
git branch --merged

#lists branches that have not been merged
git branch --no-merged 

```

## Merge branch locally
``` bash
# switch to the target branch
git checkout <old_branch>

# merge new branch to current branch
git merge <new_branch>
```

## Show branch history
``` bash
git show-branch
```


## Create subtree
```
	git subtree push --prefix dist origin gh-pages
```

## Reset commit
``` bash
# get commit history
git log 

git reset --hard <commit_id>

git clean -f -d 

git push -f
```

## organize commits before push
``` bash
# checkout commit history
git log --oneline

# choose the base commit(the commit you don't want to modify), after the interactive done, the rest of commit should be modified
git rebase -i <commit_id>  

git reset

git log

git reflog

```

## Create pull request

```bash
#clone repo
git clone <repo_url>

#check branch
git branch -a

#check tracking branches
git branch -vv

#create branch
git checkout -b <branch_name>

#create branch from certain branch
git checkout -b <new_branch> <exist_branch>

#create remote upstream repo(the original repo you created your fork from)
git remote add upstream <repo_url>

#remove upstream
git remote rm upstream 

#set branch upstream
git branch --set-upstream-to <remote> <branch>

#remove branch upstream
git branch --unset-upstream <branch_name>

#make some changes and commit(skip)

#push branch to remote to create pull request
git push -u origin <branch_name>

#go to github to manage pull request

#--------------------------------
#delete branch locally
git branch -d <branch_name>

#delete branch remotely
git push origin --delete <branch_name>

```
## Pull certain branch
``` bash

git clone -b <branchname> <remote-repo-url>

#alternative method(Git version 1.7.10 and later)
git clone -b <branchname> --single-branch <remote-repo-url>


# pull exist branch
git checkout --track origin/<branchname>

#note: pull exist branch after clone certain branch,update all before running the commands
git fetch --all

#note: when remote is not updated with git fetch
#remove with:
git remote rm origin

#and recreate with: 
git remote add origin <git uri>

```

## Submodule

``` bash

git submodule update --init --recursive

git submodule update --recursive --remote

```

## Config setting

``` bash
# list config
git config --list --show-origin

# set user name email locally
git config user.name <username>
git config user.email <useremail>
```

## clean 
``` bash
# check the detail of the file which will be deleted
git clean -n

# delete untracked files
git clean -f　　
```


## merge issues

``` bash
# reset the branch to the status before solving conflicts
git merge --abort

# save temporary changes
git stash save

# load temporary changes
git stash pop



```

## references
1. [create pull request](https://opensource.com/article/19/7/create-pull-request-github)
2. [delete branch](https://www.freecodecamp.org/news/how-to-delete-a-git-branch-both-locally-and-remotely/)
3. [pull certain branch only](https://www.freecodecamp.org/news/git-clone-branch-how-to-clone-a-specific-branch/)
4. [set up upstream](https://devconnected.com/how-to-set-upstream-branch-on-git/)
5. [tracking branch](https://githowto.com/adding_a_tracking_branch)
6. [organize commits](https://blog.carbonfive.com/always-squash-and-rebase-your-git-commits/)
7. [organize commits -2](https://blog.darkthread.net/blog/git-squash-in-vs/)
8. [git cheetsheet](https://blog.darkthread.net/blog/my-git-cheatsheet/)
9. [git clean](https://www.796t.com/content/1547528799.html)
10. [git stash](https://backlog.com/git-tutorial/tw/reference/stash.html)
11. [git diff](https://ithelp.ithome.com.tw/articles/10135441)
12. [git reflog](https://w3c.hexschool.com/git/10bf7677)
13. [git tag](https://medium.com/@emmabostian/using-git-tags-to-version-coding-tutorials-cf9ff28fad4f)