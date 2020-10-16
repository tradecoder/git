# git
Git Documents

## Clone a project from the github

`git clone https://github.com/githubusername/projectname.git`

Example clone of the this project:

`git clone https://github.com/tradecoder/git.git`

## Add remote url from local machine
`git remote add origin https://github.com/githubusername/projectname.git`

Example add of this project url

`git remote add origin https://github.com/tradecoder/git.git`

## Remove remote url from the local machine
`git remote remove origin`

If you want to add another remote url, at first you need to remove the current remote url then to add new url

## Add any changes including files, folders and codes
`git add --all`

## Commit all changes 
`git commit -m 'your commit message here'`

## Push your source code to the github
`git push` (This will push the source codes on the current branch) <br/>
`git push origin master` (This will push the source codes to the master branch) <br/>
also `git push -u origin master`

## Check recent commit history
`git log`

## Initialize new git repository
`git init`

## Reset saved but uncommitted code 
First save unsaved work or close and reopen the file, then use this command

`git reset --hard` <br/>Then use `git pull`

## Restore your currently changed files
`git restore`

## Force to push your code if you think it's ok but it is refusing
`git push -f origin master`

## Create a new branch
`git branch your_new_branch_name`

## Go / switch to a branch
`git checkout your_target_branch_name`<br/>
`git switch your_target_branch_name`

## Create a new branch and switch to that branch
`git checkout -b your_new_branch_name`

## Check the changes status
`git status`

## Create an orphan branch 
An ophan branch is completely a new branch without any git history or git commit. You need to commit add all the files to this branch before making a commit

```
git checkout --orphan yourNewBranchNameHere
git add -A
git commit -m 'commitMessageHere'
```

## Remove git commit history from your repo
First make an orphan branch, then add all files, then commit the files to that orphan branch, then delete the master branch, then remove remote origin if exists, then git init, then add remote origin url, then push your code with force and finally remove all the old files, continue your work...
```
git checkout --orphan newbranch
git add -A
git commit -m 'firstcommit'
git branch -D master
git branch -m master
git remote remove origin
git init
git remote add origin https://github.com/yourUsername/yourGithubRepoName.git
git push -f origin master
git gc --aggressive --prune=all
```

## Warning: Shallow update not allowed!
## How to remove shallow clone?
## What is shallow clone?
Shallow clone is just cloning a repository using `--depth` <br/>
If you use Shallow clone to your local machine, it will not allow you to push your codes to your remote origin. You have to remove the shallow clone record to push your codes to remote repository. To do this just follow this :
```
git fetch --unshallow https://github.com/this_is_the_source_url_from_where_you_did_clone_it.git
```
Now do your regular work, if you still have not set your new remote url, set it before to push
```
git remote remove origin
git init
git remote add origin https://github.com/your_new_repository_url_here.git
git push origin master
```
Change the branch name if you need. Set upstream as your own

## Get update codes on local machine from the github repo
`git pull` also `git pull origin master`
