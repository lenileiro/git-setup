
# SSH keys
To generate SSH keys on ubuntu

make sure that the email address same as one used to login to your github account

`
ssh-keygen -t rsa -C "example@example.com"
`
Press Enter

When promted to enter passphrase
 
Input a secure password
 
This provides an additional layer of security that require password incase your security bridge to your laptop or server

### Copy generated key 

`
cat /home/user/.ssh/id_rsa.pub
`

Copy

On Github 

`
 setting->SSH and GPG keys->New SSH key
`

Enter Title
Paste Key

# Create a new repository

Put your

- Repository name
- Description (optional)

Don't Initialize this repository with a README  for now as I will guild you to do that later on.

Select your prefered license 

Then Click Create repository
# Git
download git

`
sudo apt-get install git
`

make project directory

`
mkdir project
`

`
cd project
`

`
git init
`

# Create README.md

Using editor of your choice make `README.md`

# Connect to repository

`git remote add origin git@github.com:username/repository.git .`

`git pull`

# Push to repository

`git add .`

`git commit -m 'initial commit'`

`git push -u origin master`

### git add and commit

`
git commit -am ' initial commit'
`

### Errors

incase of push error

`git pull --allow-unrelated-histories`

# Create Branches and push to Github
### Check what branch you are on

`
git status
`

### Create Branch

`
git branch <branchName>
`

### Check Branches

`
git branch --list
`

`git branch -a
`

### switch Branches

`
git checkout <branchName>
`

### Create and checkout Branch

creates and switches to the branch

`
git checkout -b <branchName>
`

### Push branch to github

`
git push --set-upstream origin <branchName>
`

# Merge and Delete Branches

### merge branch

checkout the branch you want to merge with

`
git checkout <branchName> 
`

Merge branches

`
git merge <branchName>
`

### delete branch

`
git branch -d <branchName>
`

`
git push origin :<branchName>
`

# Fetch and Pull from Origin

### Pull
Update the local repository to match the remote repository

`
git pull 
`

### Fetch

Update the branches on Local repository

`
git fetch origin
`

# gitignore file

Used to Ignore files not to commit

Ignore folder
Allow only specified file

`
src/*

!src/style.css

*.zip
`

# Stash Command
Test code variation without commiting

show changes
`
git diff
`

`
git stash save "worked on x function"
`

Stash list

`
git stash list
`

To apply stash

`
git stash apply stash@{0}
`

Apply and drop Stash

`
git stash pop
`

To delete stash

`
git stash drop stash@{0}
`

Delete All stash

`
git stash clear
`


# Fixing common Mistakes and Undoing Bad Commits

### Log

`
git log
`

`
git log --stat
`

### To reset changes

`
git checkout -- .
`

### To reset on a specific file

`
git checkout <fileName>
`

### Remove untracked files 

`
git clean -df
`

### Amend bad commits

`
git commit --amend -m "my correct message" 
`

### Add changes to the last commit

`
git commit --amend
`


### copy commit to different branch

get the commit hash

`
git log
`

copy atleast the first  8 hash


`
git checkout <desiredBranch>
`

`
git cherry-pick <hash>
`

`
git log
`


### remove commit from branch

3 types of reset

copy the hash of the last desired commit

#### soft reset

`
git log
`

`
git reset --soft <commitHash>
`

Files are still in the staging area


`
git status
` 

#### mix reset  

`
git reset <commitHash>
`

Changes are in the working directory

`

same state as 
git add .
`

required

#### hard reset

return the file to the initial state of commit for tracked files
`
git reset --hard <commitHash>
`

same as 

`
git checkout -- .
`


### Recover Commits

`
git reflog
`

copy the hash of the commit

`
git checkout <ReflogHash>
`

make a branch on the reflogHash to save commit on a branch

`
git checkout backup
`


### Git Revert

Find the commit hash 

`
git log 
`

`
git revert <commitHash>
`

check differences in commit

`
git diff <oldhash> <newhash>
`


Revert last commit by history number

`
git revert HEAD~3
`

# commands with zsh short cut

### status

git status `gst`

### add

git add .  `ga .`

git add --all  `gaa`

git add --patch `gapa`

git add --update `gau`


### branch

git branch `gb`

git branch -a `gba`

git branch --remote `gbr`

git branch --set-upstream-to = origin/$(current_branch) `ggsup`

### checkout

git checkout -b `gcb <branch>`

git checkout `gco`

### commit

git commit -a -m `gcam 'commit msg'` 


### clean
git clean -df `gclean`

### cherry pick
git cherry-pick `gcp`

### diff

git diff `gd`

### fetch

git fetch `gf`

git fetch origin `gfo`

### push and pull

git push `ggp`

git pull `ggl`

git push --set-upstream origin $(current_branch) `gpsup`

### update

git update-index --assume-unchanged `gignore`


### log

git log --stat --color `glg`

git log --oneline --decorate --color `glo`

git log --graph --pretty = format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --all `glola`


### stash
git stash save `gsta`

git stash apply `gstaa`

git stash drop `gstd`

git stash list `gstl`

git stash pop `gstp`

git stash clear `gstc`

git stash show --text `gts`


